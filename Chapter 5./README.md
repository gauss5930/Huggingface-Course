# 5. THE 🤗 DATASETS LIBRARY

Chapter 3. 에서 🤗 Dataset 라이브러리에 대해 맛을 봤고, 이를 사용해서 model을 fine-tuning 하는데 다음과 같은 3개의 주요한 스텝이 있다는 것을 알았다.

1. Hugging Face Hub에서 데이터셋 불러오기
2. Dataset.map()을 사용하여 데이터 전처리
3. metrics를 불러와서 계산하기

하지만, 이것은 🤗 Dataset 라이브러리가 할 수 있는 일의 빙산의 일각에 불과하다!
이번 챕터에서는 이 라이브러리에 대해서 깊숙히 들어가보도록 하겠다.
이번 챕터를 학습하고 나면, 다음의 질문에 대답할 수 있을 것이다.

- 데이터셋 슬라이싱과 다이싱을 어떻게 해야 할까?
- 데이터셋이 너무 커서 RAM의 허용량을 초과할 때 어떻게 해야 할까?
- memory mapping과 Apache Arrow는 무엇일까?

이번 챕터에서 배울 내용은 Chapter 6. 과 Chapter 7. 에서 고급 tokenization과 fine-tuning 작업의 밑거름이 된다.
