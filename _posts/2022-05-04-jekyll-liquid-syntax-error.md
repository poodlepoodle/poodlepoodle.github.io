---
layout: post
title: ✅ Jekyll Blog - Liquid Syntax Error 해결
date: 2022-05-04 17:25:00 +0900
published: true
categories: [coding, troubleshooting]
tags: [jekyll, liquid exception, liquid syntax error]
---

## 1. Github Action으로 글 발행 시 에러 발생

![image](https://user-images.githubusercontent.com/6462456/166635867-b0c44682-ac62-497e-95e6-ff7dc89d78aa.png)

Github Blog로 발행할 글을 만지다가 `push`하고 기다리는데
시간이 지나도 글이 업데이트되지 않는다.  
poodlepoodle.github.io의 Repository > **Actions** 탭으로
가 보니 위와 같이 뭔가 Build 과정에서 에러가 난 것으로 보인다.

## 2. Liquid Exception: Liquid syntax error

![image](https://user-images.githubusercontent.com/6462456/166640253-d537b54f-aa0a-4b01-8f66-98b2ac5349e3.png)

```text
Liquid Exception: Liquid syntax error (line 151): Unknown tag 'F' in ...
```

들어가서 에러 메시지를 구체적으로 확인하면
태어나서 처음 보는 `Liquid Exception: Liquid syntax error...` 라는 에러가 발생한 것을 볼 수 있다.  
이전에 발행한 글 2개는 문제 없이 발행된 것을 보니
**ruby dependency**와 관련된 것은 아닌 것 같고..
뭔가 싶어 일단 검색창에 에러 메시지를 그대로 쳐 봤다.

> [Jekyll Liquid Template](https://jekyllrb.com/docs/liquid/)

![image](https://user-images.githubusercontent.com/6462456/166642446-ff93edf6-07d5-4b92-aa86-981191a7a286.png)

`Liquid`는 `ruby`로 만들어진 템플릿 언어이며
당연히 `Jekyll`에서도 이를 지원한다.  
그리고 보면 Liquid로 템플릿을 규정하는 표시는
`{ + {`나 `} + }`로 지정함을 알 수 있다.  
**그렇다면 만약에 markdown 파일 중간에 위의 지정 문자가 등장하면
의도와 다르게 Liquid로 인식해 위의 에러가 날 수 있겠다... 싶다.**

## 3. 에러 해결

- [https://iamheesoo.github.io/blog/gitblog-sol-jekyll02](https://iamheesoo.github.io/blog/gitblog-sol-jekyll02)
- [http://jmjeong.com/escape-in-liquid-syntax/](http://jmjeong.com/escape-in-liquid-syntax/)
- [https://gloriajun.github.io/etc/2017/04/11/github-blog-liquid-syntax.html](https://gloriajun.github.io/etc/2017/04/11/github-blog-liquid-syntax.html)

에러가 난 markdown 포스트를 뒤지다가
뭔가 굉장히 에러 원인으로 의심되는 코드 블록을 발견했다.  
이를 위 링크들을 참고한 대로 `{ + % + raw + % + }`
~ `{ + % + rawend + % + }` 블록으로 감싸 줘서
자칫 Liquid로 인식될 수 있는 부분을
raw text로 인식하도록 해 줬다.  
이후 `commit` 전에 `bundle exec jekyll serve`를 통해
테스트해 보면 에러가 뜨지 않는 것을 확인할 수 있다.  

😙