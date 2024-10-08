### 2주차 WIL
1. 문제
이번 주차를 지나며 겪었던 문제가 무엇이었나요?
=> 본격적으로 LLM 기본 원리와 트랜스포머까지의 발전과정을 살펴보면서 다양한 알고리즘과 수식을 이해해야하는 부분이 다소 어려웠습니다. 

2. 시도
문제를 해결하기 위해 어떤 시도를 하셨나요?
=> GPT를 적극 활용했습니다. 수식을 완전히 이해하기 어려운 문과생 출신으로 이해하기 위한 예제들이 필요했는데, gpt를 통해 다양한 예제를 보면서 이해하려 노력했습니다. 

3. 해결
문제를 어떻게 해결하셨나요?
=> gpt가 알려주는 예시를 통해 이해할 수 있었습니다. 예를들어 SGD 방식은 한단계씩 문제를 풀며 나아가는 방식이라면 Adam의 경우 본인이 한번 틀렸던 유형에 대해서 학습한다음 다음에는 해당 문제는 쉽게 해결하고 넘어가기때문에 더 빠르고 효율적으로 학습할 수 있는 방식이라는 부분이 인상적이였습니다. 또한 하단에 정리한 트랜스포머의 계산 순서를 실생활 예시로 빗대어 설명을 gpt가 해주었는데 이부분을 통해 트랜스포머를 좀 더 이해할 수 있었습니다. 

4. 알게된 것
문제를 해결하기 위해 시도하며 새롭게 알게된 것은 무엇인가요?
=> 아직 해결 안된 Ai 문제들이 많이 남아 있다는 것을 알게되었습니다. 예를들어 "사과의 의미로 사과를 구매해서 드렸다"라는 문장에서 사과를 정확히 구분할 수 없다는 사실이 흥미로웠습니다. 이런 부분들이 아직 남아 있다는 것에 한편으론 제가 공부해서 해결할 수 있는 미지의 분야가 있다고 생각하여 공부 의욕이 돋았습니다.

5. 지난 목표 회고
지난 주에 설정해두었던 목표는 달성하셨나요? 잘된 것은 무엇이고 안된 것은 무엇인가요?
=> 최소한 매일 한시간씩은 공부하자고 한 부분을 잘 지키지 못한것 같습니다. 현업과 병행하다보니 여러 변명이 생기는데 이부분을 좀 더 적극적으로 개선해야할 것 같습니다. 

6. 다음 목표 설정
반복적인 성장을 위한 실천 가능한 단기적인 목표를 설정해보세요!
=> 2주차부터는 실제 구현에 가까운 내용들을 배우기 시작한것 같은데, 잘 정리해서 WIL이 아닌 TIL을 남길 수 있도록 공부를 해봐야겠습니다. 

#항해플러스 #항해99


### 딥러닝 이론과 자연어 처리(2)

* 자연어처리 : 순서가 있는 데이터의 처리
* 빈칸에 들어가는 활동이라는 카테고리에 들어가게끔 하려면 (CBOW?) 문장의 컨텍스트에 있음
    * 워드 임베딩 => 비슷한 개념끼리 워딩을 군집화.
* Auto regressive는 진행중에 원 문장의 의미를 잃어버려 결괏값이 기댓값에 못미치는 상황
    * 이걸 해결하려고 teacher forcing을 진행


### 트랜스포머의 계산 순서 및 내용
1. 입력(Inputs)과 입력 임베딩(Input Embedding)
입력: 이건 컴퓨터에게 주는 말이나 글 같은 거예요.
입력 임베딩: 컴퓨터는 글자를 그대로 이해하지 못해요. 그래서 글자를 숫자로 바꿔주는 거예요. 마치 비밀 코드로 바꾸는 것처럼요!
2. 위치 인코딩(Positional Encoding)
글자의 순서가 중요하잖아요. "나는 밥을 먹었다"와 "밥을 나는 먹었다"는 느낌이 달라요. 위치 인코딩은 글자의 순서를 컴퓨터가 기억하도록 도와줘요.
3. 멀티 헤드 어텐션(Multi-Head Attention)
이 부분은 컴퓨터가 중요한 단어를 집중해서 봐요. 예를 들어 "고양이는 귀엽다"라는 문장에서 '고양이'와 '귀엽다'라는 단어에 더 많은 주의를 기울이는 거예요.
4. 정규화와 덧셈(Add & Norm)
컴퓨터가 정보를 처리하다 보면, 너무 많은 정보 때문에 혼란스러울 수 있어요. 이 상자는 정보를 조절해서 컴퓨터가 더 잘 이해할 수 있게 도와줘요.
5. 피드 포워드(Feed Forward)
이 부분은 입력된 정보를 받아서 새로운 정보를 만들어 내요. 마치 문제를 풀어서 답을 내는 것처럼요!
6. 출력 임베딩(Output Embedding)과 위치 인코딩
이건 컴퓨터가 만든 답변을 다시 글자로 바꾸는 과정이에요. 이렇게 컴퓨터가 글을 이해하고 새로운 글을 만드는 과정을 반복하면서 학습해요.
7. 선형(Linear)과 소프트맥스(Softmax)
최종적으로 컴퓨터가 만든 답변을 우리가 이해할 수 있는 형태로 바꿔주고, 가장 가능성이 높은 답변을 선택해요.


