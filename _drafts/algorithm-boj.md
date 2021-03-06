---
layout: post
title: 📄 백준 2003번 - 수들의 합 2
# date: 2022-02-07 16:51:00 +0900
# published: true
categories: [algorithm, baekjoon]
tags: [algorithm, baekjoon, two pointer]
---

## **📄 문제 소개**

![image](https://user-images.githubusercontent.com/6462456/152730612-63697f48-a4c0-4312-bdb0-f5cb73e591b9.png)
_백준 2003번 : 수들의 합 2_

링크 : [https://www.acmicpc.net/problem/2003](https://www.acmicpc.net/problem/2003)

N개의 자연수를 입력받아 배열을 구성하고,
배열 내부에서 구간 `(i, j)`를 설정했을 때  
해당 구간의 합 `A[i] + A[i + 1] + ... + A[j]`가
`M`이 되는 구간의 경우의 수를 구하는 문제이다.  

## **📗 문제풀이 과정**

![image](https://user-images.githubusercontent.com/6462456/152731456-272a772b-c5f1-47d2-b16f-596fb651e8a6.png)

```python
# N과 M 입력
N, M = map(int, input().split())
# 배열 A 입력
A = list(map(int, input().split()))

cnt = 0

for i in range(N): # O(N^3)
    for j in range(i, N):
        _sum = 0
        for k in range(i, j + 1):
            _sum += A[k]
        if _sum == M:
            cnt += 1

print(cnt)
```

문제를 보자 마자 가장 간단하게는 위처럼 모든 구간을 훑는
반복문 구조로 구성할 수 있겠으나,  
이 경우 구간 `(i, j)`의 합을 구하는 데 `O(N)`이 걸린다고 가정하면
전체 알고리즘의 시간복잡도는 `O(N^3)`이 된다.  
그리고 문제에서 N이 최대 `10^4`이고 시간 제한이 0.5초이기 때문에,  
시간복잡도가 `O(N^2)` 보다 커지는 위 알고리즘으로는
문제를 절대 시간 내에 풀 수 없다고 생각해야 한다.  

![image](https://user-images.githubusercontent.com/6462456/152732191-fd94001b-c73f-4076-a0ea-420dded9c8a4.png)

위 문제가 대표적으로 `two pointer` 알고리즘을 사용하는 예시이다.  
우선, `left`와 `right` 두 개의 포인터가
맨 처음엔 배열의 첫 번째 요소를 가리키도록 한다.  

![image](https://user-images.githubusercontent.com/6462456/152732524-faedda3d-23ea-47ad-bbc1-8ec8b79c3d03.png)
![image](https://user-images.githubusercontent.com/6462456/152732589-41017a9d-f155-4303-9916-16734ec5a016.png)

`left`와 `right`는 매 순간 어떠한 구간을 가리킨다.  
`right`가 1 증가하는 것은 구간이 오른쪽으로 늘어난다는 것을 의미하며,
마찬가지로 `left`가 1 증가하는 것은 구간이 왼쪽으로부터 줄어든다는 것을 의미한다.  

우리가 목표로 하는 것은 **구간의 합이 M이 되는 순간**을 체크하는 것이며,
문제에서 주어진 대로 배열 A의 모든 요소들은 30,000을 넘지 않는 자연수이다.
따라서 구간의 합은 `right`를 증가시킬수록 늘어나며
`left`을 증가시키면 줄어드므로
이로부터 구간의 합이 주어진 기준 `M`보다 작다면 `right`를 1 증가시키고
`M`보다 크다면 `left`를 1 증가시키는 방식으로
구간 합을 검사해 나갈 수 있다는 것을 알 수 있다.  

또한, `left`나 `right`가 증가하는 순간마다
그때까지의 구간 합을 `sum`에 저장하고 있으므로
단순히 `sum -= A[left]`나 `sum += A[right]`를 수행함으로써
구간 합의 변화를 `상수 시간 : O(1)` 내에 계산할 수 있다는 게 핵심이다.  

```python
# N, M 입력
N, M = map(int, input().split())
# 배열 A 입력
A = list(map(int, input().split()))

cnt = 0     # 경우의 수를 체크하는 카운터 변수
left = 0    # left pointer
right = 0   # right pointer
_sum = 0    # 구간의 합을 저장하는 변수

for left in range(N): # O(N^2)
    # right를 가능한 한 증가시키면서 늘어나는 구간의 합 반영
    while _sum < M and right < N: # O(N)
        _sum += A[right]
        right += 1
    
    # 구간의 합이 M인지 검사
    if _sum == M:
        cnt += 1
        
    # left를 증가시키면서 줄어든 구간의 합 반영 
    _sum -= A[left]
    
print(cnt)
```

`left`가 `right`보다 커질 수 없기 때문에,
위처럼 for문을 이용해 `left`를 N만큼 반복하고
`right`가 증가될 수 있는 조건만큼 최대한 커지도록 하면
모든 가능한 구간의 합을 검사하는 데 `O(N^2)` 의 시간복잡도를 만족할 수 있다.  

![image](https://user-images.githubusercontent.com/6462456/152744471-6beac076-4893-4603-82ee-139cb745207b.png)

위 알고리즘을 따라가다 보면
생각과 다르게 `left`와 `right`가 모두 마지막 요소를 가리키기까지 기다리지 않고
위 그림 같은 상황에서 수행을 완료해 버림을 알 수 있다.  
그 이유는 위처럼 포인터들이 가리키고 있는 경우 
`right`는 N 이상 증가할 수 없으며
`left`를 증가시켜 봤자 `sum`은 `M`보다 작아질 수 밖에 없으므로
다음 단계들을 의미 없는 수행으로 판단하고 종료하기 때문이다.

또한 이 코드를 보다 보면 `left`가 `right`보다 커지는,
그러니까 반전된 구간까지도 중복될 수 있지 않나? 하는 의문을 가질 수도 있는데  
그런 경우는 `left`가 증가되면서 `sum`에 A[left]만큼 감소되므로
구간의 합이 다시 만족될 때까지 `right`가 `left` 이상으로 다시 증가하므로
문제가 되지 않는다.

```python
# N, M 입력
N, M = map(int, input().split())
# 배열 A 입력
A = list(map(int, input().split()))

cnt = 0     # 경우의 수를 체크하는 카운터 변수
left = 0    # left pointer
right = 0   # right pointer
_sum = 0    # 구간의 합을 저장하는 변수

while True: # O(N^2)
    if _sum > M:    # 구간 합이 M보다 크면 left 증가
        _sum -= A[left]
        left += 1
    elif right == N:
        break
    else:           # 구간 합이 M보다 작으면 right 증가
        _sum += A[right]
        right += 1
    
    if _sum == M:   # 구간 합이 M이면 cnt 증가
        cnt += 1

print(cnt)
```

만약 for문을 이용하지 않고 while 문을 이용해 구현하도록 하면,
위처럼 코드를 구성할 수 있다.  
이 때는 구간 합을 `M`에 비교해 가며 각 상황마다 `left`와 `right`를 증가시키며,
`right`가 `N`보다 커지는 순간을 탈출 조건으로 설정해 주어야 한다.

## **💻 코드**

<script src="https://gist.github.com/poodlepoodle/87f324cb4696e9da7e1b1d5cc583dd51.js"></script>

## **📒 연관 개념**

> -   Two Pointer(투 포인터)