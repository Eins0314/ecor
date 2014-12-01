http://ko.wikipedia.org/wiki/%EA%B3%A0%EC%9C%B3%EA%B0%92

위키 - 고윳값

선형대수학에서 고유벡터란,

어떤 선형변환이 일어난 후에도 그 방향이 변하지 않는 영벡터가 아닌 벡터를 말한다.

(* 선형변환이란,

벡터 합과 스칼라 곱 성질을 만족하는 벡터 공간 사이 함수이다.

시계방향 회전, x축에 대칭이동, 모든방향에 K 배 변형, y축 사영, 찌그러뜨림 등등)

변환 후에 고유벡터의 크기가 변하는 비율을 그 벡터의 고윳값이라 한다.

선형변환은 대개 고유벡터와 고윳값만으로 완전히 설명할 수 있다.


<역사와 어원>

이차형식 미분방정식 이론에서 나왔다.
코시가 대칭행렬이 실수 고윳값을 가진다는 것을 증명했는데,
에르미트가 이를 더 확장해서,
에르미트 행렬이면 실수 고윳값을 가짐을 증명했다.

힐베르트가 오늘날 용어인 아이젠벡터, 아이젠밸류 사용을 도입했다.


----------
http://darkpgmr.tistory.com/105
블로그

고유값과 고유벡터는 SVD(특이값분해), pseudo-inverse, 선형연립방정식 풀이,
PCA(주성분분석) 등의 주요 응용에 밑바탕으로 사용된다.


1. 고유값, 고유벡터?

행렬 A 를 선형변환으로 볼때, 고유벡터란,
그 선형변환에 대한 자신의 결과가, 자기자신의 상수배가 되는 (0이 아닌)벡터이다.
그 상수배가 고유값이다.

즉, 그 선형변환에 대해서 방향이 변하지 않는 벡터.

고유값과 고유벡터는 아에 없을 수도 있고, 하나만, 또는 최대 n 개가 존재할 수도 있다.


2. 기하학적 의미

기하학적으로 선형변환 행렬 A 의 고유벡터란 것은,

그 선형변환에 의해 방향은 보존되고 스케일만 변화되는 방향벡터를 말하고,

그 변화된 스케일 값을 고유값이라고 한다.

예를들어,

지구 자전운동같은 3차원 변화를 생각할때,

이 회전에 의해 변하지 않는 고유벡터는 회전축벡터이고 고유값은 1일 것이다.


3. 고유값 분해를 이용한 대각화 eigendecomposition

정방행렬의 대각화와 밀접한 관련이 있다.

일단 대각행렬을 뒤에 곱하면, 대각 원소 크기만큼 상수배가 된다.

행렬 A 의 고유값, 고유벡터가 있을때

A[v1 v2 v3 ... vn] = [l1v1 l2v2 ... lnvn]

= [v1 v2 v3.. vn] l 대각 행렬

이를 요약하면,

AP = PA_

A = PA_P^-1

즉 A 행렬은 자신의 고유벡터들로 이루어진 P 행렬과 고유값으로 이루어진 대각행렬A_ 로 표현될 수 있다.

모든 정방행렬이 가능한 것은 아니지만,

이렇게 대각화 가능해지면 좋은 점이 있다.

A 의 det(A) 값, 거듭제곱값, 역행렬, 대각합, 행렬 다항식등을 손쉽게 계산 가능하다.

det(A) = 대각화 곱(람다 곱 = 고유값 곱)

A^k = P L^k P-1

inv(A) = P 1/L P-1

tr(A) = 대각화 합

f(A) = P f(L) P-1

(* 대각행렬은 제곱, 역행렬, 함수적용이 쉽다)



4. 고유값분해 가능조건

n x n 행렬 A 라면,

n 개의 일차독립인 고유벡터를 가져야 한다. (선형독립)


6. 대칭행렬과 고유값분해

대칭행렬의 좋은 성질 2가지

- 대칭행렬은 항상 고유값 대각화가 가능
- 특히 직교행렬로 대각화가 가능

A = PA_P-1
  = PA_P'


* 직교행렬은 전치행렬이 역행렬이 된다.
A-1 = A'
AA' = I



---------
http://darkpgmr.tistory.com/106
특이값 분해 SVD singular value decomposition

고유값분해처럼 행렬을 대각화하는 방법

그런데 이 특이값 분해는 정방행렬 외에 모든 m x n 행렬에 적용 가능하다.

....