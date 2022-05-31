# AI_theory

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
# S = klnW (볼츠만 엔트로피)  
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
S = klnW에 대입  
S = kln(N!product(1/Nk!)) = (k){ln(N!) - sigma(ln(Nk))}




















