---
layout: post
title: 💬 CEOS 15기 프론트엔드 5주차 스터디 발표 자료
date: 2022-05-15 19:00:00 +0900
published: true
categories: [life]
tags: [ceos, frontend, study]
---

안녕하세요. 5주차 발표를 맡은 최어진입니다.  

# 개요

제가 구현한 일부 내용을 중점으로 발표하겠습니다.  
또한 제가 빠뜨린 내용들까지 포함해 알찬 발표 진행해 주신 오민지님, 김채림님께 감사의 말씀을 드립니다.  

# 오늘 소개할 내용

1. React에서의 **Routing** 적용

# React에서의 Routing 적용

그 동안 진행한 미션들은 한 페이지 내에서 URL 이동 없이 웹 애플리케이션을 구현하는 것을 목표로 했는데요, 이번 5주차에는 **여러 페이지를 나누어 애플리케이션의 각 기능을 제공하고 이를 다른 URL로 접근할 수 있도록 하는 것**이 목표였습니다.

## Routing과 SSR

먼저 몇 가지 개념에 대해서 먼저 짚고 넘어가야겠는데요,,,
이번 주차 미션 Key Question으로도 주어진 키워드들입니다.  

일반적으로 우리가 웹사이트를 접속한다고 했을 때,
다른 경로의 URL을 불러오면 다른 페이지로 연결됩니다.  
즉, URL을 변경하면 우리가 보고자 하는 페이지의 내용들이 바뀝니다.  
이처럼 URL에 따라 경로를 추적하여 경로에 맞는 페이지를 보여주는 것을
**라우팅**이라고 할 수 있습니다.

또한 이렇게 라우팅을 통해 URL마다 다른 페이지를 사용자에게 보여줘야 하는 경우
기존의 작동 방식은 서버에서 각 페이지를 모두 만들어서 브라우저에게 전송하고,
이를 브라우저가 사용자에게 보여주게 됩니다.  
이 경우 페이지가 서버에서 만들어진 상태로 보내지므로
**Server-Side Rendering** 방식이라고 합니다.  

## React에서의 Routing?

1. 라우팅 시 새로 보여져야 하는 부분만을 재 렌더링 
2. 리소스를 모두 미리 다운로드받고 Client-Side Rendering

하지만 기존의 웹사이트와 달리 React로 만들어진 애플리케이션은
Single Page Application이기 때문에, 하나의 페이지로만 구성되어 있습니다.  

따라서 SPA에서 Routing을 제공하기 위해서는 각각의 HTML을 구성하는 파일들을
서버에 저장하거나, 혹은 서버에서 동적으로 생성하여 저장하고 다른 URL에 따라
요청하는 방식으로 구현할 수 있습니다.  

> SPA에서 Routing을 하는 순간 Single Page가 아니게 되지 않나요?

Url을 사용하면 하나의 페이지 안에서도 필요한 항목을 사용자가 북마크 처리 하거나,
사용중에 뒤로가기를 눌렀을 때 그 전 페이지로 이동할 수 있게 해 줍니다.  
이런 이유에서 SPA에서의 Routing 필요성을 언급할 수 있겠구요,,  
반박 시 너 말이 맞음  

## React Router v6?

아주 다행스럽게도, 프론트 개발자들이 **당장 오늘 실제로** Routing을
구현하고자 한다면 `react-router` 라이브러리를 바로 갖다 씀으로써
편리하게 구현할 수 있습니다.  

react-router의 핵심 컴포넌트들을 알아볼까요?  

> BrowserRouter

```javascript
import { BrowserRouter } from 'react-router-dom'

import ReactDOM from 'react-dom'

import './index.css'
import App from './App'

ReactDOM.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>,
  document.getElementById('root')
)
```

react-router를 사용하기 위한 가장 첫 번째 작업은,
최상위 애플리케이션을 `BrowserRouter`로 감싸는 것입니다.  

> Route

```javascript
import { Route } from 'react-router-dom'
import Friends from './pages/Friends'
import Chat from './pages/Chat'

function App() {
  return (
    <div>
      <Route path="/friends">
        <Friends />
      </Route>
      <Route path="/chat">
        <Chat />
      </Route>
    </div>
  )
}

export default App
```

그 다음으로는 path property에 따라 다르게 렌더링하고 싶은 컴포넌트들을
`Route`로 감쌉니다.  

> Link

```javascript
import { Link } from 'react-router-dom'

const SideBar = () => {
  return (
    <header>
      <nav>
        <ul>
          <li>
            <Link to="/friends">Friends</Link>
          </li>
          <li>
            <Link to="/chat">Chat</Link>
          </li>
        </ul>
      </nav>
    </header>
  )
}

export default SideBar
```

