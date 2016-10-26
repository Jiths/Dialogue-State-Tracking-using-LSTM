## Todo
Translate manual (and comments on source codes) to English 

## Name
DSTracker4DSTC4

## Overview
Dialogue state tracker for [DSTC4](http://www.colips.org/workshop/dstc4/)

[DSTC4](http://www.colips.org/workshop/dstc4/)�p�̑Θb��ԒǐՊ�

## Description
DSTracker4DSTC4 is a dialogue state tracker for DSTC4, written in Python. 
This tracker is based on Long-shot term memory, and estimates dialogue states from an input utterance and its past history.
This program 1) constructs trackers from training data, and 2) evaluates these trackers. 

<!-- 
DSTracker4DSTC4��python�ŏ����ꂽDSTC4�p�̑Θb��ԒǐՊ�i�Ȍ�A�g���b�J�[�j�B���̃g���b�J�[�̊�{�I�Șg�g�݂�Long-short term memory�Ɋ�Â��Ď�������Ă���A�ߋ��̗����Ɠ��͂��ꂽ���b����Θb�̏�Ԃ𐄒肷��B
���̃v���O�����ł́A1)�P���f�[�^����g���b�J�[�̍\�z��2)�\�z�����g���b�J�[�̐��\�]�����s���B
-->

## Demo
Execute "main.py" in DSTC4 directory.  
<!-- 
DSTC4�t�H���_��main.py�����s
-->

## Requirement
### Mandatory
* Dialogue data whose form follows the specification of DSTC4. 
* Python (version 2.7.6+)
* Pybrain and its dependencies (0.3.3+)
* Scikit-learn (version 1.5+)
* fuzzywuzzy (0.5.0+)
* NLTK (3.0.2+)
* gensim (0.12.1+)

<!-- 
* DSTC4�����̎d�l�ŋL�q���ꂽ�Θb�f�[�^
* Python (version 2.7.6�œ���m�F�ς�)
* Pybrain�Ƃ��̈ˑ����C�u����(0.3.3�œ���m�F�ς�)
* Scikit-learn (version 1.5�ȏ�)
* fuzzywuzzy (0.5.0�œ���m�F�ς�)
* NLTK (3.0.2�œ���m�F�ς�)
* gensim (0.12.1�œ���m�F�ς�)
-->

### Optional
* python_Levenshtein 

## Usage
* [Construction of trackers:] Set the variable "isLearnLSTM" in "DSTC4/main.py" as "True". 
* [Construction and evaluation of trackers with Sentence2Vec] 1) Set variables "isLearnDoc2vec4LSTM", "isLearnLSTM" and "ifFindTheBestOneOverLearnedNetworks" in "DSTC4/main.py" as "True". 2) Set the variable "isUseSentenceRepresentationInsteadofBOW" in "DSTC4/dstc4_traindev/scripts/LSTMWithBow.py" as "True". 3) Execute "main.py"
* [Evaluation of trackers:] Set the variable "ifFindTheBestOneOverLearnedNetworks" in "DSTC4/main.py" as "True", then exucte "main.py". 
* [Construction and evaluation of trackers with Committee:] Set the variable "isLearnAndEvaluateNaiveEnsembler" in "DSTC4/main.py" as "True", and execute "main.py". 

<!-- 
* [�g���b�J�[�̍\�z:] DSTC4/main.py����isLearnLSTM��True��ݒ肵��main.py�����s�B
* [Sentence2Vec�𗘗p�����g���b�J�[�̕]���ƍ\�z:] 1)DSTC4/main.py����isLearnDoc2vec4LSTM��True��ݒ�A2)DSTC4/main.py����isLearnLSTM��ifFindTheBestOneOverLearnedNetworks��True��True��ݒ�B�܂�3)DSTC4/dstc4_traindev/scripts/LSTMWithBow.py����isUseSentenceRepresentationInsteadofBOW��True�ɂ���B���̌�Amain.py�����s
* [�g���b�J�[�̕]��:] DSTC4/main.py����ifFindTheBestOneOverLearnedNetworks��True�ɐݒ肵�āAmain.py�����s�B
* [�R�~�b�e�B�[�Ɋ�Â��g���b�J�[�̕]���ƍ\�z:] DSTC4/main.py����isLearnAndEvaluateNaiveEnsembler��True��ݒ肵�āAmain.py�����s
-->

## Install
1. install all requirment in "Mandatory". 
2. download this project and set python binary path to DSTC4 directory. 
3. put dialogue data into DSTC4\dstc4_traindev\data. 

<!-- 
1. Requirment��Mandatory���C���X�g�[������
2. �{�v���W�F�N�g���_�E�����[�h����DSTC4�t�H���_��Python�̎��s�p�X��ʂ�
3. �Θb�f�[�^��DSTC4\dstc4_traindev\data�t�H���_�ɓ����
-->

## Introducing new feature
In order to append new feature, we need implement following part in "DSTC4\dstc4_traindev\scripts\LSTMWithBOW.py": 

* [Registration of new feature:] __rejisterM1sInputFeatureLabel
* [Calculation of registered feature:] __calculateM1sInputFeature

<!-- 
�g���b�J�[�ւ̐V���������ʂ𓱓�����ۂɂ́A�P�j�����ʂ̓o�^��2)�o�^���������ʂ̌v�Z���K�v�ƂȂ�B���̍ۂ́ADSTC4\dstc4_traindev\scripts\LSTMWithBOW.py�̈ȉ��̉ӏ��ɒǋL����B

* [�����ʂ̓o�^:] __rejisterM1sInputFeatureLabel
* [�o�^���������ʂ̌v�Z:] __calculateM1sInputFeature

�ڍׂ�ǋL��̓\�[�X�R�[�h�̊Y�������Q�Ƃ��ꂽ���B
-->

## Upload to CodaLab (DSTC4 competition)

<!-- 
[�g���b�J�[�̕]��]���s���č쐬���ꂽ�Abaseline_dev.json��answer.json�Ƀ��l�[������B�����āA���̃t�@�C����zip�Ɉ��k����B�Ō��zip�t�@�C�����ȉ��̃T�C�g�ɍs���Ē�o����B
https://www.codalab.org/competitions/4971#participate.
-->>


## Tips
TBA

## Contribution
TBA
## Licence
TBA

## Author

[TakuyaHiroka](http://isw3.naist.jp/~takuya-h/)