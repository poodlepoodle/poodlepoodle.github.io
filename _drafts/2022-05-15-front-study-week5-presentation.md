---
layout: post
title: ๐ฌ CEOS 15๊ธฐ ํ๋ก ํธ์๋ 5์ฃผ์ฐจ ์คํฐ๋ ๋ฐํ ์๋ฃ
date: 2022-05-15 19:00:00 +0900
published: true
categories: [life]
tags: [ceos, frontend, study]
---

์๋ํ์ธ์. 5์ฃผ์ฐจ ๋ฐํ๋ฅผ ๋งก์ ์ต์ด์ง์๋๋ค.  

# ๊ฐ์

์ ๊ฐ ๊ตฌํํ ์ผ๋ถ ๋ด์ฉ์ ์ค์ ์ผ๋ก ๋ฐํํ๊ฒ ์ต๋๋ค.  
๋ํ ์ ๊ฐ ๋น ๋จ๋ฆฐ ๋ด์ฉ๋ค๊น์ง ํฌํจํด ์์ฐฌ ๋ฐํ ์งํํด ์ฃผ์  ์ค๋ฏผ์ง๋, ๊น์ฑ๋ฆผ๋๊ป ๊ฐ์ฌ์ ๋ง์์ ๋๋ฆฝ๋๋ค.  

# ์ค๋ ์๊ฐํ  ๋ด์ฉ

1. React์์์ **Routing** ์ ์ฉ

# React์์์ Routing ์ ์ฉ

๊ทธ ๋์ ์งํํ ๋ฏธ์๋ค์ ํ ํ์ด์ง ๋ด์์ URL ์ด๋ ์์ด ์น ์ ํ๋ฆฌ์ผ์ด์์ ๊ตฌํํ๋ ๊ฒ์ ๋ชฉํ๋ก ํ๋๋ฐ์, ์ด๋ฒ 5์ฃผ์ฐจ์๋ **์ฌ๋ฌ ํ์ด์ง๋ฅผ ๋๋์ด ์ ํ๋ฆฌ์ผ์ด์์ ๊ฐ ๊ธฐ๋ฅ์ ์ ๊ณตํ๊ณ  ์ด๋ฅผ ๋ค๋ฅธ URL๋ก ์ ๊ทผํ  ์ ์๋๋ก ํ๋ ๊ฒ**์ด ๋ชฉํ์์ต๋๋ค.

## Routing๊ณผ SSR

๋จผ์  ๋ช ๊ฐ์ง ๊ฐ๋์ ๋ํด์ ๋จผ์  ์ง๊ณ  ๋์ด๊ฐ์ผ๊ฒ ๋๋ฐ์,,,
์ด๋ฒ ์ฃผ์ฐจ ๋ฏธ์ Key Question์ผ๋ก๋ ์ฃผ์ด์ง ํค์๋๋ค์๋๋ค.  

์ผ๋ฐ์ ์ผ๋ก ์ฐ๋ฆฌ๊ฐ ์น์ฌ์ดํธ๋ฅผ ์ ์ํ๋ค๊ณ  ํ์ ๋,
๋ค๋ฅธ ๊ฒฝ๋ก์ URL์ ๋ถ๋ฌ์ค๋ฉด ๋ค๋ฅธ ํ์ด์ง๋ก ์ฐ๊ฒฐ๋ฉ๋๋ค.  
์ฆ, URL์ ๋ณ๊ฒฝํ๋ฉด ์ฐ๋ฆฌ๊ฐ ๋ณด๊ณ ์ ํ๋ ํ์ด์ง์ ๋ด์ฉ๋ค์ด ๋ฐ๋๋๋ค.  
์ด์ฒ๋ผ URL์ ๋ฐ๋ผ ๊ฒฝ๋ก๋ฅผ ์ถ์ ํ์ฌ ๊ฒฝ๋ก์ ๋ง๋ ํ์ด์ง๋ฅผ ๋ณด์ฌ์ฃผ๋ ๊ฒ์
**๋ผ์ฐํ**์ด๋ผ๊ณ  ํ  ์ ์์ต๋๋ค.

