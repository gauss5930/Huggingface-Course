# 3. FINE-TUNING A PRETRAINED MODEL

Chapter 2.에서 tokenizer와 pre-trained model을 사용하여 예측을 진행하는 방법에 대해 알아보았다.
하지만, 만약 자기 자신의 데이터셋에 대해 pre-trained model을 fine-tune하려면 어떻게 해야 할까?
그것이 바로 이번 챕터의 주제이다! 이번 챕터에서 배우게 될 내용들은 다음과 같다.

- Hub에서 대규모 데이터셋 불러오기 💾
- high-level Trainer API를 사용해서 model fine-tune 하기 🖥️
- custom training loop 사용해보기 😉
- 어떠한 셋팅에서도 손쉽게 custom training loop를 실행할 수 있는 🤗 Accelerate 라이브러리 leverage 해보기 🔥
