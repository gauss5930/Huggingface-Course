# 2. USING 🤗 TRANSFORMERS

Chapter 1. 에서 봤던 것처럼, Transformer model은 보통 매우 크다. 
수많은 파라미터와 덕분에, 모델을 학습시키는 것과 적용하는 것은 매우 복잡하다.
게다가, 날이 지남에 따라 우후죽순 나오는 새로운 모델들을 모두 시도해보는 것은 쉽지 않다.

🤗 Transformer 라이브러리는 이러한 문제를 해결하기 위해 만들어졌다. 
Hugging Face의 목표는 하나의 API로 모든 Transformer 모델을 불러오고, 학습시키고, 저장하는 것이다.
라이브러리의 주 특징은 다음과 같다.

- **사용하기 쉬움**: NLP SOTA 모델을 다운받고, 불러와서 사용하는 것이 오직 두 줄의 코드면 끝난다!
- **가용성**: code를 살펴보면, 모든 모델이 Pytorch의 'nn.Module'이거나, TensorFlow의 'tf.keras.Model'의 클래스이고, 각각 ML 프레임워크처럼 다루어진다.
- **간편함**: 많은 복잡한 개념들이 지나다니지만, 가장 핵심이 되는 컨셉은 'All in one file'이다. 모델의 forward pass가 완전히 하나의 파일로 정의된다