### Transformer 에서의 MLP와 SA, CA의 개념
1. MLP (Multi-Layer Perceptron)
MLP는 컴퓨터가 복잡한 문제를 푸는 데 도움을 주는 일련의 계산 층이에요. MLP는 여러 개의 **피드 포워드 층(Feed Forward Layers)**으로 구성되어 있어서, 각 층은 입력받은 정보를 받아서 새로운 정보를 계산해내요. 이 과정에서 문제의 답을 점점 더 잘 찾아가는 거예요.

2. 셀프 어텐션(Self-Attention)
셀프 어텐션은 트랜스포머 모델에서 매우 중요한 부분이에요. 이 기술은 문장 내의 각 단어가 서로 얼마나 관련이 있는지를 컴퓨터가 파악하도록 도와줘요. 예를 들어, "고양이는 귀엽다"라는 문장에서 '고양이'와 '귀엽다'는 서로 강하게 연관되어 있어요. 셀프 어텐션은 이런 연관성을 수치로 나타내어 컴퓨터가 어떤 단어에 더 주의를 기울여야 할지를 알 수 있게 해줘요.

3. 크로스 어텐션(Cross-Attention)
크로스 어텐션은 트랜스포머의 다른 부분에서 사용되며, 특히 번역과 같은 작업에서 중요해요. 여기서는 원문의 단어와 번역할 단어 사이의 관계를 찾아내는 데 사용돼요. 예를 들어, 영어 문장을 한국어로 번역할 때, 각 영어 단어가 한국어 단어와 어떻게 연결되어야 할지를 컴퓨터가 이해하도록 도와주죠.

이 도식의 설명에 이 개념들을 적용하면:
입력 임베딩과 위치 인코딩은 문장을 숫자로 변환하고 그 순서를 기록하는 초기 단계예요.
멀티 헤드 셀프 어텐션은 문장 내에서 각 단어들 사이의 관계를 평가하여 중요한 단어에 더 많은 주의를 기울이게 해줘요.
Add & Norm과 MLP는 계산된 정보를 바탕으로 문제의 답을 점점 더 잘 찾아갈 수 있도록 도와주는 계산 과정을 거칩니다.
**선형(Linear) 층과 소프트맥스(Softmax)**는 최종적으로 가장 가능성 있는 답을 선택하여 우리가 이해할 수 있는 형태로 출력해줘요.

### Transformer에서의 Matmul과 SoftMax
1. MatMul (Matrix Multiplication, 행렬 곱셈)
MatMul은 행렬 곱셈을 의미해요. 행렬 곱셈은 수학에서 두 행렬을 서로 곱하는 연산을 말하죠. 컴퓨터 과학과 인공 지능에서, 행렬 곱셈은 데이터를 변환하고 합성하는 데 아주 중요한 도구예요.

셀프 어텐션에서의 역할:
셀프 어텐션에서 MatMul은 입력된 문장의 모든 단어들의 임베딩 벡터에 대해 **가중치 행렬(weight matrices)**을 곱해 새로운 행렬을 만듭니다. 이 가중치 행렬은 Query, Key, Value라는 세 가지로 구분되는데, 각각의 단어에 대해 이 가중치를 곱하여 쿼리 행렬(Query matrix), 키 행렬(Key matrix), 값 행렬(Value matrix)을 생성합니다.
이 과정을 통해 각 단어의 새로운 표현을 얻어, 단어들 사이의 관계를 더 잘 이해할 수 있게 해줍니다.
2. Softmax
Softmax는 입력받은 값을 확률로 변환해주는 함수예요. 각 입력값에 대해 **지수(exp)**를 계산하고, 모든 지수값의 합으로 각각을 나눠줘요. 이렇게 하면 결과값은 모두 0과 1 사이의 값이 되며, 모든 결과값의 합은 1이 됩니다.