๋ํ ์ด๋ ๊ฒ ๋ผ์ฐํ์ ํตํด URL๋ง๋ค ๋ค๋ฅธ ํ์ด์ง๋ฅผ ์ฌ์ฉ์์๊ฒ ๋ณด์ฌ์ค์ผ ํ๋ ๊ฒฝ์ฐ
๊ธฐ์กด์ ์๋ ๋ฐฉ์์ ์๋ฒ์์ ๊ฐ ํ์ด์ง๋ฅผ ๋ชจ๋ ๋ง๋ค์ด์ ๋ธ๋ผ์ฐ์ ์๊ฒ ์ ์กํ๊ณ ,
์ด๋ฅผ ๋ธ๋ผ์ฐ์ ๊ฐ ์ฌ์ฉ์์๊ฒ ๋ณด์ฌ์ฃผ๊ฒ ๋ฉ๋๋ค.  
์ด ๊ฒฝ์ฐ ํ์ด์ง๊ฐ ์๋ฒ์์ ๋ง๋ค์ด์ง ์ํ๋ก ๋ณด๋ด์ง๋ฏ๋ก
**Server-Side Rendering** ๋ฐฉ์์ด๋ผ๊ณ  ํฉ๋๋ค.  

## React์์์ Routing?

1. ๋ผ์ฐํ ์ ์๋ก ๋ณด์ฌ์ ธ์ผ ํ๋ ๋ถ๋ถ๋ง์ ์ฌ ๋ ๋๋ง 
2. ๋ฆฌ์์ค๋ฅผ ๋ชจ๋ ๋ฏธ๋ฆฌ ๋ค์ด๋ก๋๋ฐ๊ณ  Client-Side Rendering

ํ์ง๋ง ๊ธฐ์กด์ ์น์ฌ์ดํธ์ ๋ฌ๋ฆฌ React๋ก ๋ง๋ค์ด์ง ์ ํ๋ฆฌ์ผ์ด์์
Single Page Application์ด๊ธฐ ๋๋ฌธ์, ํ๋์ ํ์ด์ง๋ก๋ง ๊ตฌ์ฑ๋์ด ์์ต๋๋ค.  

๋ฐ๋ผ์ SPA์์ Routing์ ์ ๊ณตํ๊ธฐ ์ํด์๋ ๊ฐ๊ฐ์ HTML์ ๊ตฌ์ฑํ๋ ํ์ผ๋ค์
์๋ฒ์ ์ ์ฅํ๊ฑฐ๋, ํน์ ์๋ฒ์์ ๋์ ์ผ๋ก ์์ฑํ์ฌ ์ ์ฅํ๊ณ  ๋ค๋ฅธ URL์ ๋ฐ๋ผ
์์ฒญํ๋ ๋ฐฉ์์ผ๋ก ๊ตฌํํ  ์ ์์ต๋๋ค.  

> SPA์์ Routing์ ํ๋ ์๊ฐ Single Page๊ฐ ์๋๊ฒ ๋์ง ์๋์?

Url์ ์ฌ์ฉํ๋ฉด ํ๋์ ํ์ด์ง ์์์๋ ํ์ํ ํญ๋ชฉ์ ์ฌ์ฉ์๊ฐ ๋ถ๋งํฌ ์ฒ๋ฆฌ ํ๊ฑฐ๋,
์ฌ์ฉ์ค์ ๋ค๋ก๊ฐ๊ธฐ๋ฅผ ๋๋ ์ ๋ ๊ทธ ์  ํ์ด์ง๋ก ์ด๋ํ  ์ ์๊ฒ ํด ์ค๋๋ค.  
์ด๋ฐ ์ด์ ์์ SPA์์์ Routing ํ์์ฑ์ ์ธ๊ธํ  ์ ์๊ฒ ๊ตฌ์,,  
๋ฐ๋ฐ ์ ๋ ๋ง์ด ๋ง์  

## React Router v6?

์์ฃผ ๋คํ์ค๋ฝ๊ฒ๋, ํ๋ก ํธ ๊ฐ๋ฐ์๋ค์ด **๋น์ฅ ์ค๋ ์ค์ ๋ก** Routing์
๊ตฌํํ๊ณ ์ ํ๋ค๋ฉด `react-router` ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ๋ฐ๋ก ๊ฐ๋ค ์์ผ๋ก์จ
ํธ๋ฆฌํ๊ฒ ๊ตฌํํ  ์ ์์ต๋๋ค.  