`Route` 컴포넌트를 통해 라우팅에 따라 다르게 보여지고 싶은 요소를 선택했다면,  
`Link` 태그를 이용해 실제로 라우팅이 이루어져야 하는 페이지로의
이동 기능을 제공할 수 있습니다.  

## 좀 더 깊이 파고 든 react-router 동작 원리

위에서 본 것처럼 `react-router`를 이용해 라우팅을 구현하는 방법은 간단합니다.  
제가 발표자가 아니었다면 신나게 코드를 적용하고 끝났을 테지만 발표자이기 때문에...  
좀 더 동작 원리를 자세히 살펴보도록 하죠..

> react-router vs react-router-dom?

- react-router-dom : react-router v4 버전에서 처음 릴리즈된 라우팅 모듈
- react-router 모듈을 코어로 웹 개발을 위한 `react-router-dom`,  
앱 개발을 위한 `react-router-native`가 나누어 제공

우선 이번 미션을 위해 검색하다가 `react-router-dom`과
`react-router`에 대한 용어가 일부 혼용되어 있는 자료들을 발견하셨을 텐데요,  
정확하게는 react-router-dom 모듈은 react-router 모듈에
dom이 바인딩 되어 있는 모듈이라고 합니다.  

![image](https://user-images.githubusercontent.com/6462456/168460914-706af89b-3679-4c2e-8c7f-46c92599aacf.png)
_모바일에서는...? - React Navigation vs React Router_

- React Navigation은 `react-native-screens`에 의존성을 가짐
- `IOS`의 경우는 `UINavigationController`, `Android`의 경우는
`Fragment`를 이용하는 **Native-Stack Navigator** 구조로
해당 API를 이용한 네이티브 개발 방식과 같은 퍼포먼스를 가짐

> HTML 5 History API

- 현재 탭의 방문 기록을 **Stack 형태**로 메모리 상에서 관리
(이하 **History Stack**)
- History API는 탭 단위로 존재하는 **windows** 전역 객체의
property 및 method들로 제공됨

```javascript
/* properties */
history.length
history.scrollRestoration
history.state
```

- properties  
`history.length` : 현재 페이지를 포함해 방문한 기록의 총 길이  
`history.scrollRestoration` : `auto` | `manual` :  
방문 기록을 탐색할 때 스크롤 위치를 원래 위치로 복원할 지의 여부  
`history.state` : History Stack의 최상단에 위치한 상태 값  

```javascript
/* methods */
history.go([delta])
history.back()
history.forward()
```

- methods  
`history.go([delta])` : 현재 페이지를 기준으로, **상대적인 위치에 존재하는 방문 기록 내 페이지로 이동**  
`history.back()` : 방문 기록의 **바로 뒤 페이지로 이동**  
`history.forward()` : 방문 기록의 **바로 앞 페이지로 이동**  

```javascript
/* methods */
history.pushState(state, title[, url])
history.back()
history.forward()
```
`history.pushState(state, title[, url])` :  
주어진 상태 값을 **History Stack에 추가**  
`history.replaceState(state, title[, url])` :  
History Stack의 **제일 최근 항목을 주어진 상태 값으로 대체**  

_참고로, 브라우저의 새로고침(= location.reload() 함수의 호출)은 추가적인 방문 기록을 Push 하지 않는다._

```javascript
/* event */
.onpopstate = (event) => {...}
```

- event  
`popstate` : 사용자의 방문 기록 탐색으로 인해
현재 활성화되는 기록 항목이 바뀔 때 발생  

```javascript
window.onpopstate = function (event) {
    console.log('location: ' + document.location + ', state: ' + JSON.stringify(event.state));
};

history.pushState({page: 1}, 'title 1', '?page=1');
history.pushState({page: 2}, 'title 2', '?page=2');
history.replaceState({page: 3}, 'title 3', '?page=3');
history.back();
// Logs "location: http://example.com/example.html?page=1, state: {"page":1}"
history.back();
// Logs "location: http://example.com/example.html, state: null"
history.go(2);
// Logs "location: http://example.com/example.html?page=3, state: {"page":3}"
```

> Node.js의 History 패키지

![image](https://user-images.githubusercontent.com/6462456/168462542-019845fd-0390-4464-953f-a7600fce23a8.png)
_https://github.com/remix-run/history/blob/28c89f4091ae9e1b0001341ea60c629674e83627/docs/api-reference.md_

- Session의 History를 다루는 방법을 구동 환경을 기준으로 세 가지로 나눠서 제공  
`createBrowserHistory`  <-  이 놈 주목  
`createHashHistory`    
`createMemoryHistory`

_history API를 기반으로 구현되는 history 객체를 다루는 방식에만 주목_

> BroswerRouter

![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbQoWT9%2FbtqNqdkcKIF%2FUOhoaTws6GK4m0jUeFPucK%2Fimg.png)
_Overall Structure in react-router-dom_

- 우선적으로 history 패키지의 `createBrowserHistory()` 함수를 호출함으로써 history 객체가 생성
- `BrowserRouter` 컴포넌트가 `Router` 컴포넌트를 렌더링할 때  
`props`로 history 객체 전달

> (BrowserRouter 내의) Router

- 마운트되는 순간에 `props`로 전달받은 history 객체 내 location 객체를 자신의 지역 상태에 저장
- `history.listen()`을 이용해 `props`로 전달 받은 history 객체를 구독해 현재 URL이 변경될 때마다 지역 상태의 location 객체를 갱신
- Router 컴포넌트는 현재의 URL과 관련된 몇몇 정보들(match 객체, location 객체, history 객체)을 Context로 구성해서 해당 Context의 `RouterContext.Provider`를 렌더링

> Route

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FpVUsh%2FbtqNmcG9d5u%2FF6P0Hixg6eSt2S9vk8h1x0%2Fimg.png)
_Overall Structure in Route Component_

- `props`로 전달받는 path의 값이 브라우저의 현재 URL과 매칭 될 때
함께 명시된 **특정 컴포넌트를 렌더링 하는 컴포넌트**
- `RouterContext.Consumer` 컴포넌트를 렌더링함으로써
`RouterContext` 참조
- `RouterContext`의 location 객체 정보와 props로 전달받은 path 값 비교  
**매칭 O** -> props로 **전달받은 컴포넌트**를 렌더링  
**매칭 X** -> **null**을 렌더링 

> Switch(v5) -> Routes(v6)

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FkT8DE%2FbtqNouA0hXr%2FQiZXsIGiQTJ6NpwVYiHV6k%2Fimg.png)
_Overall Structure in Switch(Routes) Component_

