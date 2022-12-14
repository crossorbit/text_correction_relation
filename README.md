# Text Correction - fastText 활용한 OCR 오인식 보안 
  
## 목적
- 주민등록증, 가족관계증명서 등 행정서류에서 관계(본인/자녀 등)를 추출하여 OCR 변환 시, 오인식으로 잘못된 관계정보 처리될 수 있음(e.g. 몬인, 지녀 등)
- 관계와 관련된 단어를 fastText 통해 학습하여 **사전에 등록된 단어로 변환**하여 정확도 향상

## 활용 기술/라이브러리 - fastText
- 페이스북에서 word2vec(구글)의 단점을 보완하면서 만들어낸 알고리즘
- 문장 속 단어들의 조합으로 워드 임베딩을 하며, 이에 따라 학습에 사용된 적이 없는 단어에 대해서도 단어 벡터를 만들 수 있음
- 형태학적 측면의 유사성 판단 가능  
  &rarr; **의미가 아닌 형태의 유사성만 판단하기 위해 fastText 활용** 

## 적용 내용
- 모델 학습 위한 말뭉치의 경우, 단어+자모 형태로 구성하여 형태 유사성 판단 강화(자모 추가 여부에 따라 미세하게 차이남)
- 유사도 평가 시 단어-단어 비교 보다는 **자모분리한 단어와 자모분리한 단어를 비교**하면 원하는 결과 얻을 수 있음

## 결과
<img width="659" alt="스크린샷 2022-09-01 오후 4 30 46" src="https://user-images.githubusercontent.com/54519026/187857591-7e8388f4-d238-40b3-b13a-f5be8f180025.png">