react-router์ ํต์ฌ ์ปดํฌ๋ํธ๋ค์ ์์๋ณผ๊น์?  

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

react-router๋ฅผ ์ฌ์ฉํ๊ธฐ ์ํ ๊ฐ์ฅ ์ฒซ ๋ฒ์งธ ์์์,
์ต์์ ์ ํ๋ฆฌ์ผ์ด์์ `BrowserRouter`๋ก ๊ฐ์ธ๋ ๊ฒ์๋๋ค.  

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

๊ทธ ๋ค์์ผ๋ก๋ path property์ ๋ฐ๋ผ ๋ค๋ฅด๊ฒ ๋ ๋๋งํ๊ณ  ์ถ์ ์ปดํฌ๋ํธ๋ค์
`Route`๋ก ๊ฐ์๋๋ค.  

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

`Route` ์ปดํฌ๋ํธ๋ฅผ ํตํด ๋ผ์ฐํ์ ๋ฐ๋ผ ๋ค๋ฅด๊ฒ ๋ณด์ฌ์ง๊ณ  ์ถ์ ์์๋ฅผ ์ ํํ๋ค๋ฉด,  
`Link` ํ๊ทธ๋ฅผ ์ด์ฉํด ์ค์ ๋ก ๋ผ์ฐํ์ด ์ด๋ฃจ์ด์ ธ์ผ ํ๋ ํ์ด์ง๋ก์
์ด๋ ๊ธฐ๋ฅ์ ์ ๊ณตํ  ์ ์์ต๋๋ค.  

## ์ข ๋ ๊น์ด ํ๊ณ  ๋  react-router ๋์ ์๋ฆฌ

์์์ ๋ณธ ๊ฒ์ฒ๋ผ `react-router`๋ฅผ ์ด์ฉํด ๋ผ์ฐํ์ ๊ตฌํํ๋ ๋ฐฉ๋ฒ์ ๊ฐ๋จํฉ๋๋ค.  
์ ๊ฐ ๋ฐํ์๊ฐ ์๋์๋ค๋ฉด ์ ๋๊ฒ ์ฝ๋๋ฅผ ์ ์ฉํ๊ณ  ๋๋ฌ์ ํ์ง๋ง ๋ฐํ์์ด๊ธฐ ๋๋ฌธ์...  
์ข ๋ ๋์ ์๋ฆฌ๋ฅผ ์์ธํ ์ดํด๋ณด๋๋ก ํ์ฃ ..

> react-router vs react-router-dom?

- react-router-dom : react-router v4 ๋ฒ์ ์์ ์ฒ์ ๋ฆด๋ฆฌ์ฆ๋ ๋ผ์ฐํ ๋ชจ๋
- react-router ๋ชจ๋์ ์ฝ์ด๋ก ์น ๊ฐ๋ฐ์ ์ํ `react-router-dom`,  
์ฑ ๊ฐ๋ฐ์ ์ํ `react-router-native`๊ฐ ๋๋์ด ์ ๊ณต

์ฐ์  ์ด๋ฒ ๋ฏธ์์ ์ํด ๊ฒ์ํ๋ค๊ฐ `react-router-dom`๊ณผ
`react-router`์ ๋ํ ์ฉ์ด๊ฐ ์ผ๋ถ ํผ์ฉ๋์ด ์๋ ์๋ฃ๋ค์ ๋ฐ๊ฒฌํ์จ์ ํ๋ฐ์,  
์ ํํ๊ฒ๋ react-router-dom ๋ชจ๋์ react-router ๋ชจ๋์
dom์ด ๋ฐ์ธ๋ฉ ๋์ด ์๋ ๋ชจ๋์ด๋ผ๊ณ  ํฉ๋๋ค.  

