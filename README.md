# AI_theory

[1. Entropy](#Entropy)  
[1.1 Cross Entropy](#Cross Entropy)

# Entropy
사디 카르노  
산업혁명 시대 증기기관 발명  
"열은 일을 할 수 있다."  
"열은 일로 전환되어 일을 한 뒤 완전히 보존되어 열로 다시 나온다." (칼로릭 보존)  
"열은 높은 곳에서 낮은 곳으로 이동한다."  

제임스 줄  
아니다. "에너지 보존 법칙에 의해 열은 일로 전환된 만큼 소모되어 줄어든다."  
  
윌리엄 톰슨  
그런데 "왜 열은 높은 곳에서 낮은 곳으로 이동하나?"  
"카르노 엔진의 예를 들자면 아무리 이상적인 열기관을 만들더라도 열효율이 결코 100%가 되지 않으며 어떻게든 낭비되는 열량이 있다."  
"즉, 가만히 있던 분자가 어떤 한곳으로 이동해 한 물체를 밀어내는 일은 없으며 수면의 물이 갑자기 한곳이 솟아 오르는 경우는 없다. 고로 열은 항상 감소 하는 방향으로 움직인다."  

루돌프 클라우지우스  
그렇다면 "열은 높은 곳에서 낮은 곳으로 이동하나 에너지 보존 법칙에 의해 열은 일로 전환된 만큼 소모되어 줄어든다. 이를 엔트로피라 하자!!"  
예> Th: 뜨거운 돌의 온도, Tc: 찬물의 온도  
돌을 물에 떨어 뜨리면 엔트로피는?  
S = Q{(1/Tc) - (1/Th)}  
Th>Tc 므로 엔트로피 s>0  
즉, 엔트로피는 항상 증가하는 방향으로 이동한다.  

루트비히 볼츠만  
"너희들의 주장에 따르면 기체 평균 분자 운동 에너지는 온도에 비례 하는군"  
"하지만 이는 거시적 상태(눈에 보이는)에서의 이상적 논리이고 미시적 상태(눈에 보이지 않는)에는 분자는 무질서하게 운동하므로 충돌 등과 같이 보다 복잡한 에너지 관계를 갖는다."  
"즉, 미시적 상태의 통계적 결과가 거시적 상태가 되는 것이다."  
하지만 당시 원자론은 증명되지 못 했고 확률통계는 신을 모독하는 죄로 해당 이론은 무시당함 그리고 자살  
추후 아인슈타인이 원자론 증명 그래서 죽은 후에야 인정 받은 이론   

# S = klogW (볼츠만 엔트로피)  
S: 엔트로피  
k: 볼츠만 상수  
W: 미시적 상태에 원자가 가질수 있는 배열의 수  
증명>  
N: 에너지를 가진 원자수  
a~k개의 뽑는 경우가 있다 가정  
W = {N!/((Na!)x(N-Na)!)} x {(N-Na)!/((Nb!)x(N-Na-Nb)!)} x ....... x {(N-...-Nl)!/((Nk!)x(N-...-Nl-Nk)!)} -> 순열  
W = {N!/((N!Na!...Nk!)x(N-Na-....-Nk)!)}  
N-Na-Nb-.....-Nk = 0 -> 0! = 1  
W = N!product(1/Nk!)  
S = klogW에 대입  
S = klog(N!product(1/Nk!)) = (k){log(N!) - sigma(log(Nk))}  

# 클로드 섀넌
"그럼, 볼츠만의 이론으로 정보량의 표현이 가능하겠네"  
How? -> bit 개념 도입 (0과 1로 표현한다.)  
"정보이론에 있어서 엔트로피란 무질서한 정보량을 표현하기 위해 사용되는 최소한의 자원량 이다."  
예를 들어 보자  
연인과의 카톡을 할떄 대화 정보를 표현해야된다. 가정하자  
하트와 욕설이 있다하면 어느 것을 더 많이 쓰겠는가? (일반적으로)  
당연히 하트가 많을것이다. 그렇다면 하트를 1bit로 표현하고 욕설을 4bit로 표현하면 정보를 표현하는데 있어서 효율적이다.  
즉, 발생 빈도수가 높은 것을 낮은 bit를 사용하고 낮은 빈도수를 높은 bit를 사용  
때문에 y=-logx 그래프를 가질것 이다.  
좀 더 직관적으로 해석해보자  
2^k = W -> (k는 W 경우의 수를 표현하기 위한 최소한의 자원량)  
k = -lgW -> (k > 0 이며 W = 0 ~ 1)  

# k = -lgW  
여기서 k는 확률값으로 자연에 존재하는 사전은 무수히 발생되므로 기대값으로 구한다.  
"기대값은 각 원소 값에 각 확률을 곱한 값의 합"  
왜 기대값을 구해야 하나?  
주사위를 한번 던진 결과를 가지고 그 결과를 주사위가 준 일반적인 결과라 할 수 없다.  
어쩌다 처음에 숫자가 높을 수도 있고, 때로는 낮을 수도 있기 때문이다.  
따라서 여러번 시행하여 그에 대한 평균으로 비교해야 하기 때문에 기대값이 활용된다.  
# E[k] = -sigma(q(x)lgq(x)) 


# Cross Entropy
우리는 실제 데이터의 분포 q(x)를 모른다. 이때 모델링(딥러닝, 머신러닝,...)으로 예측한 분포 p(x)를 통해 q(x)를 구해야된다.  
이때 쓰이는 것이 loss function 중 하나인 Cross Entropy  
# E[p,q] = -sigma(q(x)lgp(x))
왜 저  공식인가? -> Cross Entropy를 최소화 하는 것은 log likelihood를 최대화 하는 것과 같다.  
확률(Probability) : 어떤 시행에서 특정 결과(sample)가 나올 가능성. 즉, 시행 전 모든 경우의 수의 가능성은 정해져 있으며 그 총합은 1(100%)이다.  
우도(가능도, Likelihood) : 어떤 시행을 충분히 수행한 뒤 그 결과(sample)를 토대로 경우의 수의 가능성을 도출하는 것  
예를 들어 보자 주사위 한개를 던저서 1이 나올 확률은 1/6이다. (즉 모델과 추정치로 부터 데이터를 구하는) 
하지만 실제로 던지게 되면 1/6로 1이 나온다는 보장은 없다. 계속 시행해서 1/6확률이 나오는 분포를 찾아야된다. 이것이 likelihood이다. (즉 데이터로 부터 정확한 모델과 추정치를 찾는)  
그렇다면 왜 Maximum Likelihood Estimation을 사용하는가? 데이터를 잘 설명하는 것이 likelihood가 높다.  
그렇다면 왜 Cross Entropy를 최소화 하는 것은 log likelihood를 최대화 하는 것인가?  
likelihood의 공식은 p(x|y) = product(p(x|y))  
최대값을 구하기 위해 편미분을 해서 0이 되는 y값을 찾자 -> d/dy{p(x|y)} = 0  
편미분을 할려고하니 product는 곱집합이라 계산이 어렵다. 그래서 로그와 음수를 취해서 최소값을 찾자  
-lg(p(x|y)) = -lg(product(p(x|y)) = -sigma(lg(p(x|y)))  
d/dy{-sigma(lg(p(x|y)))} = 0 -> 이제 이렇게 유도 해보면 Cross Entropy와 동일하다.  
즉, log likelihood를 최대화는 likelihood에 로그과 음수를 취해 최소를 구하는 것이고 이는 Cross Entropy 최소 구하는 것과 동일하다.

# 베이즈 정리
"토마스 베이즈에 의해 최초로 서술된 정리"  
P(A|B) = {{P(B|A)P(A)} / P(B)}  
"어떤 사건이 만들어 놓은 상황에서, 그 사건이 일어난 후 앞으로 일어나게 될 다른 사건의 가능성을 구하는 것"  
셜록홈즈의 명대사 "설령 믿어지지 않는다고 해도, 가능성을 제외하고 남는 게 진짜 범인이다"  
Q> 간단한 게임을 해보자  
당신은 게임에 참가했고 해당 게임은 3개의 문이 있다. 문 뒤에는 차가 한대 염소가 두마리 있다. 쇼 진행자는 하나의 문을 선택하라 하고 문 뒤에 것을 주겠다고 한다.  
단 쇼 진행자는 무엇이 어디에 있는다 알고 있다. 자 이때 당신은 하나를 선택했고 쇼 진행자는 염소가 있는 문을 먼저 하나 보여줬다. 그리고 당신에게 다시 질문한다.  
기회를 한번 더 줄테니 선택을 바꿀텐가?  
그럼 당신은 선택을 바꾸는게 유리 할까 안 바꾸는게 유리할까?  
sol>  
정답은 바꾸는게 유리하다. 왜?  
처음 당신은 아무것도 모르는 상태에서 선택하여 차를 얻을 확률은 33.3%이다. 하지만 쇼 진행자가 염소를 하나 보여 주였다. 그럼 이제 변수는 달라진다. 하나가 배제 되었으니 66.6%가 되는 것이다. 그러니 당연히 저에게 33.3%의 확률을 더 주셔서 감사합니다. 하고 바꾸어야 된다.  
이를 베이즈 정리와 같이 적용해보자.  
당신이 1번 문을 선택한 경우 진행자가 3번문을 열었을 때 자동차가 1번 문에 있을 확률 : 1/3 -> P(car1|select3) : 조건부 확률  
P(car1|select3) = P(select3|car1)P(car1) / P(select3) = 1/3  
P(select3|car1) = 1/2  
P(car1) = 1/3  
P(select3) = 1/2  
그럼 이제 3번 문을 열었습니다. 이때 자동차가 2번 문에 있을 확률 : 2/3 -> P(car2|select3) : 조건부 확률  
P(car2|select3) = P(select3|car2)P(car2) / P(select3) = 2/3  
P(select3|car2) = 1 -> 당신이 1번을 선택했기 때문에 2번에 차가 있으면 결국 3번 밖에 열수없다  
P(car2) = 1/3  
P(select3) = 1/2  
이는 AI의 추론에 큰 도움이 된다. 데이터가 많으면 많을수록 올바른 추론에 도달한다. 즉 사전 확률을 지속적 업데이트 하면은 성능은 올라간다.  
Q> 넷플릭스는 돈을 어떻게 벌까요?  
바로 추천 시스템 -> 다양한 알고리즘이 있지만 가장 기본인 naive bayes  
처음 가압한 사람은 무엇을 좋아하는지 넷플리스는 알지 못 한다. 이를 cold start라 한다. 때문에 무엇을 보든 그것을 좋아할 확률을 50% 싫어할 확률도 50%으로 가정한다.  
여기서 해당 콘텐츠를 좋아할 확률 50%를 사전 확률이라 한다. 시간이 지나고 총 과련 콘텐츠를 10편을 보았다.  
예를들어 관련 콘테츠를 영화라 하자 그리고 10편 중 5편을 좋아요를 눌렀고 그중 3편은 액션장르였다 즉, 좋아하는 영화 중 60%가 액션이다.  
그리고 나머지 5편은 싫어요 인데 이중 액션은 1편이 였다. 즉 싫어하는 영화 중 20%가 액션이다.  
초기에 좋고 싫은 확률을 50%(사전확률)로 두었다. 그럼 베이즈 이론에 의해 액션영화 중 좋아요를 누를 확률은 0.75 = 0.3/((0.5x0.6)+(0.5x0.2))  
이제 사전확률을 75%(사후확률)로 업데이트 할 수 있습니다. 그러니 넷플릭스는 액션영화를 더 많이 노출 시킬것입니다.  
시간이 지나 시청자는 넷플리스에게 정보를 제공했다고 가정하자  
10편의 액션영화를 더 보고 이중 좋아요는 5편인데 그중 4편에 라이언 레이놀즈가 나왔다. 좋아하는 영화에 라이언 레이놀즈가 나올 확률 80%  
싫어요 5편 중 1편만이 라이언 레이놀즈가 나왔다. 싫어하는 영화에 라이언 레이놀즈가 나올 확률 20%  
그렇다면 라이언 레이놀즈가 나온다면 그 영화를 얼마나 좋아할까? 그 확률은?  
베이즈에 따라 구하면 이미 사전에 액션영화를 좋아할 확률을 75%로 업데이트 했다. 그러므로 75:25의 비율에서 계산하자  
(0.75x0.8)/(0.75x0.8)+(0.25x0.2) = 0.6/0.65 = 0.923 -> 92.3% 그럼 이 정보를 가지고 그 사람은 라이언 레이놀즈가 나오는 액션 영화에 노출시키면 좋을것이다.  
<img width="429" alt="캡처" src="https://user-images.githubusercontent.com/50193583/171524543-47f16a96-6adb-471a-b993-b1a6cc1ab7a8.PNG">  
<img width="310" alt="1" src="https://user-images.githubusercontent.com/50193583/171524532-77a578a4-1546-4733-9658-a3d28864ac4f.PNG"> 

# Kullback–Leibler divergence (KL - Divergence)
내가 모델링하여 추론한 엔트로피와 정확하게 모델링한 엔트로피 간의 오차율(cost)  
KL Divergence = cross entropy - entropy 여기서 entropy는 사실의 고정 값이므로 오차율(cost)를 최소로하는 것은 cross entropy를 최소화하는 것이다.  
KL Divergence = E[p,q] - E[k] = (-sigma(q(x)lgp(x))) - (-sigma(q(x)lgq(x))) = -sigma{q(x)lg(p(x)/q(x))} -> 예측 모델링 모양만 다르지 결국 Cross Entropy와 동일  

# Mutual Information
KL Divergence는 나의 모델링과 실제 모델링 간의 오차율(error)를 찾는 것이면 Mutual Information는 반대로 둘이 얼마나 비슷한지를 찾는 척도 이다.  
두 개의 확률변수 x, y가 있다.  
Mutual Information = sigma{p(x,y)log(p(x,y)/p(x)p(y))}  
만약 두 확률변수가 독립이면 p(x,y) = p(x)p(y) 성립하므로 log1 = 0 따라서 Mutual Information = 0

# 그 외 loss function

1. MSE(Mean Squared Error)  
MSE가 크다는 것은 데이터와 평균 사이에 차이가 크다는 것이고, MSE가 작다는 것은 데이터와 평균 사이의 차이가 작다는 것을 알 수 있어요. 즉 데이터가 평균으로부터 떨어진 정도를 표현한 것이다  
MSE = 1/N(sigma{(q(x)-p(x))^2}) -> 실제값과 예측값의 차이를 제곱하여 평균을 구함  
이는 neural network 보다는 regression에 많이 쓰임  
2. RMSE(Root Mean Squared Error)  
MSE에 루트(√)를 씌운 것으로 MSE와 기본적으로 동일하다. MSE 값은 오류의 제곱을 구하기 때문에 실제 오류 평균보다 더 커지는 특성이 있어 MSE에 루트를 씌운 RMSE 은 값의 왜곡을 줄여준다.  
  
더 많은 손실함수가 존재하지만 기본적으로는 위의것들이 많이 쓰인다. 이 외에는 솔직히 상황에 맞는 손실 함수를 직접 만드는 경우가 많다.  

# 신경망 (Neural network)
신경망의 시작은 알렉산더 베인과 윌리엄 제임스가 시작이다.베인은 인간의 뇌의 뉴런 간의 연결이 반복되면서 기억의 형성으로 이어진다고 말했다. 제임스는 베인 이론과 유사 했지만 기억과 행동은 뇌의 뉴런 사이에 흐르는 전류에서 비롯된다고 제안했다. 그리고 찰스 셰링턴은 제임스 이론은 실험하기 위해 쥐의 척수에 전류를 흐르게 했습니다. 제임스가 예측한 대로 전류의 증가를 보여주는 대신 테스트가 시간이 지남에 따라 전류 강도가 감소한다. 당시는 1890년대 이다.  
1940년대에 맥컬로크와 피츠가 수학적으로 신경망 모델을 만들었고 도널드 헵이 최초의 학습 알고리즘을 제안했다.  
1950년대에 프랭크 로젠블릿은 단순 덧셈과 뺄셈을 사용하는 2계층 학습 알고리즘인 퍼셉트론은 발표한다.  
1970년대에 마빈 민스키와 시모어 페퍼트가 퍼셉트론의 2개 문제점을 제기한다. 첫번째 XOR문제를 처리할 수 없다. 두번째 당시 컴퓨터가 대규모 신경망을 처리하기에는 정교하지 않다.  
이후 신경망은 암흑기이다. 인기가 없어져 아무도 연구하지 않았다.(미국방부 2천만달러 연구자금 지원 중단)  
2000년대 들어서 힐튼 교수가 MLP(Multilayer Perceptron)과 Backpropagation을 제안하면서 다시 신경망 연구가 부활한다. 솔직히 Backpropagation 이론은 1970년에 폴 웨어보스가 먼저 발표했다. 하지만 퍼셉트론에 적용하여 상세히 문제점을 해결할 생각은 못 했다.  
그리고 얀 르쿤 교수는 MLP와 Backpropagation과 Convolution을 결합하여 최초의 MNIST 테스트를 발표한다. 이것이 LeNet-5 라는 최초의 CNN(convolution neural network)이다.  
뭐 힐튼 교수와 르쿤 교수 이외에도 문제점은 해결할려고 많이들 노력했지만 예를 들면 SVM같은 하지만 그렇게 효과는 못 봐서 지금은 그냥 않쓴다. 안되는 건 아니다. 학습 속도가 느리다 그래서 구지 CNN이 있는데 SVM를 쓸 이유가 없어짐  

# Perceptron
로젠블릿이 제안한 이론  
신경망 중 가장 간단한 형태 (입력과 가중치, activation function만 사용)  
![Perceptrons](https://user-images.githubusercontent.com/50193583/171540098-7cbaff7d-ae36-48f2-92ca-26ef61f18ab8.jpeg)
  
학습 진행 과정  
1. 가중치 초기값 설정(0~1, small random value)
2. 학습 데이터 = [x1,x2,x3,.....,xj], activation function = f(x), theta : 임계값
3. y_j = f{ sigma{wj * xj} - theta } -> 출력값
4. e = (y_o - y_j) -> 오류값 = 실제값 - 예측값
5. 오류가 0이 아닌 경우 가중치 업데이트 0이면 업데이트 안함
6. w_j+1 = w_j + learning_rate * xj * e

# Multilayer Perceptron(MLP) = Fully Connected layer(FC) = Dense layer
힐튼이 제안한 이론 당시 1985년 논문에는 error propagation이라고 썼다.  
Perceptron이 비선형 데이터를 추론 못하는 문제를 해결함  
입력층과 출력층 사이에 하나 이상의 히든층이 존재하는 신경망 그리고 학습을 위해 backpropagetion 적용  
지금은 Multilayer perceptron를 fully connected layer(FC)이라고 부른다. 그리고 Dense layer 라고도 한다.  
(솔직히 불만임 왜 MLP라고 하면 될것을 FC라고 했다 다시 Dense라고 했다 말을 바꿀까? 괜히 사람 헷갈리게 구글이 처음 tensorflow 만들면서 이렇게 이름을 바꿔서 라이브러리를 만들다보니 어쩔수없지만 ..... 대기업의 힘이구만 ㅠㅠ;)  
playground.tensorflow.org  -> MLP 실험 사이트 해보세요 재밌어요  
![week4_0300](https://user-images.githubusercontent.com/50193583/171559738-f4da0b71-5914-433c-b037-0120edcac57c.png)
  
학습 진행 과정(feedforward network, backpropagation)  
feedforward network : 결과 값을 예측하는 과정  
1. 가중치 초기값 설정(-0.3 ~ 0.3, small random value)
2. 학습 데이터 = [x1,x2,x3,.....,xj], activation function = f(x), theta : 임계값
3. y_j = f{ sigma{wj * xj} - theta } -> 해당 계산은 생성 은닉층 만큼 진행
4. e = (y_o - y_j) -> 오류값 = 실제값 - 예측값(마지막 출력값) -> 실제는 단순 차이값이 아닌 loss function을 이용
  
backpropagation : 결과값과 실제값의 오류률을 계산하여 가중치를 다시 업데이트하는 과정
1. 출력에서 마지막 은닉 가중치 업데이트 (오류가 0이 아닌 경우 가중치 업데이트 0이면 업데이트 안함)
2. delta = 출력값 * (1-출력값) * e 
3. w_j+1 = w_j + learning_rate * xj * delta
4. 은닉에서 은닉 가중치 업데이트
5. delta = 해당_출력값 * (1-해당_출력값) * 이전_delta * 이전_weight
6. w_j+1 = w_j + learning_rate * xj * delta
7. 이를 입력까지 계속 반복
8. 그후 다시 feedforward network 진행 오류 다시 계산 오류가 0에 가까워 질때까지 진행

# 이제 실제 딥러닝이라고 불리며 사용하고있는 방법 들에 대해 논의

# Loss Function (손실 함수)
손실함수는 위에서 설명한 봐가 있다.  
Cross Entropy가 이에 헤당한다. 정확히는 KL-Divergence  
Calssification에서 Cross Entropy가 많이 쓰이고 Regression에서는 MSE가 쓰인다.  
그 외에도 종류는 천차만별이다.

# Optimization Function (최적화 함수)
손실함수의 결과값을 최소화하는 함수이다. 즉 오류률을 줄이기 위한 가중치 업데이트 방법을 말한다.  
처음 MLP의 backpropagation에서 가중치 업데이트는 단순히 delta값을 구하는 방법은 perceptron rule의 기반이다.  
하지만 비선형에는 쓸수없으니 바꿔야 했고 delta rule이 등장한다.  
delta rule의 핵심은 gradient descent를 이용하는 것이다.  
Gradient Descent (GD)는 오류률을 미분해서 0이되는 값을 찾을 때까지 계속 가중치를 업데이트 하는 방법 이다.  
(미분해서 0되다는 것이 최소를 의미하는 건 고등학교에서 배우니 알겠죠)  
그럼 여기서 두 가지 의문점은 갖는다.  
1. 첫째 미분해서 0이 최소인것은 Convex인 경우고 미분해서 0이 최대가 되는 Concave도 있지 않는가?  
아니요 그럴일은 없다 왜?  
gradient descent의 공식을 보면 w_j+1 = w_j - (learning_rate)(d/dw)(error) 인데 이전 가중치에서 오류를 편미분한 값을 빼주기 때문에 절대 Concave로 갈 일은 없다.  
2. 두번째 오류의 minimum을 구하는데 만약 무한히 넓은 함수 공간의 경우는 local minimum에 빠지거나 plateau에 빠질 수 있지 않는가?  
맞는 말이다. 때문에 학습 속도도 느리고 미리 학습이 중단 되거나 영원히 않 끝날 수도 있다. 이는 GD의 문제점이다.  
그래서 새로운 방법이 등장한다.  
Stochastic Gradient Descent (SGD)이다.  
전체 데이터(full batch) 대신 일부 데이터의 모음(mini Batch)를 사용하여 계산하는 것이다. 전체 데이터 중 무작위로 뽑아 사용하기 때문에 확률적(Stochastic)이라고 한다. 일부 데이터만을 학습하기 때문에 메모리 소모량이 낮으며 학습속도도 빠르다. 하지만 무작위로 데이터를 선정하므로 gradient가 불안정하게 움직이는 shooting 현상이 발생한다. 이것 때문에 local minimum에 빠진다 해도 쉽게 빠져나올 수는 있지만 global minimum에 도달할 수 없을 경우도 발생한다.  
이를 해결하고자 Moment와 Adaptive를 사용한다.  
먼저 Moment를 사용한 Momentum 이다.  
이전의 Gradient 값도 고려하여 가중치를 업데이트하는 방법이다. 공식은 다음과 같다.  
v_t = (r * v_t-1) + (learning_rate)(d/dw)(error) ...... [ r : moment variable 0 ~ 0.9 ]  
w_t+1 = w_t - v_t  
Momentum은 local minimum과 shooting 문제를 해결은 가능하나 이전 가중치를 계산에 계속 고려해야되서 학습속도가 느려진다.   
그래서 Adaptive를 사용한다.  
이를 가중치 업데이트 빈도수에 따라 learning_rate를 다르게 해준다. 





# Activation Function (활성화 함수)
활성화함수  
이전 층(layer)의 결과값을 변환하여 다른 층의 뉴런으로 신호를 전달하는 역할  
왜 쓸까? -> 데이터를 비선형으로 변형하기 위해 사용한다.
초기 활성화함수는 임계치을 넘으면 1(혹은 True)를 출력하고 그렇지 않을 때는 0(False)을 출력하는 이진분류기 또는 퍼셈트론에 쓰이던 함수  
처음 linear, step, sigmoid 등을 사용 (linear는 입출력이 동일하여 딥의 의미가 없어지고 step은 binary case에서는 좋지만 optimization에서 미분을 해야되는데 못 하므로 의미 없음)  
그래서 sigmoid를 많이 썼다. (퍼셉트론 당시에만) sigmoid = 1/(1+exp^-x)  
하지만 문제점이 있다. gradient vanishing 문제 




# Convolution Neural Network (CNN)







