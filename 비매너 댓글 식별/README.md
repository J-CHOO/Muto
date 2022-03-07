# 비매너 댓글 식별
뉴스 기사의 댓글 (comment) 중 편견, 혐오 표현 (bias, hate)이 포함된 댓글을 식별하는 과제 (데이터는 저작권상 공개하지 않습니다.)
  - 이어드림스쿨 AI과정 중에 진행한 프로젝트로, [AI connect](https://www.aiconnect.kr/main/competition/detail/204/task/214/assignmentinfo)플랫폼에서 진행한 대회입니다.

## 1. 과제개요
- 멀티 라벨 자연어 분류 (Multi-label Text Classification)
    - 자연어 영역 | 개방형 문제 | Macro F1-Score



- 문제정의
    - 뉴스 기사의 댓글 (comment) 중 편견, 혐오 표현 (bias, hate)이 포함된 댓글을 식별하는 과제



- 추진배경

    - 온라인 게임 속 비매너 채팅 빈도 증가 추세

    - 건전한 온라인 댓글, 채팅 문화 정착을 위한 혐오, 편견적 언어 필터링의 필요성 증대



## 2. 데이터 설명
- 데이터 구조

    - train.csv : 8367개의 뉴스 기사 제목 및 해당 기사 댓글 하나, 댓글이 가진 혐오 표현 종류를 분류한 라벨 두가지 (bias, hate)
    (필요에 따라 train 데이터를 train / validation 으로 나누기 가능) 

    - test.csv : 511개의 뉴스 기사 제목 및 해당 기사 댓글 하나



- 제출방법
    - 'ID' 값에 유의하여 첨부드린 sampe_submission.csv의 'bias'와 'hate' column을 분류된 라벨값으로 채워 제출해주시면 됩니다.


## 3. 프로젝트 과정
1. EDA

2. 데이터 전처리(Pykospacing, hanspell, soynlp.normalizer모듈 사용)

3. BERT, KoBERT, RoBERTa, Albert, Electra모델을 팀원들끼리 나눠서 돌려봄 

4. 모델 선정 후 학습(Electra)

5. adam, learning rate등 하이퍼 파라미터 조정 후 비교

6. test 데이터에 최적모델을 적용 한 후 sample_submission 파일로 대입시킨 후 제출

## 4. 사용 스택
- 개발 환경
  - Jupyter Notebook
- 기술 및 라이브러리
  - Pytorch, Pandas, BERT, KoBERT, RoBERTa, Electra 

## 5. 배운점
- 자연어처리에서 데이터 전처리를 어떤식으로 해야하는지, 또 어떤걸 적용할 시에 성능이 더 잘 나오는지에 대한 걸 알게되었습니다.

- ICLR 2020에서 구글 리서치 팀이 새로운 pre-training 기법을 적용한 모델인 Electra모델에 대해서 알게 되었고, 기존 BERT나 RoBERT보다 데이터셋이 적을때 성능이 더 잘 나오게 된다는걸 확인하였습니다.

- 하이퍼 파라미터 조정만으로도 성능이 크게 향상이 될 수 있다는 것을 이번 과제를 통해서 더 체감하게 되었습니다.

### 주최
중소벤처기업진흥공단

### 주관
마인즈앤컴퍼니