![image](https://user-images.githubusercontent.com/6462456/168460914-706af89b-3679-4c2e-8c7f-46c92599aacf.png)
_๋ชจ๋ฐ์ผ์์๋...? - React Navigation vs React Router_

- React Navigation์ `react-native-screens`์ ์์กด์ฑ์ ๊ฐ์ง
- `IOS`์ ๊ฒฝ์ฐ๋ `UINavigationController`, `Android`์ ๊ฒฝ์ฐ๋
`Fragment`๋ฅผ ์ด์ฉํ๋ **Native-Stack Navigator** ๊ตฌ์กฐ๋ก
ํด๋น API๋ฅผ ์ด์ฉํ ๋ค์ดํฐ๋ธ ๊ฐ๋ฐ ๋ฐฉ์๊ณผ ๊ฐ์ ํผํฌ๋จผ์ค๋ฅผ ๊ฐ์ง

> HTML 5 History API

- ํ์ฌ ํญ์ ๋ฐฉ๋ฌธ ๊ธฐ๋ก์ **Stack ํํ**๋ก ๋ฉ๋ชจ๋ฆฌ ์์์ ๊ด๋ฆฌ
(์ดํ **History Stack**)
- History API๋ ํญ ๋จ์๋ก ์กด์ฌํ๋ **windows** ์ ์ญ ๊ฐ์ฒด์
property ๋ฐ method๋ค๋ก ์ ๊ณต๋จ

```javascript
/* properties */
history.length
history.scrollRestoration
history.state
```

- properties  
`history.length` : ํ์ฌ ํ์ด์ง๋ฅผ ํฌํจํด ๋ฐฉ๋ฌธํ ๊ธฐ๋ก์ ์ด ๊ธธ์ด  
`history.scrollRestoration` : `auto` | `manual` :  
๋ฐฉ๋ฌธ ๊ธฐ๋ก์ ํ์ํ  ๋ ์คํฌ๋กค ์์น๋ฅผ ์๋ ์์น๋ก ๋ณต์ํ  ์ง์ ์ฌ๋ถ  
`history.state` : History Stack์ ์ต์๋จ์ ์์นํ ์ํ ๊ฐ  

```javascript
/* methods */
history.go([delta])
history.back()
history.forward()
```

- methods  
`history.go([delta])` : ํ์ฌ ํ์ด์ง๋ฅผ ๊ธฐ์ค์ผ๋ก, **์๋์ ์ธ ์์น์ ์กด์ฌํ๋ ๋ฐฉ๋ฌธ ๊ธฐ๋ก ๋ด ํ์ด์ง๋ก ์ด๋**  
`history.back()` : ๋ฐฉ๋ฌธ ๊ธฐ๋ก์ **๋ฐ๋ก ๋ค ํ์ด์ง๋ก ์ด๋**  
`history.forward()` : ๋ฐฉ๋ฌธ ๊ธฐ๋ก์ **๋ฐ๋ก ์ ํ์ด์ง๋ก ์ด๋**  

```javascript
/* methods */
history.pushState(state, title[, url])
history.back()
history.forward()
```
`history.pushState(state, title[, url])` :  
์ฃผ์ด์ง ์ํ ๊ฐ์ **History Stack์ ์ถ๊ฐ**  
`history.replaceState(state, title[, url])` :  
History Stack์ **์ ์ผ ์ต๊ทผ ํญ๋ชฉ์ ์ฃผ์ด์ง ์ํ ๊ฐ์ผ๋ก ๋์ฒด**  

_์ฐธ๊ณ ๋ก, ๋ธ๋ผ์ฐ์ ์ ์๋ก๊ณ ์นจ(= location.reload() ํจ์์ ํธ์ถ)์ ์ถ๊ฐ์ ์ธ ๋ฐฉ๋ฌธ ๊ธฐ๋ก์ Push ํ์ง ์๋๋ค._

```javascript
/* event */
.onpopstate = (event) => {...}
```

- event  
`popstate` : ์ฌ์ฉ์์ ๋ฐฉ๋ฌธ ๊ธฐ๋ก ํ์์ผ๋ก ์ธํด
ํ์ฌ ํ์ฑํ๋๋ ๊ธฐ๋ก ํญ๋ชฉ์ด ๋ฐ๋ ๋ ๋ฐ์  

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

> Node.js์ History ํจํค์ง

![image](https://user-images.githubusercontent.com/6462456/168462542-019845fd-0390-4464-953f-a7600fce23a8.png)
_https://github.com/remix-run/history/blob/28c89f4091ae9e1b0001341ea60c629674e83627/docs/api-reference.md_

- Session์ History๋ฅผ ๋ค๋ฃจ๋ ๋ฐฉ๋ฒ์ ๊ตฌ๋ ํ๊ฒฝ์ ๊ธฐ์ค์ผ๋ก ์ธ ๊ฐ์ง๋ก ๋๋ ์ ์ ๊ณต  
`createBrowserHistory`  <-  ์ด ๋ ์ฃผ๋ชฉ  
`createHashHistory`    
`createMemoryHistory`

_history API๋ฅผ ๊ธฐ๋ฐ์ผ๋ก ๊ตฌํ๋๋ history ๊ฐ์ฒด๋ฅผ ๋ค๋ฃจ๋ ๋ฐฉ์์๋ง ์ฃผ๋ชฉ_

> BroswerRouter

![image](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbQoWT9%2FbtqNqdkcKIF%2FUOhoaTws6GK4m0jUeFPucK%2Fimg.png)
_Overall Structure in react-router-dom_

- ์ฐ์ ์ ์ผ๋ก history ํจํค์ง์ `createBrowserHistory()` ํจ์๋ฅผ ํธ์ถํจ์ผ๋ก์จ history ๊ฐ์ฒด๊ฐ ์์ฑ
- `BrowserRouter` ์ปดํฌ๋ํธ๊ฐ `Router` ์ปดํฌ๋ํธ๋ฅผ ๋ ๋๋งํ  ๋  
`props`๋ก history ๊ฐ์ฒด ์ ๋ฌ

> (BrowserRouter ๋ด์) Router

- ๋ง์ดํธ๋๋ ์๊ฐ์ `props`๋ก ์ ๋ฌ๋ฐ์ history ๊ฐ์ฒด ๋ด location ๊ฐ์ฒด๋ฅผ ์์ ์ ์ง์ญ ์ํ์ ์ ์ฅ
- `history.listen()`์ ์ด์ฉํด `props`๋ก ์ ๋ฌ ๋ฐ์ history ๊ฐ์ฒด๋ฅผ ๊ตฌ๋ํด ํ์ฌ URL์ด ๋ณ๊ฒฝ๋  ๋๋ง๋ค ์ง์ญ ์ํ์ location ๊ฐ์ฒด๋ฅผ ๊ฐฑ์ 
- Router ์ปดํฌ๋ํธ๋ ํ์ฌ์ URL๊ณผ ๊ด๋ จ๋ ๋ช๋ช ์ ๋ณด๋ค(match ๊ฐ์ฒด, location ๊ฐ์ฒด, history ๊ฐ์ฒด)์ Context๋ก ๊ตฌ์ฑํด์ ํด๋น Context์ `RouterContext.Provider`๋ฅผ ๋ ๋๋ง

> Route

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FpVUsh%2FbtqNmcG9d5u%2FF6P0Hixg6eSt2S9vk8h1x0%2Fimg.png)
_Overall Structure in Route Component_

- `props`๋ก ์ ๋ฌ๋ฐ๋ path์ ๊ฐ์ด ๋ธ๋ผ์ฐ์ ์ ํ์ฌ URL๊ณผ ๋งค์นญ ๋  ๋
ํจ๊ป ๋ช์๋ **ํน์  ์ปดํฌ๋ํธ๋ฅผ ๋ ๋๋ง ํ๋ ์ปดํฌ๋ํธ**
- `RouterContext.Consumer` ์ปดํฌ๋ํธ๋ฅผ ๋ ๋๋งํจ์ผ๋ก์จ
`RouterContext` ์ฐธ์กฐ
- `RouterContext`์ location ๊ฐ์ฒด ์ ๋ณด์ props๋ก ์ ๋ฌ๋ฐ์ path ๊ฐ ๋น๊ต  
**๋งค์นญ O** -> props๋ก **์ ๋ฌ๋ฐ์ ์ปดํฌ๋ํธ**๋ฅผ ๋ ๋๋ง  
**๋งค์นญ X** -> **null**์ ๋ ๋๋ง 

> Switch(v5) -> Routes(v6)

![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FkT8DE%2FbtqNouA0hXr%2FQiZXsIGiQTJ6NpwVYiHV6k%2Fimg.png)
_Overall Structure in Switch(Routes) Component_

-  ๋ธ๋ผ์ฐ์ ์ ํ์ฌ URL๊ณผ ๋งค์นญ ๋๋ ์ฒซ ๋ฒ์งธ `Route` ์์ Element๋ฅผ
๋ ๋๋งํ๋ ์ปดํฌ๋ํธ
- `RouterContext.Consumer` ์ปดํฌ๋ํธ๋ฅผ ๋ ๋๋งํจ์ผ๋ก์จ `RouterContext` ์ฐธ์กฐ
- `RouterContext`์ location ๊ฐ์ฒด ์ ๋ณด์ props๋ก ์ ๋ฌ๋ฐ์
๊ฐ ์์ Element์ path props ์ ๋ณด๋ฅผ ํ๋์ฉ ๋น๊ต  
**๋งค์นญ O** -> ์ฒซ ๋ฒ์งธ๋ก ๋งค์นญ๋๋ `Route` Children Element๋ฅผ ๋ ๋๋ง

> Link

- **Page Reloading ์์ด Navigation์ ์ํ**ํ๋ ์ปดํฌ๋ํธ
- ๊ฒฐ๊ณผ์ ์ผ๋ก๋ ์ผ๋ฐ์ ์ธ `a` ํ๊ทธ๋ก ๋ ๋๋ง ๋์ง๋ง...  
1. ๋จผ์  `preventDefault()` ํจ์๋ฅผ ํธ์ถํด `a` ํ๊ทธ์ ๊ธฐ๋ณธ ๋์ ๋ง์
2. ๊ทธ ๋์  `RouterContext`์ ์กด์ฌํ๋ history ๊ฐ์ฒด๋ฅผ ์ด์ฉํ์ฌ ๋ด๋น๊ฒ์ด์์ ์ํํ๋๋ก ๊ตฌํ

> ๊ฒฐ๋ก  (์ธ ์ค ์์ฝ)

1. `Router` ์ปดํฌ๋ํธ์ ์ง์ญ ์ํ์๋ history.location ๊ฐ์ฒด๊ฐ ์กด์ฌํ๋ฉฐ
history.listen() ๋ฉ์ปค๋์ฆ์ ์ํด ํญ์ ์ต์  ์ํ๋ก ๊ด๋ฆฌ๋จ
2. ์ด ์ ๋ณด๊ฐ ๋ฐ๋ ๋๋ง๋ค `Router`์ปดํฌ๋ํธ๊ฐ Re-Rendering๋๋ฉฐ
ํ์ ์ปดํฌ๋ํธ๊น์ง ํจ๊ป Re-Rendering๋๋๋ก ๋ง๋ฆ
3. location ๊ฐ์ฒด์ Matchingํ ๊ฒฐ๊ณผ๋ฅผ ๋ฐํ์ผ๋ก `Switch`์ ๊ฒฝ์ฐ๋
์์ ์๋ฆฌ๋จผํธ๋ค ์ค Matching๋ ์ปดํฌ๋ํธ๋ฅผ, `Route` ์ปดํฌ๋ํธ๋ ํจ๊ป ๋ช์๋ ์ปดํฌ๋ํธ๋ฅผ ๋ ๋๋งํ๋ฉฐ  
match ๊ฐ์ฒด, location ๊ฐ์ฒด, history ๊ฐ์ฒด๋ฅผ ๋ ๋๋ง ํ  ์ปดํฌ๋ํธ์๊ฒ ๋๊ฒจ์ค

## ๋ช ๊ฐ์ง ์๊ฐํด ๋ณผ ๋งํ ์ฃผ์ ๋ค

> v5 -> v6๋ก์ ๋ณํ?

> Link ์ปดํฌ๋ํธ๊ฐ ์๋๋ผ HTML์ anchor ํ๊ทธ๋ฅผ ์ด์ฉํด ์ด๋ํ๋ค๋ฉด?

> URL matching

## ์ ์ฉ ๊ฐ๋ฅํ ๋ช ๊ฐ์ง ํจํด

> Nested Routing

> Sidebar CSS Styling

---

# ์ฐธ๊ณ  ์๋ฃ

- https://www.reimaginer.me/entry/spa-and-spa-routing
- https://serzhul.io/REACT/์ฑ๊ธํ์ด์ง-์ดํ๋ฆฌ์ผ์ด์-๋ผ์ฐํ(single-page-application-routing)/
- https://it-eldorado.tistory.com/111
- https://it-eldorado.tistory.com/113
- https://velog.io/@devstone/react-router-dom-์ดํดํ๊ณ -ํ์ฉํ๊ธฐ
- https://velog.io/@function_dh/HTML5-history-API-๋ธ๋ผ์ฐ์ -์ด๋