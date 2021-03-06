---
layout: post
title: ๐ ๋ฐฑ์ค 2003๋ฒ - ์๋ค์ ํฉ 2
# date: 2022-02-07 16:51:00 +0900
# published: true
categories: [algorithm, baekjoon]
tags: [algorithm, baekjoon, two pointer]
---

## **๐ ๋ฌธ์  ์๊ฐ**

![image](https://user-images.githubusercontent.com/6462456/152730612-63697f48-a4c0-4312-bdb0-f5cb73e591b9.png)
_๋ฐฑ์ค 2003๋ฒ : ์๋ค์ ํฉ 2_

๋งํฌ : [https://www.acmicpc.net/problem/2003](https://www.acmicpc.net/problem/2003)

N๊ฐ์ ์์ฐ์๋ฅผ ์๋ ฅ๋ฐ์ ๋ฐฐ์ด์ ๊ตฌ์ฑํ๊ณ ,
๋ฐฐ์ด ๋ด๋ถ์์ ๊ตฌ๊ฐ `(i, j)`๋ฅผ ์ค์ ํ์ ๋  
ํด๋น ๊ตฌ๊ฐ์ ํฉ `A[i] + A[i + 1] + ... + A[j]`๊ฐ
`M`์ด ๋๋ ๊ตฌ๊ฐ์ ๊ฒฝ์ฐ์ ์๋ฅผ ๊ตฌํ๋ ๋ฌธ์ ์ด๋ค.  

## **๐ ๋ฌธ์ ํ์ด ๊ณผ์ **

![image](https://user-images.githubusercontent.com/6462456/152731456-272a772b-c5f1-47d2-b16f-596fb651e8a6.png)

```python
# N๊ณผ M ์๋ ฅ
N, M = map(int, input().split())
# ๋ฐฐ์ด A ์๋ ฅ
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

๋ฌธ์ ๋ฅผ ๋ณด์ ๋ง์ ๊ฐ์ฅ ๊ฐ๋จํ๊ฒ๋ ์์ฒ๋ผ ๋ชจ๋  ๊ตฌ๊ฐ์ ํ๋
๋ฐ๋ณต๋ฌธ ๊ตฌ์กฐ๋ก ๊ตฌ์ฑํ  ์ ์๊ฒ ์ผ๋,  
์ด ๊ฒฝ์ฐ ๊ตฌ๊ฐ `(i, j)`์ ํฉ์ ๊ตฌํ๋ ๋ฐ `O(N)`์ด ๊ฑธ๋ฆฐ๋ค๊ณ  ๊ฐ์ ํ๋ฉด
์ ์ฒด ์๊ณ ๋ฆฌ์ฆ์ ์๊ฐ๋ณต์ก๋๋ `O(N^3)`์ด ๋๋ค.  
๊ทธ๋ฆฌ๊ณ  ๋ฌธ์ ์์ N์ด ์ต๋ `10^4`์ด๊ณ  ์๊ฐ ์ ํ์ด 0.5์ด์ด๊ธฐ ๋๋ฌธ์,  
์๊ฐ๋ณต์ก๋๊ฐ `O(N^2)` ๋ณด๋ค ์ปค์ง๋ ์ ์๊ณ ๋ฆฌ์ฆ์ผ๋ก๋
๋ฌธ์ ๋ฅผ ์ ๋ ์๊ฐ ๋ด์ ํ ์ ์๋ค๊ณ  ์๊ฐํด์ผ ํ๋ค.  

![image](https://user-images.githubusercontent.com/6462456/152732191-fd94001b-c73f-4076-a0ea-420dded9c8a4.png)

์ ๋ฌธ์ ๊ฐ ๋ํ์ ์ผ๋ก `two pointer` ์๊ณ ๋ฆฌ์ฆ์ ์ฌ์ฉํ๋ ์์์ด๋ค.  
์ฐ์ , `left`์ `right` ๋ ๊ฐ์ ํฌ์ธํฐ๊ฐ
๋งจ ์ฒ์์ ๋ฐฐ์ด์ ์ฒซ ๋ฒ์งธ ์์๋ฅผ ๊ฐ๋ฆฌํค๋๋ก ํ๋ค.  

![image](https://user-images.githubusercontent.com/6462456/152732524-faedda3d-23ea-47ad-bbc1-8ec8b79c3d03.png)
![image](https://user-images.githubusercontent.com/6462456/152732589-41017a9d-f155-4303-9916-16734ec5a016.png)

`left`์ `right`๋ ๋งค ์๊ฐ ์ด๋ ํ ๊ตฌ๊ฐ์ ๊ฐ๋ฆฌํจ๋ค.  
`right`๊ฐ 1 ์ฆ๊ฐํ๋ ๊ฒ์ ๊ตฌ๊ฐ์ด ์ค๋ฅธ์ชฝ์ผ๋ก ๋์ด๋๋ค๋ ๊ฒ์ ์๋ฏธํ๋ฉฐ,
๋ง์ฐฌ๊ฐ์ง๋ก `left`๊ฐ 1 ์ฆ๊ฐํ๋ ๊ฒ์ ๊ตฌ๊ฐ์ด ์ผ์ชฝ์ผ๋ก๋ถํฐ ์ค์ด๋ ๋ค๋ ๊ฒ์ ์๋ฏธํ๋ค.  

์ฐ๋ฆฌ๊ฐ ๋ชฉํ๋ก ํ๋ ๊ฒ์ **๊ตฌ๊ฐ์ ํฉ์ด M์ด ๋๋ ์๊ฐ**์ ์ฒดํฌํ๋ ๊ฒ์ด๋ฉฐ,
๋ฌธ์ ์์ ์ฃผ์ด์ง ๋๋ก ๋ฐฐ์ด A์ ๋ชจ๋  ์์๋ค์ 30,000์ ๋์ง ์๋ ์์ฐ์์ด๋ค.
๋ฐ๋ผ์ ๊ตฌ๊ฐ์ ํฉ์ `right`๋ฅผ ์ฆ๊ฐ์ํฌ์๋ก ๋์ด๋๋ฉฐ
`left`์ ์ฆ๊ฐ์ํค๋ฉด ์ค์ด๋๋ฏ๋ก
์ด๋ก๋ถํฐ ๊ตฌ๊ฐ์ ํฉ์ด ์ฃผ์ด์ง ๊ธฐ์ค `M`๋ณด๋ค ์๋ค๋ฉด `right`๋ฅผ 1 ์ฆ๊ฐ์ํค๊ณ 
`M`๋ณด๋ค ํฌ๋ค๋ฉด `left`๋ฅผ 1 ์ฆ๊ฐ์ํค๋ ๋ฐฉ์์ผ๋ก
๊ตฌ๊ฐ ํฉ์ ๊ฒ์ฌํด ๋๊ฐ ์ ์๋ค๋ ๊ฒ์ ์ ์ ์๋ค.  

๋ํ, `left`๋ `right`๊ฐ ์ฆ๊ฐํ๋ ์๊ฐ๋ง๋ค
๊ทธ๋๊น์ง์ ๊ตฌ๊ฐ ํฉ์ `sum`์ ์ ์ฅํ๊ณ  ์์ผ๋ฏ๋ก
๋จ์ํ `sum -= A[left]`๋ `sum += A[right]`๋ฅผ ์ํํจ์ผ๋ก์จ
๊ตฌ๊ฐ ํฉ์ ๋ณํ๋ฅผ `์์ ์๊ฐ : O(1)` ๋ด์ ๊ณ์ฐํ  ์ ์๋ค๋ ๊ฒ ํต์ฌ์ด๋ค.  

```python
# N, M ์๋ ฅ
N, M = map(int, input().split())
# ๋ฐฐ์ด A ์๋ ฅ
A = list(map(int, input().split()))

cnt = 0     # ๊ฒฝ์ฐ์ ์๋ฅผ ์ฒดํฌํ๋ ์นด์ดํฐ ๋ณ์
left = 0    # left pointer
right = 0   # right pointer
_sum = 0    # ๊ตฌ๊ฐ์ ํฉ์ ์ ์ฅํ๋ ๋ณ์

for left in range(N): # O(N^2)
    # right๋ฅผ ๊ฐ๋ฅํ ํ ์ฆ๊ฐ์ํค๋ฉด์ ๋์ด๋๋ ๊ตฌ๊ฐ์ ํฉ ๋ฐ์
    while _sum < M and right < N: # O(N)
        _sum += A[right]
        right += 1
    
    # ๊ตฌ๊ฐ์ ํฉ์ด M์ธ์ง ๊ฒ์ฌ
    if _sum == M:
        cnt += 1
        
    # left๋ฅผ ์ฆ๊ฐ์ํค๋ฉด์ ์ค์ด๋  ๊ตฌ๊ฐ์ ํฉ ๋ฐ์ 
    _sum -= A[left]
    
print(cnt)
```

`left`๊ฐ `right`๋ณด๋ค ์ปค์ง ์ ์๊ธฐ ๋๋ฌธ์,
์์ฒ๋ผ for๋ฌธ์ ์ด์ฉํด `left`๋ฅผ N๋งํผ ๋ฐ๋ณตํ๊ณ 
`right`๊ฐ ์ฆ๊ฐ๋  ์ ์๋ ์กฐ๊ฑด๋งํผ ์ต๋ํ ์ปค์ง๋๋ก ํ๋ฉด
๋ชจ๋  ๊ฐ๋ฅํ ๊ตฌ๊ฐ์ ํฉ์ ๊ฒ์ฌํ๋ ๋ฐ `O(N^2)` ์ ์๊ฐ๋ณต์ก๋๋ฅผ ๋ง์กฑํ  ์ ์๋ค.  

![image](https://user-images.githubusercontent.com/6462456/152744471-6beac076-4893-4603-82ee-139cb745207b.png)

์ ์๊ณ ๋ฆฌ์ฆ์ ๋ฐ๋ผ๊ฐ๋ค ๋ณด๋ฉด
์๊ฐ๊ณผ ๋ค๋ฅด๊ฒ `left`์ `right`๊ฐ ๋ชจ๋ ๋ง์ง๋ง ์์๋ฅผ ๊ฐ๋ฆฌํค๊ธฐ๊น์ง ๊ธฐ๋ค๋ฆฌ์ง ์๊ณ 
์ ๊ทธ๋ฆผ ๊ฐ์ ์ํฉ์์ ์ํ์ ์๋ฃํด ๋ฒ๋ฆผ์ ์ ์ ์๋ค.  
๊ทธ ์ด์ ๋ ์์ฒ๋ผ ํฌ์ธํฐ๋ค์ด ๊ฐ๋ฆฌํค๊ณ  ์๋ ๊ฒฝ์ฐ 
`right`๋ N ์ด์ ์ฆ๊ฐํ  ์ ์์ผ๋ฉฐ
`left`๋ฅผ ์ฆ๊ฐ์์ผ ๋ดค์ `sum`์ `M`๋ณด๋ค ์์์ง ์ ๋ฐ์ ์์ผ๋ฏ๋ก
๋ค์ ๋จ๊ณ๋ค์ ์๋ฏธ ์๋ ์ํ์ผ๋ก ํ๋จํ๊ณ  ์ข๋ฃํ๊ธฐ ๋๋ฌธ์ด๋ค.

๋ํ ์ด ์ฝ๋๋ฅผ ๋ณด๋ค ๋ณด๋ฉด `left`๊ฐ `right`๋ณด๋ค ์ปค์ง๋,
๊ทธ๋ฌ๋๊น ๋ฐ์ ๋ ๊ตฌ๊ฐ๊น์ง๋ ์ค๋ณต๋  ์ ์์ง ์๋? ํ๋ ์๋ฌธ์ ๊ฐ์ง ์๋ ์๋๋ฐ  
๊ทธ๋ฐ ๊ฒฝ์ฐ๋ `left`๊ฐ ์ฆ๊ฐ๋๋ฉด์ `sum`์ A[left]๋งํผ ๊ฐ์๋๋ฏ๋ก
๊ตฌ๊ฐ์ ํฉ์ด ๋ค์ ๋ง์กฑ๋  ๋๊น์ง `right`๊ฐ `left` ์ด์์ผ๋ก ๋ค์ ์ฆ๊ฐํ๋ฏ๋ก
๋ฌธ์ ๊ฐ ๋์ง ์๋๋ค.

```python
# N, M ์๋ ฅ
N, M = map(int, input().split())
# ๋ฐฐ์ด A ์๋ ฅ
A = list(map(int, input().split()))

cnt = 0     # ๊ฒฝ์ฐ์ ์๋ฅผ ์ฒดํฌํ๋ ์นด์ดํฐ ๋ณ์
left = 0    # left pointer
right = 0   # right pointer
_sum = 0    # ๊ตฌ๊ฐ์ ํฉ์ ์ ์ฅํ๋ ๋ณ์

while True: # O(N^2)
    if _sum > M:    # ๊ตฌ๊ฐ ํฉ์ด M๋ณด๋ค ํฌ๋ฉด left ์ฆ๊ฐ
        _sum -= A[left]
        left += 1
    elif right == N:
        break
    else:           # ๊ตฌ๊ฐ ํฉ์ด M๋ณด๋ค ์์ผ๋ฉด right ์ฆ๊ฐ
        _sum += A[right]
        right += 1
    
    if _sum == M:   # ๊ตฌ๊ฐ ํฉ์ด M์ด๋ฉด cnt ์ฆ๊ฐ
        cnt += 1

print(cnt)
```

๋ง์ฝ for๋ฌธ์ ์ด์ฉํ์ง ์๊ณ  while ๋ฌธ์ ์ด์ฉํด ๊ตฌํํ๋๋ก ํ๋ฉด,
์์ฒ๋ผ ์ฝ๋๋ฅผ ๊ตฌ์ฑํ  ์ ์๋ค.  
์ด ๋๋ ๊ตฌ๊ฐ ํฉ์ `M`์ ๋น๊ตํด ๊ฐ๋ฉฐ ๊ฐ ์ํฉ๋ง๋ค `left`์ `right`๋ฅผ ์ฆ๊ฐ์ํค๋ฉฐ,
`right`๊ฐ `N`๋ณด๋ค ์ปค์ง๋ ์๊ฐ์ ํ์ถ ์กฐ๊ฑด์ผ๋ก ์ค์ ํด ์ฃผ์ด์ผ ํ๋ค.

## **๐ป ์ฝ๋**

<script src="https://gist.github.com/poodlepoodle/87f324cb4696e9da7e1b1d5cc583dd51.js"></script>

## **๐ ์ฐ๊ด ๊ฐ๋**

> -   Two Pointer(ํฌ ํฌ์ธํฐ)