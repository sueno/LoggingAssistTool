
���M���O���C�u����
---
�����̃N���X�Ƀ��M���O������ǉ�����D

���M���O������ǉ�����N���X�̃\�[�X�R�[�h��ύX����K�v���Ȃ��̂������D(�{���̏����ƃ��M���O�����̊��S�ȕ���)

logger.jar�Ƀp�X��ʂ��Ύg����(�n�Y�D����m�F�͂��Ă��܂���)

�ʓrjavassist���C�u�������K�v�D


�Ƃ���N���X�Ƀ��O���Ƃ鏈����ǉ�������@

1. �V�����N���X�����

2. info.nohoho.logger.StateLogger���p��(����Ȃ�����)

3. ���M���O�叫�N���X��info.nohoho.logger.annotation.TargetClass�A�m�e�[�V�����̈����Ɏw��

4. ���M���O�ΏۃN���X�Ɠ������\�b�h���`

5. ��`�������\�b�h�Ƀ��O���Ƃ鏈�����L�q����

6. ������N���X���R���p�C�����C�N���X�p�X�ɒǉ�

7. ```info.nohoho.logger.Weave.weave();```���v���O�������s�̎n�߂ɍs���悤�ɏ�����ǉ�


��) Bank�N���X��doOpen(String name, String passwd)�Ƀ��O���Ƃ鏈����ǉ�
```
import info.nohoho.logger.annotation.TargetClass;
import info.nohoho.logger.StateLogger;

//�^�[�Q�b�g�N���X��Bank
@TargetClass("Bank")

//s.logger.StateLogger���p��
public class Bank_Logger extends StateLogger {

	//���M���O�ΏۃN���X�Ɠ������\�b�h���`
	public void doOpen (String name, String passwd) {
		//���O���Ƃ鏈�����L�q
		System.out.println("doOpen����΂ꂽ��I");
	}
}
```