셀프 어텐션에서의 역할:
셀프 어텐션에서 Softmax는 키(Key)와 쿼리(Query)의 행렬 곱셈 결과(점수)에 적용되어, 어떤 단어들이 다른 단어에 대해 가지는 중요도를 확률로 나타냅니다.
즉, 각 단어가 다른 단어에 얼마나 주목해야 할지를 결정하는 데 사용됩니다. 이렇게 계산된 확률을 바탕으로, 각 단어에 대한 Value 벡터들의 가중합을 구하여 최종적인 셀프 어텐션 출력을 만들어냅니다.
셀프 어텐션에서의 과정 요약:
**임베딩 벡터에 대한 행렬 곱셈(MatMul)**을 수행하여 Query, Key, Value 행렬을 만듭니다.
Query와 Key 행렬의 곱을 통해 각 단어 조합의 상호 작용 점수를 계산합니다.
계산된 점수에 Softmax 함수를 적용하여, 각 단어가 문장 내 다른 단어에 주는 주목도를 확률로 변환합니다.
이 확률을 사용하여 각 단어의 Value 벡터들을 가중합하여, 각 단어의 새로운 표현인 셀프 어텐션 결과를 얻습니다.



### 지난 과제 피드백

nn.fn 에서 어떤 곳은 numpy 어떤고은 또 다른 패키지를 사용하는데, 성능은 비슷한다. activation 함수가 어떤건지가 중요.
ex) nn.sigmoid(), nn.RELU()


### SGD와 ADAM의 차이
1. SGD(확률적 경사 하강법, Stochastic Gradient Descent)
SGD는 모델이 공부할 때 한 번에 하나씩 데이터를 사용해서 학습하는 방식이에요. 마치 시험을 본 후 틀린 문제에 대해 즉시 피드백을 받고, 그 피드백을 반영해서 계속 공부하는 것과 같아요. 즉, 매번 하나의 문제에 대해 잘못된 점을 고치면서 조금씩 학습해 나가죠.

예시:
상상해보세요. 당신이 100개의 수학 문제를 풀고 있어요. SGD는 문제 하나를 풀고 틀리면, 그 문제에 대한 피드백을 즉시 받고, 그것을 반영해 다음 문제로 넘어가요. 그래서 매번 조금씩 고쳐나가는 과정이에요.
SGD의 단점:
때때로 피드백이 너무 작거나, 너무 급격하게 변할 수 있어요. 그래서 더 빠르게 학습할 수 있는 기회를 놓칠 때가 많아요.
경사가 급격하게 변하는 구간에서는 오히려 잘못된 방향으로 학습할 수도 있죠.
2. Adam(Adaptive Moment Estimation)
Adam은 SGD보다 똑똑한 방식으로 학습해요. 각각의 변수가 어떻게 변하는지에 대한 정보를 기억하고, 이를 바탕으로 더 나은 학습을 진행해요. 이를 위해 두 가지 중요한 개념을 사용해요:

이동 평균: 학습이 진행되는 동안 이전 단계에서의 변화를 기억하고, 그 정보를 바탕으로 더 적합한 방향으로 나아가요.
변동성 측정: 학습 속도를 변화시키는 방법을 사용해서, 많이 변동하는 구간에서는 학습 속도를 줄이고, 적게 변동하는 구간에서는 속도를 높여요.
예시:
다시 수학 문제를 풀고 있다고 생각해보세요. Adam은 이전 문제들에서 틀린 문제들의 패턴을 기억해서, 더 효과적으로 공부해요. 예를 들어, 당신이 특정 유형의 문제에서 자주 틀린다면, 그 문제 유형에 대해 더 많이 신경 쓰고 공부하는 방식이에요. 또한, 틀릴 때마다 공부 속도를 자동으로 조정해서, 더 빨리 배워야 할 때는 빨리 배우고, 천천히 해야 할 때는 천천히 진행해요.
Adam의 장점:
빠른 학습: Adam은 학습 속도를 조절할 수 있기 때문에 빠르고 안정적인 학습이 가능해요.
더 안정적인 결과: SGD보다 더 적은 변동성으로 안정적으로 학습해 나가요. 그래서 결과가 더 정확하게 나오는 경우가 많아요.
자동으로 조정: Adam은 변수마다 학습 속도를 다르게 조정하기 때문에, 학습을 일일이 손으로 조절하지 않아도 되는 편리함이 있어요.
비교 요약:
SGD: 문제를 하나씩 풀면서 즉시 피드백을 반영하는 방식. 다만 속도가 일정하고, 더 똑똑하게 학습하지는 않음.
Adam: 이전의 학습 패턴을 기억하고, 학습 속도를 조정하면서 더 빠르고 정확하게 공부하는 방식. 복잡한 문제일수록 더 나은 성과를 냄.
왜 Adam이 더 나은가?
Adam은 학습 속도를 자동으로 조정하고, 과거의 변화를 기억하면서 효율적으로 학습하기 때문에, SGD보다 더 빠르고 안정적으로 좋은 결과를 낼 수 있어요. 특히 데이터가 크거나 복잡한 문제일 때, Adam은 훨씬 더 효율적이에요.