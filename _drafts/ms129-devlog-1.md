---
layout: post
title: 📷 머선129 개발 로그 1. 레이아웃 구성/그래디언트 및 그림자/카메라 입력/앨범 불러오기/애니메이션
date: 2022-01-28 15:03:00 +0900
published: true
categories: [projects, ms129]
tags: [project, ms129, react native, expo]
---

## **📋 1. 전체적인 UX/UI 레이아웃 구성**

### **💻 A. 네비게이션 구성**

[https://reactnavigation.org/docs/getting-started](https://reactnavigation.org/docs/getting-started)  

전체적인 화면 구성 및 이동은 `React Navigation`을 사용해서 구현했다.  
`React Native`의 특징 중 하나가 핵심 라이브러리들 중에서
커뮤니티에 의존하는 경향이 있다는 점인데, 대표적인 게 `React Navigation`이다.  
공식 Expo Documentation에서도 Navigation에 대해서 `React Navigation`으로 링크를 제공하고 있다.  

```javascript
import React, {Component} from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';

import MainScreen from './MainScreen';
import SelectScreen from './SelectScreen';
import CameraInputScreen from './CameraInputScreen';
import AlbumInputScreen from './AlbumInputScreen';
import InputConfirmScreen from './InputConfirmScreen';
import ResultScreen from './ResultScreen';
import GalleryScreen from './GalleryScreen';
import TutorialScreen from './TutorialScreen';
import TestScreen from './TestScreen';

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator screenOptions={{headerShown : false}}>
        <Stack.Screen name="Home" component={MainScreen} />
        <Stack.Screen name="Select" component={SelectScreen} />
        <Stack.Screen name="CameraInput" component={CameraInputScreen} />
        <Stack.Screen name="AlbumInput" component={AlbumInputScreen} />
        <Stack.Screen name="InputConfirm" component={InputConfirmScreen} />
        <Stack.Screen name="Result" component={ResultScreen} />
        <Stack.Screen name="Gallery" component={GalleryScreen} />
        <Stack.Screen name="Tutorial" component={TutorialScreen} />
        <Stack.Screen name="Test" component={TestScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```
{: file='App.js'}

`React Navigation`을 사용함으로써
앱을 구성하는 여러 스크린들을 각각 다른 .js 파일로 관리할 수 있다.  
우선, `createNativeStackNavigator`를 선언한 후
_App.js_에서 위와 같이 각 _*Screen.js_를 import해 `Stack.screen`으로 `NavigationContainer` 안에 포함해 준다.  
여기서 `name`으로 지정한 값들을 이용해 나중에 다른 스크린으로의 이동을 호출할 수 있다.  

```javascript
navigation.push()
// onPress={() => navigation.push('Gallery')}>

navigation.goBack()
```

다른 스크린으로 이동하는 경우 `navigation.push()` 안에
위에서 지정한 `name`을 포함해 호출할 수 있다.  
`StackScreen`이라는 이름에서 알 수 있듯이, 호출이 이루어지는 경우
화면을 호출한 히스토리가 남아 있다.  
이 경우 현재 스크린을 호출하기 전 스크린으로 돌아가고자 하는 경우
`navigation.goBack()`을 호출하면 된다.  

### **💻 B. 아이콘 및 스플래시 이미지 적용**

![img-19](https://user-images.githubusercontent.com/6462456/151497908-3f5007f3-15b4-465b-9cc0-978159c97e44.png)

_assets/_ 폴더 내부를 확인하면 위처럼 _icon.png_ 와 _splash.png_ 가 존재하는 것을 확인할 수 있다.  
이 파일들을 교체해 주면 된다.  

![img-20](https://user-images.githubusercontent.com/6462456/151497915-02712254-2e74-46de-b227-cc82cccbc63b.png){: width="250px"}

아이콘 같은 경우는 사실 [안드로이드 아이콘 디자인 가이드](https://developer.android.com/google-play/resources/icon-design-specifications?hl=ko)를 보고 
디자인했어야 하는데
일단 정사각형 규격으로 디자인만 해놓고 나중에 다시 수정하자는 생각으로 박았다.  

![img-21](https://user-images.githubusercontent.com/6462456/151497918-93fc1b8e-7955-4eaa-ac58-78422f73a170.png){: width="350px"}

스플래시 이미지 또한 디자인프로젝트 시연 때 아이폰 X로 돌릴 생각이었기 때문에
아이폰 X 사이즈로 맞추어 만들었다.

![img-22](https://user-images.githubusercontent.com/6462456/151498158-f31f3f86-71fa-4cc1-9f26-6c4b26d13e8c.png){: width="400px"}
![img-23](https://user-images.githubusercontent.com/6462456/151498159-25fa0f33-5a09-4f84-831d-f4fa15fba2a1.png){: width="500px"}

다시 프로젝트 폴더로 올라와서 _app.json_ 파일을 열면
splash 하위에 `resizeMode`와 `backgroundColor`가 존재한다.  
이를 통해, 만들어놓은 _splash.png_ 를 적용하는 과정에서
각 디바이스 별 크기에 의해 _splash.png_가 다르게 보여질 경우
생기는 여백을 어떻게 조정할 지 설정할 수 있다.  
(참고 : [https://docs.expo.dev/guides/splash-screens/](https://docs.expo.dev/guides/splash-screens/))

## **📋 2. 메인 화면 구현**

메인 화면은 위와 같이 구현했다.  
사각형 ㅇㅓ떻게 구현했는지, 그래디언트, 그림자 등도 추가하공ㅇ

<!-- ### **💻 A. 그래디언트 박스**
### **💻 B. 자연스러운 그림자 효과**
### **💻 C. 반응형 배치 구현**

## **📋 3. 입력 화면 구현**

### **💻 A. 카메라 촬영하기**
### **💻 B. 앨범에서 불러오기**

## **📋 3. 입력 확인 화면 구현**

### **💻 A.**
### **💻 B.**

## **📋 4. 선택 화면 구현**

### **💻 A.**
### **💻 B.**

## **📋 5. 결과 화면 구현**

### **💻 A.**
### **💻 B.**

## **📋 6. 튜토리얼/개발진 화면 구현**

### **💻 A. ** -->