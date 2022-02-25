---
layout: post
title: 📄 백준 2143번 - 두 배열의 합
# date: 2022-02-07 16:51:00 +0900
# published: true
categories: [algorithm, baekjoon]
tags: [algorithm, baekjoon]
---

## **📄 문제 소개**

_백준 2143번 : 두 배열의 합_

링크 : [https://www.acmicpc.net/problem/2143](https://www.acmicpc.net/problem/2143)

정수로 이루어진 배열 A와 B를 입력받았을 때
A와 B에서 각각 부분 배열을 정하고,  
두 부분 배열의 합이 `T`가 되는 경우의 수를 카운팅하는 문제이다.

## **📗 문제풀이 과정**

### **🧐 무식한 접근**

![image](https://user-images.githubusercontent.com/6462456/152927944-a1fb1dd4-546c-44b8-99a5-960fa21cf9a0.png)

```python
# 부분합 목표 값 T 입력
T = int(input())

# 배열 A의 요소 입력
len_A = int(input())
A = list(map(int, input().split()))
# 배열 B의 요소 입력
len_B = int(input())
B = list(map(int, input().split()))

answer = 0

# A 배열의 가능한 부분합 경우의 수 완전 탐색 => O(N^5)
for i in range(len_A):
    for j in range(i, len_A):
        # A 배열의 부분합 계산
        T_A = 0
        for ind in range(i, j + 1): # O(N)
            T_A += A[ind]
        
        # B 배열의 가능한 부분합 경우의 수 완전 탐색 => O(N^3)
        for k in range(len_B):
            for l in range(k, len_B):
                # B 배열의 부분합 계산
                T_B = 0
                for ind in range(k, l + 1): # O(N)
                    T_B += B[ind]
                
                # 두 배열의 부분합을 더한 결과가 T인 경우 카운팅
                if T_A + T_B == T:
                    answer += 1

print(answer)
```

가장 무식한 방법부터 접근해 보자.  

A 배열의 모든 부분배열을 검사하는 데 `O(N^2)`,  
B 배열의 모든 부분배열을 검사하는 데 `O(N^2)`,  
그리고 부분 배열의 합을 계산하는 시간을 `O(N)`으로 고려하면
전체 알고리즘은 `O(N^5)` 정도로 생각할 수 있다.  

A 배열과 B 배열의 크기가 각각 `N`, `M`으로 주어져 있고  
`N`과 `M` 모두 `10^3`이므로
주어진 시간 제한 2초에 들어오기 위해서는
알고리즘이 `O(N^2)`보다 크면 안 된다고 판단할 수 있다.  

### **😀 Two Pointer를 사용한다면?**

> 작성중

## **💻 코드**

<script src="https://gist.github.com/poodlepoodle/87f324cb4696e9da7e1b1d5cc583dd51.js"></script>

## **📒 연관 개념**

> -   Two Pointer(투 포인터)