# Transformer는 어떻게 작동할까?

이 절에서는 Transformer model의 architecture에 더욱 자세하게 들여다보았다.

### Transformer의 역사

다음의 그림은 Transformer model에 대한 간략한 역사를 보여준다. 
Transformer architecture는 2017년에 소개된 모델로 다음과 같은 후속 모델들의 베이스가 되었다.

![transformer 역사](https://user-images.githubusercontent.com/80087878/217529621-30047b8c-2558-41eb-b45c-5c7126b0521b.svg)

수많은 모델들이 존재하는데, 이를 좀 더 이해하기 쉽게 널리 사용되는 3가지 카테고리로 분류하면 다음과 같이 표현할 수 있다.

- GPT기반 or *auto-regressive* Transformer model
- BERT기반 or *auto-encoding* Transformer model
- BART/T5기반 or *seq-to-seq* Transformer model

### Transformer는 Language Model이다!

위에 언급한 모든 Transformer model은 *language model*로 학습되었다. 
이는 이들이 비지도학습 방식으로 거대한 양의 raw text로부터 학습되었다는 것을 의미한다.

이러한 방식으로 학습된 모델은 언어에 대해 통계학적 이해는 발전시키지만, 특정한 실용적인 task에 대해서는 그리 유용하지 않다.
그래서, 일반적인 pre-trained model은 *transfer learning*이라는 과정을 거치게 된다. 
이 과정 중에는 모델이 사람의 라벨을 이용하여 지도 학습 방식으로 주어진 task에 대해 fine-tuned된다.

이에 대한 예시로는 이전의 n개의 단어와 현재 단어를 이용하여 문장에 다음으로 나오게 될 단어를 예측하는 task가 있다.
이러한 방식을 *casual language modeling*이라고 하는데, 왜냐하면 출력이 미래가 아닌 과거와 현재의 입력에 의해 결정되기 때문이다.
다음의 그림은 *casual language modeling*의 예시이다.

![casual language modeling](https://user-images.githubusercontent.com/80087878/217532902-78b48ec1-3621-40fd-9d86-d42194be0fcc.svg)

또다른 예시로는 *masked language modeling*이 있다. 
이 방식은 모델이 문장의 중간에 mask가 씌워진 단어를 예측하는 방식으로 작동한다.
다음의 그림은 *masked language modeling*의 예시이다.

![masked language modeling](https://user-images.githubusercontent.com/80087878/217533225-819f1eae-ec2f-41de-b233-bae5a721a481.svg)

### Transformer는 거대한 모델!

특별한 케이스인 DistilBERT를 제외하면, 좋은 성능을 얻기 위한 일반적인 전략은 pre-trained하는 데이터의 양 뿐만 아니라, 모델의 크기를 키우는 것이다.
하지만, 이렇게 모델의 크기를 늘리고, 더 많은 양의 데이터를 요구로 하는 것은 엄청난 양의 자원을 요구한다. 

따라서 이렇게 거대한 모델을 사용할 때, 처음부터 다시 만들어서 사용하는 것은 너무 많은 자원을 요구로 한다.
이러한 불상사를 막기 위해 다음과 같은 방법이 제안되었고, 실제로도 많이 사용된다.

### Transfer Learning

