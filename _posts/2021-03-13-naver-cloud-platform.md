---
layout: post
title: ☁️ Naver Cloud Platform Micro 타입 서버 생성
date: 2021-03-13 18:34:00 +0900
published: true
categories: [projects, web portfolio]
tags: [naver cloud platform]
---

## **클라우드 플랫폼 신청**

4월 안쪽으로 포트폴리오를 웹상에 띄워 놓기로 염두에 두고 있었는데,
메일로 구독하고 있던 노마드 코더에서 [포트폴리오 챌린지](https://nomadcoders.co/community/thread/458)를 3월 28일까지 진행한다고 해서
급히 시작하려고 서버 인스턴스 생성부터 들어갔다.

![](https://user-images.githubusercontent.com/6462456/150917428-cdecf006-c02b-49b4-9222-b6995c64c272.png){: .shadow }

군대에서 신청한 `AWS` 1년 무료 체험이 끝나 있어서 다른 계정으로 만들까 아니면 구글 클라우드 플랫폼으로 해볼까 고민했는데,
일단 서버 쪽 지식이 거의 없어서.. 당장 한글 레퍼런스가 잘 설명되어 있는 `네이버 클라우드 플랫폼`으로 해보기로 결정했다.
여기도 신규 가입한 경우 10만원치 크레딧과 1년 무료 서버를 제공한다.
_(Micro 타입으로 생성할 경우에 한해서)_

## **인스턴스 생성 과정**

![](https://user-images.githubusercontent.com/6462456/150917720-8f88d25d-133a-42e6-a86a-d7a38a671525.png){: .shadow }
![](https://user-images.githubusercontent.com/6462456/150917723-3bc5481b-891a-4dc4-82e5-1aafc26595d7.png){: .shadow }


`Micro 타입 서버`로 선택하면 사실상 서버 생성 과정에서 선택할 항목은 거의 없다.
인증서를 다운받아 잘 보관해 두고 계속 진행한다.

![](https://user-images.githubusercontent.com/6462456/150917780-7e4c63df-83a4-4c4e-8a8b-114d5e29c9c9.png){: .shadow }

수 분 내에 서버가 생성된다고 하는데, 나 같은 경우는 5분 안쪽으로 생성 알림 메일이 도착했다.

![img-23](https://user-images.githubusercontent.com/6462456/150917936-bf52459e-b2bd-458b-bf04-fb87bd20004c.png){: .shadow}

다음으로는 공인 IP 신청을 해야 한다. 공인 IP는 한 달 기준으로 4,032원씩 요금이 결제된다.

![img-24](https://user-images.githubusercontent.com/6462456/150918096-c30cbb0a-8e93-4ebd-af02-da3d84ff3986.png){: .shadow}
![img-25](https://user-images.githubusercontent.com/6462456/150918100-08dba940-59f5-4ca0-9ee6-18a1db56dce4.png){: .shadow}

포트포워딩도 설정한다.
캡쳐는 하지 않았는데 ACG 설정도 일단 몇 개 포트에 대해서 추가로 설정했다.

![img-26](https://user-images.githubusercontent.com/6462456/150918122-c7671bcd-c6db-47f9-a40a-807701715431.png){: .shadow}

필요한 설정 마무리하고 터미널로 접속한 모습..
이제 홈페이지 배포하려면 이것저것 깔고 삽질 해야할듯 🔥

## **참고한 링크**

- [전체적인 과정이 잘 설명되어 있는 블로그](https://essencedrain.tistory.com/3?category=841985)
- [NCP Documentation](https://docs.ncloud.com/ko/compute/compute-3-1-v2.html)