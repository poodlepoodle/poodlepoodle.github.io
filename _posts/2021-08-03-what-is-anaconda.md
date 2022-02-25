---
layout: post
title: 🐍 Anaconda 정의, 주요 명령어 정리
date: 2021-08-03 03:51:00 +0900
published: true
categories: [coding, python]
tags: [anaconda, conda, python]
---

이번에 디자인프로젝트 대비 DIP 세미나를 마치고 딥러닝 세미나 주차에 들어가면서 다시 파이썬을 다룰 일이 더 많아졌다.  
이전에는 파이썬 가상환경은 그나마 `virtualenv`로만 다뤄봤는데 연구실 멘토분들께서 `Anaconda`로 환경 세팅하는 걸 알려주셨다.  
Anaconda의 존재와 편리함은 알고 있었지만 파이썬을 깊게 팔 계기가 없어서 그냥 필요할 때마다 pip만 사용했는데...  
그래서 이참에 명령어를 좀 정리해 보기로 했다.

## **🐍 Anaconda?**

![img-27](https://user-images.githubusercontent.com/6462456/150922155-7c6372f9-d28b-477c-8d1b-a2ae6fdf3239.png){: .shadow}

`Anaconda`는 쉽게 생각해서 `파이썬 라이브러리 패키지를 관리해 주고 환경 설정을 도와주는 서비스`이다.  
이렇게 말하면 pip와 뭐가 다르냐... 고 할 수도 있겠지만, Anaconda는 각각의 실행 환경을 분리할 수가 있다.  
예시를 들면, 내가 파이썬을 사용해 A라는 작업과 B라는 작업을 할 때, A와 B의 패키지 환경을 독립적으로 관리할 수 있다는 뜻이다.

이러한 특징은 프로젝트 단위 코드가 복잡해질수록 생길 수 있는 의존성 충돌 문제를 방지해준다는 점에서 굉장히 편하다.  
뿐만 아니라 자체적으로 패키지들을 버젼 별로 배포한다는 점도 사용하기 편리한 장점이다.

## **💻 설치**

![img-28](https://user-images.githubusercontent.com/6462456/150922233-c2336434-6539-4add-b351-2836f6e7858b.png){: .shadow}

[https://www.anaconda.com/products/individual#download-section](https://www.anaconda.com/products/individual#download-section)

설치는 크게 건드릴 것 없이 안내해 주는 대로 따라가면 된다.  
Mac OS 기준으로도 pkg 파일로 제공되므로 편리하다.

## **🔨 기본적인 명령어**

```bash
# anaconda 버젼 확인
conda --version

# anaconda 버젼 업데이트
conda update --all
conda update -n base -c defaults conda

# base 가상환경 자동 실행 해제
conda config --set auto_activate_base false
```

![img-29](https://user-images.githubusercontent.com/6462456/150922304-eaaa1232-f047-4695-98f3-7b2b61bb7b11.png){: .shadow}

Anaconda가 잘 설치되었다면 터미널에서 앞에 `(base)` 라는 표시가 생겼음을 확인할 수 있다.  
이는 현재 base(= 기본) 가상환경이 실행되었다는 것을 의미한다.  
만약 터미널 실행 시 자동으로 base 가상환경이 실행되는 것을 방지하려면 `auto_activate_base` 옵션을 `false`로 지정하면 된다.  

```bash
# 새로운 가상환경 생성
conda create -n [가상환경 이름]

# 파이썬 버젼을 명시해 주면서 가상환경 생성
conda create -n [가상환경 이름] python=[파이썬 버젼]

# 생성된 가상환경 복제
conda create --clone [복제되는 가상환경 이름] -n [새로운 가상환경 이름]

# 생성된 가상환경 세팅 목록 확인
conda env list
conda info --envs

# 생성된 가상환경 삭제 (패키지 포함)
conda remove -n [가상환경 이름] --all
```

![img-30](https://user-images.githubusercontent.com/6462456/150922390-e76f32d5-7a34-435f-86c4-4d7d45ade0d7.png){: .shadow}

Anaconda 명령어들은 대부분 `conda`로 시작하며, 용도에 따라 추가로 뒤에 argument가 붙는다.  
`conda create -n [가상환경 이름]`으로 새로운 가상환경을 생성할 수 있으며  
`conda env list`를 통해 생성한 가상환경 목록을 확인할 수 있다.

(-n 옵션은 풀어서 쓰면 `--name`을 의미한다.)  

```bash
# 가상환경 활성화
conda activate [가상환경 이름]

# 가상환경 비활성화
conda deactivate

# 가상환경 삭제
conda env remove -n [가상환경 이름]

# 가상환경 세팅 파일로 추출
conda env export > [파일 이름.yml]
conda env export -n [가상환경 이름] -f [파일 이름.yml]

# 추출된 가상환경 세팅 파일을 토대로 가상환경 생성
conda env create -f [파일 이름.yml]
```

`activate`와 `deactivate`를 통해 가상환경을 활성화하거나, 또는 비활성화할 수 있다.  
보통 비활성화하는 경우는 해당 가상환경이 활성화된 상태에서 주는 명령이므로 이름 없이 deactivate로만 준다고 보면 될 것 같다.  
추가적으로 export로 설정한 가상환경 세팅을 내보내기 할 수 있는데,  
이렇게 생성된 파일을 -f 옵션과 함께 넘겨주면 세팅 그대로 가상환경을 새롭게 생성한다.  
(+ 어쩌다 보니까 안 사실인데, A 환경을 activate 시킨 후 B 환경을 덮어씌우듯이 activate 시키면  
추후 deactivate 시 A 환경으로 돌아가게 된다. 자세한 이유는 찾아봐야 알 것 같긴 함..)

## **🗂 패키지 설치 관련 명령어**

```bash
# anaconda 저장소에 패키지가 존재하는지 검색하기
conda search [패키지 이름]

# 현재 가상환경에 패키지 설치
conda install [패키지 이름]

# 특정 가상환경에 패키지 설치
conda install -n [가상환경 이름] [패키지 이름]

# 설치된 패키지 삭제
conda uninstall [패키지 이름]
```

![img-31](https://user-images.githubusercontent.com/6462456/150922719-8ba01152-4260-4398-8951-c4cbc38e465f.png)

pip를 사용해서 패키지를 설치해 본 경험이 있다면 anaconda를 이용한 방식도 거의 비슷하다는 것을 느낄 수 있다.  
다만, 가상환경별로 패키지가 분리되어 설치되는 방식이므로, 서로 엉킬 수 있는 문제를 방지해 준다.

```bash
# 현재 가상환경에 패키지 설치
conda install [패키지 이름]

# 버젼 명시해서 패키지 설치
conda install [패키지 이름=버젼 이름]

# Dependency 없이 패키지만 설치
conda install --no-deps [패키지 이름]
```

`conda search [패키지 이름]` 명령어를 통해 확인하면 conda 저장소에 패키지의 여러 버젼이 존재하는 것을 확인할 수 있다.  
버젼을 지정하는 경우는 =를 이용해 명령어 옵션을 줄 수 있으며, 생략된 경우 적절한 버젼을 자동으로 선택한다.

## **📒 5. 주요 패키지 설치 관련 팁**

![img-32](https://user-images.githubusercontent.com/6462456/150922806-5eba0d52-78ee-4d33-9b3e-c26d295d3a7f.png)

위에 설명한 대로 `conda install ...`을 통해 패키지를 설치할 수도 있지만,  
가장 문제 없이 원하는 패키지를 설치할 수 있는 방법은 구글에 `conda install [패키지 이름]`을 검색해 보는 것이다.

![img-33](https://user-images.githubusercontent.com/6462456/150922855-0e9490a3-4870-424e-8867-55c9db547ca9.png)

anaconda.org로 이어지는 검색 결과가 있으면 가장 참고하기 편하고,  
아니면 패키지 공식 레퍼런스 문서 쪽에서도 설치 명령어를 명시해 준 경우가 많다.  

```bash
# numpy
conda install -c anaconda numpy

# matplotlib
conda install -c conda-forge matplotlib

# pandas
conda install -c anaconda pandas
```

🔥