-  브라우저의 현재 URL과 매칭 되는 첫 번째 `Route` 자식 Element를
렌더링하는 컴포넌트
- `RouterContext.Consumer` 컴포넌트를 렌더링함으로써 `RouterContext` 참조
- `RouterContext`의 location 객체 정보와 props로 전달받은
각 자식 Element의 path props 정보를 하나씩 비교  
**매칭 O** -> 첫 번째로 매칭되는 `Route` Children Element를 렌더링

> Link

- **Page Reloading 없이 Navigation을 수행**하는 컴포넌트
- 결과적으로는 일반적인 `a` 태그로 렌더링 되지만...  
1. 먼저 `preventDefault()` 함수를 호출해 `a` 태그의 기본 동작 막음
2. 그 대신 `RouterContext`에 존재하는 history 객체를 이용하여 내비게이션을 수행하도록 구현

> 결론 (세 줄 요약)

1. `Router` 컴포넌트의 지역 상태에는 history.location 객체가 존재하며
history.listen() 메커니즘에 의해 항상 최신 상태로 관리됨
2. 이 정보가 바뀔 때마다 `Router`컴포넌트가 Re-Rendering되며
하위 컴포넌트까지 함께 Re-Rendering되도록 만듦
3. location 객체와 Matching한 결과를 바탕으로 `Switch`의 경우는
자식 엘리먼트들 중 Matching된 컴포넌트를, `Route` 컴포넌트는 함께 명시된 컴포넌트를 렌더링하며  
match 객체, location 객체, history 객체를 렌더링 할 컴포넌트에게 넘겨줌

## 몇 가지 생각해 볼 만한 주제들

> v5 -> v6로의 변화?

> Link 컴포넌트가 아니라 HTML의 anchor 태그를 이용해 이동한다면?

> URL matching

## 적용 가능한 몇 가지 패턴

> Nested Routing

> Sidebar CSS Styling

---

# 참고 자료

- https://www.reimaginer.me/entry/spa-and-spa-routing
- https://serzhul.io/REACT/싱글페이지-어플리케이션-라우팅(single-page-application-routing)/
- https://it-eldorado.tistory.com/111
- https://it-eldorado.tistory.com/113
- https://velog.io/@devstone/react-router-dom-이해하고-활용하기
- https://velog.io/@function_dh/HTML5-history-API-브라우저-이동