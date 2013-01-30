
ロギングライブラリ
---
他プロジェクトの副産物

既存のクラスにロギング処理を追加する．

ロギング処理を追加するクラスのソースコードを変更する必要がないのが特徴．(本来の処理とロギング処理の完全な分離)

logger.jarにパスを通せば使える(ハズ．動作確認はしていません)

別途javassistライブラリが必要．


とあるクラスにログをとる処理を追加する方法

1. 新しいクラスを作る

2. s.logger.StateLoggerを継承(いらないかも)

3. ロギング大将クラスをs.logger.annotation.TargetClassアノテーションの引数に指定

4. ロギング対象クラスと同じメソッドを定義

5. 定義したメソッドにログをとる処理を記述する

6. 作ったクラスをコンパイルし，クラスパスに追加

7. ```Weave.weave();```をプログラム実行の始めに行うように処理を追加


例) BankクラスのdoOpen(String name, String passwd)にログをとる処理を追加
```
import logger.annotation.TargetClass;
import logger.StateLogger;

//ターゲットクラスはBank
@TargetClass("Bank")

//s.logger.StateLoggerを継承
public class Bank_Logger extends StateLogger {

	//ロギング対象クラスと同じメソッドを定義
	public void doOpen (String name, String passwd) {
		//ログをとる処理を記述
		System.out.println("doOpenがよばれたよ！");
	}
}
```
