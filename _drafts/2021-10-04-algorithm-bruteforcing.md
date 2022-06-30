---
layout: post
title: 📋 알고리즘 개념 - Bruteforcing(완전 탐색)
date: 2022-06-27 23:41:38 +0900
published: false
categories: [algorithm]
tags: [algorithm, bruteforcing]
---

## 📋 알고리즘 소개

### 🧐 적용 가능한 상황

![img-46](https://user-images.githubusercontent.com/6462456/150930997-211563f0-38a5-4d58-90d5-da41fd45f367.png)
_출처 : 유투브 "동빈나" - 코딩 테스트 & 알고리즘 대회 핵심 노트 - 투 포인터(Two Pointers), 구간 합(Prefix Sum)_

N개 요소로 구성된 배열이 주어졌을 때, 배열 내부에서 길이가 `1 <= M <= N`인 구간을 설정해  
그 **구간의 합이 K가 되는 경우의 수**를 구하는 알고리즘을 생각해 보자.  
  
![img-47](https://user-images.githubusercontent.com/6462456/150931783-a3840303-141b-4b6b-aa00-0f3f2d05c1ee.png)
_출처 : 유투브 "동빈나" - 코딩 테스트 & 알고리즘 대회 핵심 노트 - 투 포인터(Two Pointers), 구간 합(Prefix Sum)_

```python
# using Brute Force Method

# N과 K를 입력받았다고 가정
N = 5
K = 5

# 리스트 arr에 주어진 배열의 요소들을 입력받았다고 가정 -> O(N)
arr = [1, 2, 3, 2, 5]

# arr 배열을 구성하는 N개 요소에 대해 N개의 가능한 조합을 계산하는 데 N번의 명령 수행 -> O(N^3)
cnt = 0
for i in range(N):
    for j in range(i, N):
        temp = 0
        for k in range(i, j + 1):
            temp += arr[k]

        # 구간의 합이 주어진 값 K와 같을 경우 카운팅
        if temp == K:
            cnt += 1

# 카운팅한 값 출력
print(cnt)
```

위와 같이 `N = 5`인 예시를 생각해 보면, `Brute Force Method`로 접근했을 때  
중복을 제외하고 가능한 연속 수열의 조합을 모두 확인하려면 우선 배열의 N개 요소에 대한 접근이 이루어진다.  
각 N개 요소에 대해 인덱스 `i ~ i, i ~ i + 1, ... , i ~ N - 1`까지 최대 N개의 가능한 조합을 생각할 수 있고  
각 조합의 구간 합을 계산해 비교하는 데 한 번 더 N번의 반복이 이루어지기 때문에 전체 알고리즘의 시간복잡도는 `O(N^3)`이 된다.  
하지만 `O(N^3)`의 경우 N이 1000만 넘어가더라도 채점 기준에서 대략적으로 1초 내에 절대 통과할 수가 없다.  

위와 같은 상황에서 문제를 해결하기 위한 방법들로는  
`prefix sum` 혹은 `two pointer` 알고리즘을 대표적으로 사용하는데, 이번 포스트에서는 `prefix sum` 알고리즘을 사용해서 해결해 보자.  

### 😀 Prefix Sum을 사용한다면...

`prefix sum`의 핵심 아이디어는 **미리 구간합 배열을 전처리 과정에서 계산해 놓는 것**이다.  

![img-48](https://user-images.githubusercontent.com/6462456/150931919-c528ba40-73e9-4c0e-8a50-7108863c39bd.png)
_출처 : 유투브 "동빈나" - 코딩 테스트 & 알고리즘 대회 핵심 노트 - 투 포인터(Two Pointers), 구간 합(Prefix Sum)_

```python
# using Prefix Sum

# N과 K를 입력받았다고 가정
N = 5
K = 5

# 리스트 arr에 주어진 배열의 요소들을 입력받았다고 가정 -> O(N)
arr = [1, 2, 3, 2, 5]
sum_arr = [0]

# 미리 계산된 prefix sum 리스트를 구성 -> O(1)
for i in range(len(arr)):
    sum_arr.append(sum_arr[i] + arr[i])

# sum_arr 배열을 구성하는 N개 요소에 대해 N개의 가능한 조합을 계산하는 데 N번의 명령 수행 -> O(N^2)
cnt = 0
for i in range(N):
    for j in range(i + 1, N + 1):
        # 구간의 합이 주어진 값 K와 같을 경우 카운팅
        if sum_arr[j] - sum_arr[i] == K:
            cnt += 1

# 카운팅한 값 출력
print(cnt)
```

위 알고리즘은 같은 문제를 반복문 하나를 덜 쓰고 해결할 수 있다.  
핵심은 Prefix Sum 배열을 만드는 과정인데, 맨 처음에 Prefix Sum 배열에 0을 삽입하고 그 다음 요소부터는  
`Prefix Sum[i] = Prefix Sum[i - 1] + Original Array[i]`로 나타낼 수 있기 때문에  
Prefix Sum 배열의 값을 채우는 코드는 `O(N)` 내에 전처리가 수행될 수 있다.  
  
이에 따라 기존 arr 배열의 Index `0`부터 `N - 1`까지의 구간 합을 구하는 코드가 원래는 `O(N)`에 수행되었으나  
Prefix Sum 배열을 통해 나타내면 `Prefix Sum[N] - Prefix Sum[0]`으로 `O(1)`에 계산할 수 있으므로  
이에 따라 모든 구간의 합을 `O(N^2)` 내에 전부 계산할 수 있게 된다.  
  
물론 Prefix Sum은 미리 배열에 대해 정해진 누적 합 배열을 전처리로 초기화해 놓는 것이기 때문에  
Original 배열의 `i`번째 요소가 변경되는 경우 Prefix Sum 배열의 `i + 1`번째 ~ `N - 1`번째 요소가 모두 업데이트되어야 한다는 단점이 있다.  
따라서 Prefix Sum은 값을 변경하지 않는 경우(immutable)에 효율적인 알고리즘이다.

## 💻 대표적인 문제 풀이

### 📄 백준 11441번 : 합 구하기

![img-49](https://user-images.githubusercontent.com/6462456/150932237-726cb5b5-4fce-498c-bbc4-345e5126d4c2.png)
_백준 11441번 : 합 구하기_

링크 : [https://www.acmicpc.net/problem/11441](https://www.acmicpc.net/problem/11441)

이 문제를 봤을 때 가장 간단하게 풀 수 있는 코드를 생각해 보면,  
아래와 같이 N개의 수를 입력받고 난 후 M개의 구간에 대해  
i와 j가 주어지면 구간을 계산하는 방법을 떠올릴 수 있다.  

```python
# N 입력
N = int(input())
# N개의 수 입력
numbers = list(map(int, input().split()))
# M 입력
M = int(input())

answers = []
for _ in range(M):
    # 구간 i, j 입력
    (i, j) = list(map(int, input().split()))

    Sum = 0
    # 구간 i부터 j까지의 합 계산
    for k in range(i - 1, j):
        Sum += numbers[k]
    answers.append(Sum)

for ans in answers:
    print(ans)
```

이렇게 코드를 작성하면 각 케이스에 대해 올바른 출력을 계산하지만,  
정해진 시간 1초 내에 들어올 수 없다.  

```python
# N 입력
N = int(input())
# N개의 수 입력
numbers = list(map(int, input().split()))
# M 입력
M = int(input())

# prefix sum 배열 초기화
sum_numbers = [0]
for k in numbers:
    sum_numbers.append(sum_numbers[-1] + k)

answers = []
for _ in range(M):
    # 구간 i, j 입력
    (i, j) = list(map(int, input().split()))

    # 구간 i부터 j까지의 합을 prefix sum 배열로 계산
    answers.append(sum_numbers[j] - sum_numbers[i - 1])

for ans in answers:
    print(ans)
```

위처럼 코드를 약간 수정해, Prefix Sum 배열을 만들어 놓은 후  
각 구간 값 i와 j가 입력될 때마다 구간 `i`부터 `j`까지의 합을  
`prefix[j] - prefix[i - 1]`으로 계산하면  
전체 코드를 `O(N * M)`에서 `O(M)`내에 해결할 수 있다.  

### 📄 백준 2829번 : 아름다운 행렬

![img-50](https://user-images.githubusercontent.com/6462456/150932421-a7a9f553-6ffc-4da1-b06f-83034da2bb15.png)
_백준 2829번 : 아름다운 행렬_

링크 : [https://www.acmicpc.net/problem/2829](https://www.acmicpc.net/problem/2829)

쉽게 말해서, `N * N` 크기의 Square Matrix가 주어졌을 때 그 Matrix가 포함하는 모든 부분 Square Matrix 중  
`(왼쪽 위에서 시작하는 대각선 성분의 합 - 오른쪽 위에서 시작하는 대각선 성분의 합)`이 최대가 되는 경우의 값을 찾으라는 내용이다.  

![img-51](https://user-images.githubusercontent.com/6462456/150932651-1fd272db-2de6-4792-80fb-da94b998441f.png)

```python
# 행렬의 크기 N 입력
N = int(input())

# 행렬 값 입력
matrix = []
for _ in range(N):
    matrix.append(tuple(map(int, input().split())))
matrix = tuple(matrix)

# prefix matrix 초기화
prefix_left_up = []
prefix_right_up = []

for _ in range(N + 1):
    temp = []
    for _ in range(N + 1):
        temp.append(0)
    prefix_left_up.append(temp.copy())
    prefix_right_up.append(temp.copy())

for i in range(1, N + 1):
    for j in range(1, N + 1):
        prefix_left_up[i][j] = prefix_left_up[i - 1][j - 1] + matrix[i - 1][j - 1]
    for j in range(N):
        prefix_right_up[i][j] = prefix_right_up[i - 1][j + 1] + matrix[i - 1][j]

# calculating Max value of Square Matrices
max_beauty = -800000 # Minimum Value if N == 400
for M in range(2, N + 1):
    for i in range(0, N - M + 1):
        for j in range(0, N - M + 1):
            main_diagonal = prefix_left_up[i + M][j + M] - prefix_left_up[i][j]
            sub_diagonal = prefix_right_up[i + M][j] - prefix_right_up[i][j + M]
            max_beauty = main_diagonal - sub_diagonal if max_beauty < main_diagonal - sub_diagonal else max_beauty

print(max_beauty)
```

이 문제 또한 단순히 Brute Force Method로 접근하면 `O(N^4)`가 소요되어 시간 제한에 걸린다.  
여기서 두 방향의 대각선 합에 대해 각각의 2D Prefix Sum을 사용하는 경우  
특정 부분 Square Matrix가 주어졌을 때 대각선 요소들의 합을 구하는 시간을 `O(N)` -> `O(1)`로 줄일 수 있다.  

### 📄 백준 16713번 : Generic Queries

![img-52](https://user-images.githubusercontent.com/6462456/150932911-63eb9fe3-f113-45a3-9607-df35d28f803b.png)
_백준 16713번 : Generic Queries_

링크 : [https://www.acmicpc.net/problem/16713](https://www.acmicpc.net/problem/16713)

`N`개 수열이 주어지고, `Q`개의 쿼리에 의해 구간 `(i, j)`가 주어졌을 때 수열의 `i`번째 요소부터 `j`번째 요소까지의 XOR Sum을 구한다.  
결과적으로 모든 쿼리의 XOR Sum끼리의 XOR을 한 결과가 출력이 된다.  

![img-53](https://user-images.githubusercontent.com/6462456/150933038-9c1e6214-20af-4185-b73d-01842018e26f.png)

```python
# 수열 길이 N과 쿼리 갯수 Q 입력
(N, Q) = tuple(map(int, input().split()))

# 수열 입력
arr = list(map(int, input().split()))

# prefix sum 배열 전처리
xor_arr = [0]
for item in arr:
    xor_arr.append(xor_arr[-1] ^ item)

# 쿼리 별 처리
total_xor = 0
for _ in range(Q):
    (i, j) = list(map(int, input().split()))
    temp = xor_arr[j] ^ xor_arr[i - 1]
    total_xor = total_xor ^ temp

# 결과 출력
print(total_xor)
```

덧셈이 아닌 XOR 연산 또한 `A ^ B ^ B = A`가 되는 성질을 이용해 Prefix Sum 알고리즘을 적용할 수 있다.  
만약 구간의 합을 구하는 것이 아닌, 구간의 곱을 구하는 문제 또한  
Prefix Sum 배열의 요소에서 나누어 주는 방식으로 알고리즘을 활용할 수 있다.

😎