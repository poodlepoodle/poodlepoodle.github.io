---
layout: post
title: ๐ท ๋จธ์ 129 ๊ฐ๋ฐ ๋ก๊ทธ 1. ๋ ์ด์์ ๊ตฌ์ฑ/๊ทธ๋๋์ธํธ ๋ฐ ๊ทธ๋ฆผ์/์นด๋ฉ๋ผ ์๋ ฅ/์จ๋ฒ ๋ถ๋ฌ์ค๊ธฐ/์ ๋๋ฉ์ด์
date: 2022-01-28 15:03:00 +0900
published: true
categories: [projects, ms129]
tags: [project, ms129, react native, expo]
---

## **๐ 1. ์ ์ฒด์ ์ธ UX/UI ๋ ์ด์์ ๊ตฌ์ฑ**

### **๐ป A. ๋ค๋น๊ฒ์ด์ ๊ตฌ์ฑ**

[https://reactnavigation.org/docs/getting-started](https://reactnavigation.org/docs/getting-started)  

์ ์ฒด์ ์ธ ํ๋ฉด ๊ตฌ์ฑ ๋ฐ ์ด๋์ `React Navigation`์ ์ฌ์ฉํด์ ๊ตฌํํ๋ค.  
`React Native`์ ํน์ง ์ค ํ๋๊ฐ ํต์ฌ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ค ์ค์์
์ปค๋ฎค๋ํฐ์ ์์กดํ๋ ๊ฒฝํฅ์ด ์๋ค๋ ์ ์ธ๋ฐ, ๋ํ์ ์ธ ๊ฒ `React Navigation`์ด๋ค.  
๊ณต์ Expo Documentation์์๋ Navigation์ ๋ํด์ `React Navigation`์ผ๋ก ๋งํฌ๋ฅผ ์ ๊ณตํ๊ณ  ์๋ค.  

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

`React Navigation`์ ์ฌ์ฉํจ์ผ๋ก์จ
์ฑ์ ๊ตฌ์ฑํ๋ ์ฌ๋ฌ ์คํฌ๋ฆฐ๋ค์ ๊ฐ๊ฐ ๋ค๋ฅธ .js ํ์ผ๋ก ๊ด๋ฆฌํ  ์ ์๋ค.  
์ฐ์ , `createNativeStackNavigator`๋ฅผ ์ ์ธํ ํ
_App.js_์์ ์์ ๊ฐ์ด ๊ฐ _*Screen.js_๋ฅผ importํด `Stack.screen`์ผ๋ก `NavigationContainer` ์์ ํฌํจํด ์ค๋ค.  
์ฌ๊ธฐ์ `name`์ผ๋ก ์ง์ ํ ๊ฐ๋ค์ ์ด์ฉํด ๋์ค์ ๋ค๋ฅธ ์คํฌ๋ฆฐ์ผ๋ก์ ์ด๋์ ํธ์ถํ  ์ ์๋ค.  

```javascript
navigation.push()
// onPress={() => navigation.push('Gallery')}>

navigation.goBack()
```

๋ค๋ฅธ ์คํฌ๋ฆฐ์ผ๋ก ์ด๋ํ๋ ๊ฒฝ์ฐ `navigation.push()` ์์
์์์ ์ง์ ํ `name`์ ํฌํจํด ํธ์ถํ  ์ ์๋ค.  
`StackScreen`์ด๋ผ๋ ์ด๋ฆ์์ ์ ์ ์๋ฏ์ด, ํธ์ถ์ด ์ด๋ฃจ์ด์ง๋ ๊ฒฝ์ฐ
ํ๋ฉด์ ํธ์ถํ ํ์คํ ๋ฆฌ๊ฐ ๋จ์ ์๋ค.  
์ด ๊ฒฝ์ฐ ํ์ฌ ์คํฌ๋ฆฐ์ ํธ์ถํ๊ธฐ ์  ์คํฌ๋ฆฐ์ผ๋ก ๋์๊ฐ๊ณ ์ ํ๋ ๊ฒฝ์ฐ
`navigation.goBack()`์ ํธ์ถํ๋ฉด ๋๋ค.  

### **๐ป B. ์์ด์ฝ ๋ฐ ์คํ๋์ ์ด๋ฏธ์ง ์ ์ฉ**

![img-19](https://user-images.githubusercontent.com/6462456/151497908-3f5007f3-15b4-465b-9cc0-978159c97e44.png)

_assets/_ ํด๋ ๋ด๋ถ๋ฅผ ํ์ธํ๋ฉด ์์ฒ๋ผ _icon.png_ ์ _splash.png_ ๊ฐ ์กด์ฌํ๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.  
์ด ํ์ผ๋ค์ ๊ต์ฒดํด ์ฃผ๋ฉด ๋๋ค.  

![img-20](https://user-images.githubusercontent.com/6462456/151497915-02712254-2e74-46de-b227-cc82cccbc63b.png){: width="250px"}

์์ด์ฝ ๊ฐ์ ๊ฒฝ์ฐ๋ ์ฌ์ค [์๋๋ก์ด๋ ์์ด์ฝ ๋์์ธ ๊ฐ์ด๋](https://developer.android.com/google-play/resources/icon-design-specifications?hl=ko)๋ฅผ ๋ณด๊ณ  
๋์์ธํ์ด์ผ ํ๋๋ฐ
์ผ๋จ ์ ์ฌ๊ฐํ ๊ท๊ฒฉ์ผ๋ก ๋์์ธ๋ง ํด๋๊ณ  ๋์ค์ ๋ค์ ์์ ํ์๋ ์๊ฐ์ผ๋ก ๋ฐ์๋ค.  

![img-21](https://user-images.githubusercontent.com/6462456/151497918-93fc1b8e-7955-4eaa-ac58-78422f73a170.png){: width="350px"}

์คํ๋์ ์ด๋ฏธ์ง ๋ํ ๋์์ธํ๋ก์ ํธ ์์ฐ ๋ ์์ดํฐ X๋ก ๋๋ฆด ์๊ฐ์ด์๊ธฐ ๋๋ฌธ์
์์ดํฐ X ์ฌ์ด์ฆ๋ก ๋ง์ถ์ด ๋ง๋ค์๋ค.

![img-22](https://user-images.githubusercontent.com/6462456/151498158-f31f3f86-71fa-4cc1-9f26-6c4b26d13e8c.png){: width="400px"}
![img-23](https://user-images.githubusercontent.com/6462456/151498159-25fa0f33-5a09-4f84-831d-f4fa15fba2a1.png){: width="500px"}

๋ค์ ํ๋ก์ ํธ ํด๋๋ก ์ฌ๋ผ์์ _app.json_ ํ์ผ์ ์ด๋ฉด
splash ํ์์ `resizeMode`์ `backgroundColor`๊ฐ ์กด์ฌํ๋ค.  
์ด๋ฅผ ํตํด, ๋ง๋ค์ด๋์ _splash.png_ ๋ฅผ ์ ์ฉํ๋ ๊ณผ์ ์์
๊ฐ ๋๋ฐ์ด์ค ๋ณ ํฌ๊ธฐ์ ์ํด _splash.png_๊ฐ ๋ค๋ฅด๊ฒ ๋ณด์ฌ์ง ๊ฒฝ์ฐ
์๊ธฐ๋ ์ฌ๋ฐฑ์ ์ด๋ป๊ฒ ์กฐ์ ํ  ์ง ์ค์ ํ  ์ ์๋ค.  
(์ฐธ๊ณ  : [https://docs.expo.dev/guides/splash-screens/](https://docs.expo.dev/guides/splash-screens/))

## **๐ 2. ๋ฉ์ธ ํ๋ฉด ๊ตฌํ**

๋ฉ์ธ ํ๋ฉด์ ์์ ๊ฐ์ด ๊ตฌํํ๋ค.  
์ฌ๊ฐํ ใใ๋ป๊ฒ ๊ตฌํํ๋์ง, ๊ทธ๋๋์ธํธ, ๊ทธ๋ฆผ์ ๋ฑ๋ ์ถ๊ฐํ๊ณตใ

<!-- ### **๐ป A. ๊ทธ๋๋์ธํธ ๋ฐ์ค**
### **๐ป B. ์์ฐ์ค๋ฌ์ด ๊ทธ๋ฆผ์ ํจ๊ณผ**
### **๐ป C. ๋ฐ์ํ ๋ฐฐ์น ๊ตฌํ**

## **๐ 3. ์๋ ฅ ํ๋ฉด ๊ตฌํ**

### **๐ป A. ์นด๋ฉ๋ผ ์ดฌ์ํ๊ธฐ**
### **๐ป B. ์จ๋ฒ์์ ๋ถ๋ฌ์ค๊ธฐ**

## **๐ 3. ์๋ ฅ ํ์ธ ํ๋ฉด ๊ตฌํ**

### **๐ป A.**
### **๐ป B.**

## **๐ 4. ์ ํ ํ๋ฉด ๊ตฌํ**

### **๐ป A.**
### **๐ป B.**

## **๐ 5. ๊ฒฐ๊ณผ ํ๋ฉด ๊ตฌํ**

### **๐ป A.**
### **๐ป B.**

## **๐ 6. ํํ ๋ฆฌ์ผ/๊ฐ๋ฐ์ง ํ๋ฉด ๊ตฌํ**

### **๐ป A. ** -->