---
layout: post
title: 💻 OpenCV C++ 개발환경 설정 (Windows/Mac OS)
date: 2022-03-17 02:43:00 +0900
published: true
categories: [coding, c++]
tags: [coding, c++, opencv, visual studio, xcode]
---

## **개요**

2022-1학기에 **디지털영상처리개론** 수업을 들으면서
`OpenCV`를 이용한 과제들을 수행할 필요가 생겼다.  

작년 여름방학에 연구실 DIP 세미나 준비하면서 한 번 Xcode로 개발 환경을 세팅한 적이 있긴 했는데
Windows보다는 몇 가지 자잘하게 세팅해야 하는 부분들이 있었다.  
그래서 이번에 다시 과제 제출용으로 프로젝트 생성하면서
Windows/Mac OS에서의 OpenCV 개발환경 세팅 방법을
포스팅으로 정리해보기로 했다.  

## **OpenCV?**

![OpenCV_Logo](https://user-images.githubusercontent.com/6462456/158492094-87e827aa-95be-409e-9c4f-1a2cd4d98bc0.png)
_OpenCV_

**OpenCV**는 Real-Time Image Processing과
Computer Vision 기술들을 다루는 데 있어서  
매우x3 편리한 C++ 라이브러리이다.  
C++로 구현되어 있지만 Python, Java로도 Full Interface를 제공한다.  

Image Processing 관련 코드 구현이나
관련 질문 글들을 구글링해보면 거의 모든 코드가
OpenCV에서 제공하는 함수들을 가져다 사용하는 걸 볼 수 있다.  
그만큼 편리한데 성능도 매우 빠르다.  

## **Installation (Windows)**

### 1. Microsoft Visual Studio 2022 설치

![visual_studio_download](https://user-images.githubusercontent.com/6462456/158091530-1d0173b0-90ed-4cc4-b453-61fa88a35185.png)
_Microsoft Visual Studio_

> [Visual Studio 2022 다운로드 (공식)](https://visualstudio.microsoft.com/ko)

Windows 환경에서는 **Microsoft Visual Studio**를 사용하는 것으로 권장된다.  
위의 공식 홈페이지에서 Community 2022 버젼을 다운로드받는다.  

![workload_select_cpp](https://user-images.githubusercontent.com/6462456/158091563-1df21ff4-c032-46a5-ab3e-654373c85994.png)

설치를 선택하면 위의 **워크로드** 항목에서
설치할 개별 구성 요소를 선택하는 부분이 있는데
**C++을 사용한 데스크톱 개발**만 체크해주고 넘어가면 된다.  
기본 IDE에 구성 요소 설치까지 용량이 꽤 크기 때문에
자기가 여유 있다고 생각하는 파티션으로 설치 위치를 변경해주면 좋다. (기본은 C드라이브)  

설치에는 평균 한 **20~30분** 정도가 소요된다.  
설치가 완료되면 Microsoft 계정으로 로그인하라는 메세지가 뜬다.  
당장은 로그인을 하지 않아도 문제가 없으나
30일 뒤부터는 Community 라이센스가 만료되었다는 알림과 함께 로그인을 해야만
계속 무료로 사용 가능하므로 귀찮지만 지금 로그인해 두는 게 낫다...  

### 2. 새 CMake 프로젝트 생성

![111](https://user-images.githubusercontent.com/6462456/158652100-78dd5e7b-421f-40bc-9eb0-88fa630336aa.JPG)

설치가 완료되면 새로운 프로젝트를 생성한다.  
프로젝트 형식은 **CMake 프로젝트**를 골라 준다.  
잠시 기다리면 헤더(.h) 파일과 소스 파일(.cpp)를 포함한
프로젝트 폴더가 생성된다.  

![222](https://user-images.githubusercontent.com/6462456/158652114-6b10cedd-6438-4346-a0ec-8c2aede620ff.JPG)

### 3. OpenCV 라이브러리 설치

> [OpenCV 라이브러리 다운로드](https://opencv.org/releases)

그 다음으로는 잠시 Visual Studio를 내려 놓고
위의 OpenCV 공식 홈페이지로 들어간다.  
맨 위에 **Latest Release**의 **Windows** 버튼을 통해
인스톨러 프로그램을 다운받는다.  

인스톨러를 실행시키면 선택한 경로에 라이브러리 패키지가 압축 해제된다.  
압축 해제된 폴더는 크게 `source`와 `build` 2개인데,
당장 필요한 건 이미 빌드된 라이브러리 파일이므로 `build` 폴더만 복사한다.  

![333](https://user-images.githubusercontent.com/6462456/158652120-61350b01-02cb-4d6a-b961-ab0016f2a4b4.JPG)

> C:₩opencv-sources₩**build**

C드라이브 바로 하위에 `opencv-sources`라는 빈 폴더를 만든 후
그 안에 아까 복사한 `build` 폴더를 붙여넣기한다.  
build 폴더의 크기가 1GB를 좀 넘기 때문에 용량 문제로 대신
D드라이브에 만들겠다 싶은 사람들은 상관 없지만,
프로젝트 빌드 설정 파일들(예시 : `CMakeList.txt`)에서 경로를 일치하도록 신경 써야 한다.  

### 4. CMake 프로젝트에서 OpenCV 라이브러리 불러오기

![444](https://user-images.githubusercontent.com/6462456/158652127-239c63da-52e4-474e-a216-93515215b3d3.JPG)

```text
cmake_minimum_required(VERSION 3.0)
set(opencv_DIR "C:/opencv-sources/build")
find_package(opencv)
include_directories(${OpenCV_INCLUDE_DIRS})

get_filename_component(ProjectId ${CMAKE_CURRENT_LIST_DIR} NAME)
string(REPLACE " " "_" ProjectId ${ProjectId})
project(${ProjectId} C CXX)

set(CMAKE_CXX_STANDARD 11)
file(GLOB SOURCES *.cpp)

add_executable(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBRARIES})
```
{: file='CMakeList.txt'}

이제 다시 Visual Studio로 돌아간다.  
그 다음 `CMakeList.txt` 파일의 내용을 위와 같이 수정한다.  
만약 바로 전 단계에서 용량 확보 등의 문제로
`C:₩opencv-sources₩build` 대신 다른 경로로 붙여넣은 사람들은
두 번쨰 줄 경로 부분을 그에 맞게 수정해 줘야 한다.  

이는 컴파일 및 빌드 단계에서 아까 옮겨놓은
OpenCV 라이브러리 빌드 파일을 포함하기 위한 CMake 설정이다.  

### 5. 프로젝트 빌드

```c++
#include "opencv2/opencv.hpp"
#include <iostream>

using namespace std;
using namespace cv;

int main(int, char**)
{
   Mat img_in = imread("Test.tif", IMREAD_GRAYSCALE);

   int H = img_in.rows;
   int W = img_in.cols;

   if (img_in.empty())
   {
      cout << "Image does not exist." << endl;
      return 1;
   }

   for (int i = 0; i < H; i++)
   {
      img_in.at<uchar>(i, 20) = 255;
   }

   imwrite("Save.tif", img_in);
   return 0;
}
```
{: file='main.cpp'}

![555](https://user-images.githubusercontent.com/6462456/158652129-09bf1ada-0d12-4545-87fc-f1bcc6e381d4.JPG)
_Cameraman(Before) / Cameraman(After)_

Visual Studio 환경에서 OpenCV 라이브러리를 이용해
컴파일 및 빌드를 진행할 수 있는 환경 구축을 모두 끝냈다.  
**Control + F5**로 간단한 예제 코드를 실행시키면
OpenCV에서 제공하는 기능이 잘 동작함을 확인할 수 있다.  

## **Installation (Mac OS)**

### 1. Xcode 설치

![img-24](https://user-images.githubusercontent.com/6462456/158518602-3d631d0a-b480-4099-8f05-43d9583b46ff.png)

Mac OS 환경에서는 **Xcode**를 사용해서 프로젝트를 빌드하는 방법을 설명한다.
Xcode가 깔려 있는 사람은 넘어가고
깔려 있지 않은 사람은 App Store에서 설치해주면 된다.  

![img-26](https://user-images.githubusercontent.com/6462456/158518597-010d4ddd-f045-434d-941b-f12e00d80847.png){: width="350px" class="normal"}
![img-25](https://user-images.githubusercontent.com/6462456/158518599-44ec4790-c54d-4333-bcaa-49c43cc018ea.png){: width="350px" class="normal"}

### 2. Homebrew를 통한 패키지 설치

```zsh
brew install git
brew install opencv
brew install pkg-config
```

> [Homebrew 설치](https://brew.sh)

그 다음으로는 **Homebrew**를 사용해서 OpenCV를 설치해주면 된다.  
Homebrew는 Mac OS에서 여러 패키지들을 편리하게 설치하고
관리할 수 있는 패키지 관리자인데,
만약 깔려 있지 않다면 위의 링크를 통해 `brew`를 먼저 설치해야 한다.  

Homebrew 설치가 끝나고 나면
위의 명령어들을 통해 필요한 패키지들을 설치한다.  
설치가 끝나고 나면 `brew list`를 실행시켜
패키지들이 잘 설치되었는지 확인한다.  

![img-28](https://user-images.githubusercontent.com/6462456/158518592-9cbd9241-7dc9-42a4-848b-0646fa3b21fa.png)

### 3. 새 Command Line Tool 프로젝트 생성

Xcode 설치가 완료되었다면 **Command Line Tool**로 새 프로젝트를 생성한다.  

![img-29](https://user-images.githubusercontent.com/6462456/158518591-fee0c637-bcca-4993-a4b4-259628143cfc.png)

### 4. Xcode 프로젝트에서 OpenCV 라이브러리 불러오기

> /usr/local/Cellar/opencv/**o.o.o_o(본인 설치 버젼)**/include/opencv4

```zsh
# OpenCV 설치 경로 확인
ls /usr/local/Cellar/opencv
```

Xcode 프로젝트 생성 후 **프로젝트명 - Build Setting**으로 진입하면
탭 바로 밑에 검색창이 있다.  
이 검색창에 **Header Search Paths**를 검색한 후
해당 옵션이 나오면 위의 경로를 추가한다.  
**중요한 점**은 자신의 설치 버젼을 확인하고 경로에 그 버젼을 맞춰서 적어줘야 한다는 점인데,
위 명령어를 통해 자신의 설치 버젼을 확인할 수 있다.  

![img-30](https://user-images.githubusercontent.com/6462456/158518590-1876684f-112a-4cba-abc2-23aca66c22d3.png)

> /usr/local/Cellar/opencv/**o.o.o_o(본인 설치 버젼)**/lib

이번에는 **Library Search Paths**를 검색한 후,
옵션이 나오면 위의 경로를 추가한다.  
아까와 마찬가지로 본인 버젼에 맞게 경로에 포함한다.  

![img-31](https://user-images.githubusercontent.com/6462456/158518589-69c0e02b-3ed5-4f1e-9dd4-10f20a2810df.png)

이번에는 검색창에 **other linker**라고 쳐 보자.  
**Linking** 항목의 **Other Linker Flags** 하위 항목을 발견할 수 있다.  

![img-27](https://user-images.githubusercontent.com/6462456/158518595-b799e773-57af-4ad5-aaa6-92545e20fc7a.png)

```zsh
# 링크 플래그 확인
pkg-config --cflags --libs /usr/local/Cellar/o.o.o_o(본인 설치 버젼)/lib/pkgconfig/opencv4.pc
```

터미널에 위 명령어를 치면 링크 플래그들을 추출할 수 있다.
출력되어 나오는 긴 텍스트들을 싹 긁어서 복사한다.  
그 다음 아까 Xcode에서 검색했던 **Other Linker Flags** 항목에
복사한 값을 붙여넣기 해서 추가해 주면 된다.  

![img-32](https://user-images.githubusercontent.com/6462456/158518584-bb2c3723-5473-452e-adf8-8d0efba002a6.png)

거의 다 끝났다.  
이번에는 상단 **Product>Scheme>Edit Scheme**를 클릭한 후,
**Options** 탭의 **Use custom working directory**를 체크한다.  
아래의 칸 오른쪽 버튼을 누르면 디렉토리 선택 창이 열리는데,
쭉 타고 들어가다가 Xcode 프로젝트를 통해 생성된 `main.cpp`가 존재하는
경로를 발견할 수 있다. 동일 디렉토리 안까지 타고 들어가서 선택 버튼을 누른다.  

![img-33](https://user-images.githubusercontent.com/6462456/158518578-ba383ec6-4855-4a16-babe-b5914c05ca8f.png)

**여기까지 했으면 끝!!**  
이어야 하지만... 컴파일 시 `_abort_with_payload` 에러가 자꾸 떠서 당황했다.  
구글링하니까 **Signing & Capabilities - Hardened Runtime** 항목의
**Disable Library Validation**을 체크하지 않아서 발생하는 문제라고 한다.  
해결하는 데 오래 걸리진 않았지만,
포스팅을 보는 분들의 시간 낭비를 막기 위해 함께 적는다.  

### 5. 프로젝트 빌드

![image](https://user-images.githubusercontent.com/6462456/158631156-14a9b4a7-a48d-44d0-b688-eae9352a1c54.png)

**Command + R**을 통해 컴파일이 잘 이루어진 모습이다.  

## **참고 링크**

1. [https://www.vbflash.net/83](https://www.vbflash.net/83)  
2. [https://velog.io/@chy0428/opencv-install-for-mac](https://velog.io/@chy0428/opencv-install-for-mac)

## **끝으로...**

간단히 C++을 통한 OpenCV 개발 환경을 구축해봤다.  
인터넷에서 OpenCV에 관한 스택오버플로우 질문이나 포럼 글들을 읽다 보면
요즘은 Python을 더 많이 쓰는 느낌이다.  

Python으로 OpenCV 환경을 설정하려면
간단하게 Anaconda로 `cv2`를 설치하는 것만으로 간단하기도 하고,  
Vision 분야의 딥 러닝 연구 같은 경우
Python 라이브러리들을 많이 쓰니까 그런가 싶기도 하다.  

어쨌든, 이 수업에서 C++을 사용하는 이유는
간단히 라이브러리 기능을 이용해서 할 수도 있는 영상 처리 기법들을
직접 함수로 구현하고 깨닫기 위함이 이 수업의 목적이고,  
그 목적에는 Python보다 C++이 적절하다고 교수님은 생각하신 게 아닐까..?  

어쨌든, 이걸로 인트로를 마치고
추후 중요하다고 생각되는 개념들은 실습이 끝날 때마다
따로 계속 포스팅할 예정이다.

📷  
