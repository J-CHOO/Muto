# 흉부 CT 코로나 감염 여부 분류
흉부 CT 이미지를 이용해 코로나19 감염 여부를 이진 분류하는 과제 (데이터는 저작권상 공개하지 않습니다.)
  - 이어드림스쿨 AI과정 중에 진행한 프로젝트로, [AI connect](https://www.aiconnect.kr/main/competition/detail/204/task/212/assignmentinfo)플랫폼에서 진행한 대회입니다.

## 1. 과제개요
- 흉부 CT 코로나 감염 여부 분류 모델

    - 이미지 영역 | 개방형 문제 | Accuracy



- 문제정의

    - 흉부 CT 이미지를 이용해 코로나19 감염 여부를 이진 분류



- 추진배경

    - 코로나 펜데믹 도래와 장기화에 따른 코로나 확진자 분류 필요성 증대

    - 의료 이미지 AI 기술 적용 가능성 확대



## 2. 데이터 설명
- 문제설명
    - 흉부 CT 이미지를 이용해 코로나19 감염 여부를 이진 분류하는 과제입니다.

    - train.csv에 학습 데이터의 각 타겟값('COVID' 컬럼) 정보가 들어있습니다.

- 제출방법
  - test.zip 내의 sample_submission.csv의 'COVID' 컬럼에 0(비감염) 또는 1(감염) 값을 채워 제출하세요
  - 모든 test 이미지에 대해 값을 채워 제출해야 정상적으로 채점됩니다.

## 3. 프로젝트 과정
Base Line에 대한 이해를 제대로 숙지한뒤, Base Line에서 우리가 할 수 있는걸 최대한 적용하여 점수를 올리는걸 목표로 하였습니다.

1. CNN기반의 여러가지 모델 대입(VGG-16, Resnet, Googlenet, Densenet등) -> Wandb로 accuracy,loss 비교 확인
![image](https://user-images.githubusercontent.com/95010590/156608340-48704635-c74d-497c-b62b-5c90bef23970.png)
![image](https://user-images.githubusercontent.com/95010590/156608416-b08030fd-ba0d-4248-aaf5-7b6e2da99107.png)


2. 모델 선정 후 학습(VGG-16)

3. Albumentation라이브러리를 활용한 이미지 Augmentation 진행(BlUR, CLAHE, Cutout, Resize, Rotate, Tosepia 사용)

4. 학습 향상을 위해 하이퍼파라미터 조정 (Epoch, Early stop, Learning rate, Input_size등 조정)
![image](https://user-images.githubusercontent.com/95010590/156608556-3d61384b-8611-43bb-b628-41100413fb72.png)


5. test 데이터에 최적모델을 적용 한 후 sample_submission 파일로 대입시킨 후 제출

## 4. 사용 스택
- 개발 환경
  - Jupyter Notebook
- 기술 및 라이브러리
  - Python, PyTorch(torchvision), Pandas, Matplotlib, Wandb

## 5. 배운점
- 이론으로만 배웠던 CNN기반의 다양한 모델들을 직접 적용해보면서 각 모델들의 구조에 대해서 파악할 수 있었고, 직접 눈으로 loss나 accuracy가 떨어지는걸 보면서 적합한 모델을 찾을 수 있었습니다.

- 각 모델의 Accuracy와 loss를 바로 그래프로 보면서 비교할 수 있는 Wandb를 처음 사용해보았고, 팀원들과 Wandb를 통해서 서로 돌렸던 모델들을 비교할 수 있었습니다.
![image](https://user-images.githubusercontent.com/95010590/156608124-71d4a751-d7d1-4a3f-8235-0db427a1a67d.png)


- 멘토님의 추천으로 transforms라이브러리가 아닌 Albumentation라이브러리를 통해 더욱 더 다양한 이미지 Augmentation을 할 수 있었고, 이론상으로 속도가 4배가 더 빠르다고 하였는데, 체감으로도 속도가 더 빠르다고 느낄 수 있었습니다.
- Augmentation기법중 Cutout기법(이미지에 일부를 0으로 채워 빈공간을 만듦)에 대해 처음 알게되었고, 직접 사용해보면서 성능향상에 도움이 된다는걸 보았습니다.

- Epoch, Early stop, Learning rate, Input_size등 조정해보면서 딥러닝 모델 성능향상에 중요한 하이퍼파라미터가 무엇인지 알게되었습니다.

### 주최
중소벤처기업진흥공단

### 주관
마인즈앤컴퍼니
