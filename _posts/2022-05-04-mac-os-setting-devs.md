---
layout: post
title: 🛠 Mac OS 처음부터 세팅하기 - 개발
date: 2022-05-04 02:55:00 +0900
published: true
categories: [coding, mac os]
tags: [mac os, xcode, vscode, zsh]
---

## 0. 기본 사용자 설정까지 끝낸 단계

![image](https://user-images.githubusercontent.com/6462456/166516525-0a32a19e-43fa-4d6e-97f1-652fda6f25ee.png)

[저번 포스팅](https://poodlepoodle.github.io/posts/mac-os-setting-basics/)에서 대부분의 Mac OS 사용자 환경 설정을 완료했다.  
이제 사용하던 개발 환경을 복구해 보자.....  

## 1. Xcode

![image](https://user-images.githubusercontent.com/6462456/166204362-425d756b-7ded-4dba-977c-15dc7b1399d7.png)

Xcode는 Mac 앱스토어에서 설치할 수 있다.  
업데이트를 잘 안 하고 써서 몰랐는데 최신 버전은 **Mac OS 12.0 Monterey 이상**을 필요로 한다고 한다.  
내 맥북이 Big Sur까지만 지원하는 걸 어떻게 하리... 그냥 **이전 버전 다운로드** 누른다...  

### 1-1. Command Line Tools 설치

```zsh
xcode-select --install
```

Xcode를 설치하지 않고 `git`, `gcc` 등의 여러 도구들을 사용하기 위한 방법으로는 **Command Line Tools** 설치가 있다. 물론 Xcode를 설치하면 자동으로 설치되는 것으로 확인했기 때문에 본인 선택에 따라 방법을 고르면 될 것 같다. 나는 RN 개발 시 시뮬레이터 사용이나 OpenCV 개발환경 등등 고려해서 Xcode를 아예 설치하는 게 더 나을 것으로 판단했다.  

![image](https://user-images.githubusercontent.com/6462456/166407719-dfffe84b-a93d-43a8-9fdd-553fa13fa7f1.png)

Xcode 프로젝트 생성 시 Command Line Tool 옵션이 뜨면 잘 설치된 거임  

### 1-2. Xcode OpenCV-C++ 개발환경 설정

[예전에 작성한 블로그 글 참고](https://poodlepoodle.github.io/posts/opencv-installation-windows-mac/)  

## 2. ITerm 2

![image](https://user-images.githubusercontent.com/6462456/166201976-c67abdfd-61a7-40e3-a96b-8745ae4620bf.png)

[설치 링크](https://iterm2.com)  

Mac OS의 기본 터미널을 사용할 수도 있지만,
**ITerm 2**를 사용하는 경우 좀 더 Appearence 면에서 커스터마이징이 가능하다.  

![image](https://user-images.githubusercontent.com/6462456/166203789-af95c1ce-8f22-4404-9fb9-528a76ddc5d5.png)

막 설치한 Vanilla 상태의 ITerm 2  
이제부터 터미널 명령어로 설치하고 설정해야 하는 경우들은 모두 기본 터미널이 아닌 ITerm으로 진행하겠다.  

### 2-1. ITerm 2 테마 설정

#### 2-1-1. Color Scheme 설정 - **Afterglow**

![image](https://user-images.githubusercontent.com/6462456/166436419-33dd9c5e-a025-4952-a1b2-a04405f5a50a.png)

[color scheme 둘러보기](https://iterm2colorschemes.com)  

위의 링크에서 `.itermcolors` 파일을 다운받은 후  
**Preference > Profile > Colors** 설정에서 **Color Presets...**를 눌러 불러와준 후 적용한다.  

#### 2-1-2. 폰트 설정 - **Naver D2coding**

![image](https://user-images.githubusercontent.com/6462456/166438876-014731d3-a0b4-4a22-90ab-e42da4d7deb4.png)

[설치 링크](https://github.com/naver/d2codingfont/releases/tag/VER1.3.2)  

위 링크에서 폰트 설치 후 **Profiles > Text**에서 적용  
폰트 크기는 한 13px 쯤 설정하면 괜찮은듯  

#### 2-1-3. Word jump 단축키 설정 - **Natural Text Editing**

![image](https://user-images.githubusercontent.com/6462456/166448868-bc518384-7722-4125-aae5-b24559bb4600.png)

ITerm 2에서 기본적으로 option + 방향키나 cmd + 방향키 혹은 삭제 단축키가 안 먹혀서 추가로 Keys 탭 가서 설정하고 있다가 Stackoverflow에서  
**Profiles > Keys > Preset...** 에서 **Natural Text Editing**으로 수정하면 된다는 걸 알았다.  

#### 2-1-4. 기타 설정

- **General > Closing > Confirm "Quit ITerm 2"** 체크 해제
- **Appearence > General > Theme - Mininal**로 설정
- **Profiles > Text > Cursor - Vertical Bar** 체크 및 **Blinking cursor** 체크
- **Profiles > Window > Transparency** 관련 설정 모두 해제

### 2-2. Homebrew 설치

[설치 링크](https://brew.sh/index_ko)  

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Homebrew** : Mac OS 전용 프로그램들을 설치할 수 있는 **패키지 관리자**  
설치하는데 시간 좀 걸림  

![image](https://user-images.githubusercontent.com/6462456/166426354-3f250887-1286-4cca-87de-480252d371f5.png)

위에서 Xcode 깔면서 Command Line Tools 설치된 걸로 알았는데 또 설치할거냐고 물어본다. 왜일까...?  
일단은 무지성 엔터 치고 좀 기다리면 설치가 완료된다  

```zsh
brew install wget
```

당장 생각나는 게 없으니 `wget` 정도만 설치해 주고 넘어감  

### 2-3. Oh-my-zsh 설치 및 zsh 설정

[설치 링크](https://ohmyz.sh/#install)  

```zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

다음으로는 **oh-my-zsh**을 설치해 줄 차례이다.  
oh-my-zsh은 zsh 설정을 관리해 주는 오픈소스 프레임워크이다.  
Catalina 이후부터인가 Mac OS의 기본 터미널이 `bash`에서 `zsh`로 바뀌었다고 하는데
원래부터 zsh을 사용하던 사람들에게는 익숙한 이름이다.  
어차피 깡통 상태에서 깐다고 생각해 `~/.zshrc` 의 내용은 비어 있다고 가정하고 백업 없이 그냥 설치함  

![image](https://user-images.githubusercontent.com/6462456/166429055-b18adbda-40a8-4365-83f4-54d3dc11e1c6.png)

설치가 완료되면 굉장히 알록달록해진 걸 볼 수 있는데 이대로 쓸 건 아니니까 몇 가지 추가 설정을 해줘야 함  

#### 2-3-1. zsh 테마 설정 - **powerlevel10k**

[테마 둘러보기](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)  
[powerlevel10k 설치 안내](https://github.com/romkatv/powerlevel10k#manual)  

위의 테마 둘러보기 가면 적용할 수 있는 다양한 zsh 테마들이 있다.  
어떤 걸 고르느냐에 따라 색상이나 모양을 꾸밀 수 있지만 특별히 기능이 강력해서 많이 선택받는 몇 가지 선택지가 있다.  
나는 그 중에서 **powerlevel10k**를 설치해보려고 함  

```zsh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

![image](https://user-images.githubusercontent.com/6462456/166489912-066967de-ed35-4948-9189-4f398aa9c9da.png)

다운받아 준 다음 `~/.zshrc` 파일 내부의 `ZSH_THEME="powerlevel10k/powerlevel10k"` 부분을 수정해주면 된다.  
이후 `source ~/.zshrc` 혹은 ITerm 재 실행  

![image](https://user-images.githubusercontent.com/6462456/166490599-9c0e709f-129d-4fc9-bd9b-551aa0b823e5.png)

자동으로 powerlevel10k의 configuration script가 실행된다.  
취향에 맞게 적당히 골라주면서 넘어가면 됨  
만약 설정을 마쳤는데 다시 고르고 싶다면 `p10k configure` 실행 ㄱㄱ  

#### 2-3-2. zsh 추가 커스터마이징

- 명령어 실행 시마다 앞에 붙는 사용자 및 컴퓨터 없애기  

{% raw %}
```zsh
prompt_context() { 
	if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then 
    	prompt_segment black default "%(!.%{%F{yellow}%}.)$USER" 
    fi 
}
```
{% endraw %}

`~/.zshrc` 아래 부분에 위 내용을 붙여 주면 없앨 수 있다.  

- zsh Syntax Highlighting 및 auto-suggestion 설치 후 적용  

```zsh
# install zsh syntax highlighting plugin
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# install zsh auto-suggestion plugin
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# ~/.zshrc 파일 내에 수정
plugins=(
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
)
```

- 터미널 실행 시 뜨는 `last login : ....일시 On ttys..` 안 뜨도록 설정  

```zsh
touch .hushlogin
```

터미널 실행 후 `root` 경로에서 빈 `.hushlogin` 파일 생성 후 터미널 다시 시작하면 적용됨  

## 3. VScode

[설치 링크](https://code.visualstudio.com)  

Stable build로 설치  

### 3-1. VScode 테마 설정 - **Shades of Purple**

![image](https://user-images.githubusercontent.com/6462456/166473998-a740ca49-f894-4dc9-8c56-f87dcaac29fe.png)

예전에 쓰던 테마가 뭔지 기억이 안나서 그냥 괜찮아 보이는 걸로 설치했다

### 3-2. zsh에서 code 명령어로 실행하도록 설정

![image](https://user-images.githubusercontent.com/6462456/166474428-8eba120a-6828-40f3-acd3-38fe150302b3.png)

**Cmd + Shift + P** 누른 다음  
**Shell Command: Install 'code' command in PATH** 선택  

## 4. Git

```zsh
brew install git git-lfs
```

기본으로 설치되어 있으나 최신 버전으로 업그레이드  

```zsh
git config --global user.name "poodlepoodle"
git config --global user.email "chammal97@naver.com"
git config --global core.precomposeunicode true
git config --global core.quotepath false
```

계정 설정 및 한글 관련 몇가지 추가 설정을 해 준다.  

## 5. Github Blog

```zsh
git clone https://github.com/poodlepoodle/poodlepoodle.github.io.git
```

먼저 github에 올린 내용들을 clone해 온다  

### 5-1. rbenv를 통한 ruby 버전 변경

```zsh
brew install rbenv ruby-build
rbenv versions
rbenv install 3.1.2
```

![image](https://user-images.githubusercontent.com/6462456/166504804-9482268c-95c5-4f37-84d2-5c6015d4004e.png)

위 명령어를 치면 현재 Mac OS에 깔려 있는 ruby가 system 버젼을 사용하고 있음을 알 수 있다.  
그대로 `bundle` 명령어를 수행하게 되면 오류가 발생하기 때문에,
`rbenv install -l` 명령어로 설치 가능한 stable 버전들을 확인한 후 골라서 깔아준다.  
_(2022-05-04 기준으로 3.1.2 설치)_  

```zsh
# ruby 버전 방금 설치한 3.1.2로 지정
rbenv global 3.1.2

# ~/.zshrc 내 아래 내용 추가
[[ -d ~/.rbenv  ]] && \
  export PATH=${HOME}/.rbenv/bin:${PATH} && \
  eval "$(rbenv init -)"
```

설치한 버젼을 글로벌 버전으로 지정해 준 다음,
위의 내용을 `~/.zshrc` 마지막에 추가해 준다.  

![image](https://user-images.githubusercontent.com/6462456/166509263-7ba98095-69f7-422b-ae9a-a30d9bf973da.png)

이후 `bundle` 명령어를 실행하면 자동으로 패키지들이 잘 깔린다.  

```zsh
# 로컬에서 블로그 실행
bundle exec jekyll serve

# 포스트 올릴 때 commit message 양식
git commit -m ":memo: [docs]: edit some posts"
git push origin main
```

굳이 로컬에서 안 돌려봐도 **typora** 같은 마크다운 에디터로 미리 보고 발행할 때만 push해도 될 듯..  

## 6. React, Typescript

하드 날라가면서 프론트엔드 과제 때 Prettier 다시 세팅해야겠다는
걱정이 들었는데 정작 Node 날라간 건 생각 못했다....  

### 6-1. Node.js 설치

![image](https://user-images.githubusercontent.com/6462456/167136932-08b34465-b20d-45b7-9aac-aa4032e37370.png)

[설치 링크](https://nodejs.org/en/)

왼쪽의 **LTS**로 선택해서 다운로드 후 설치  

```zsh
sudo npm install npx -g
```

위 명령어를 통해 npx 최신 버전 설치  
이미 파일이 있다는 둥 에러가 뜨는데 ㄱㅊ다고 함  

```zsh
node -v # v16.15.0
npm -v #8.5.5
npx -v #8.5.5
```

22-05-06 기준 설치된 버젼 체크  
React 개발 시 node 버전은 13 이하, 17은 피해서 설치하라고 한다...  

```zsh
npm install
```

`react-scripts: command not found` 에러 보고 싶지 않다면  
프로젝트 실행하기 전에 잊지 말자...  

### 6-2. Styled-Components 설치

```zsh
npm install styled-components
```

Css 스타일링 방식 중 `Styled-Components`를 사용하기 위해 설치  

![image](https://user-images.githubusercontent.com/6462456/167169820-8e2fa7c2-6130-48fe-b7fb-fd294174999c.png)

VScode에서 Styled-Components **자동 완성 기능**을 사용하기 위한 확장임  

### 6-3. Prettier 설정

![image](https://user-images.githubusercontent.com/6462456/167231278-c3479af8-a98f-497c-9df5-1b17d87364e5.png)

Extentions 탭에 들어가 Prettier를 설치  

![image](https://user-images.githubusercontent.com/6462456/167231309-d736117e-afe5-4d43-b092-4f2b138d6638.png)

Settings > **Prettier: Config Path**에 `.prettierrc` 입력  
이렇게 하면 VSCode로 여는 모든 폴더의 `.prettierrc` 파일을 반영하여 에디터에서 파일을 저장할 때마다 적용됨  

![image](https://user-images.githubusercontent.com/6462456/167264773-0fb30459-44c6-470b-9726-20f25dcd59fb.png)

그 다음으로 Settings > **Default Formatter**를
**Prettier - Code formatter**로 설정  

![image](https://user-images.githubusercontent.com/6462456/167264808-f4bd430f-3cbf-4644-be31-ee9673924ec6.png)

이어서 Settings > **Format On Save** 체크  

```json
{
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true
}
```

마지막으로 프로젝트 루트 폴더에 `.prettierrc` 파일 생성 후
위처럼 prettier 적용 규칙을 작성해 주면
이제 저장할때마다 서식이 정리되어 적용된다.  

```zsh
# 1. Prettier를 글로벌로 설치
sudo npm i -g prettier

# 2. Prettier를 이용하여 폴더 혹은 파일을 검사
prettier --check . # .(현재 디렉토리)

# 3. 폴더 혹은 파일 내 전체 파일을 포맷팅하여 저장
prettier --write . # 전체 디렉토리가 수정되니 주의
```

물론 Command Line으로 위와 같이 Prettier를 사용하는 방법도 있으나,  
위처럼 VScode 확장을 이용해 설정하면 저장 시 자동 포맷팅이 적용되므로
따로 commit 때마다 신경쓰지 않아도 된다는 점이 편리함  

### 6-4. Gitmoji-cli 설정

```zsh
sudo npm i -g gitmoji-cli
```

Github commit message를 작성할 때 `gitmoji`를 활용하면 보기도 좋고
단위 commit의 목적을 명확하게 나타낼 수 있어서 좋다.  
설치할 때 sudo 안 붙으면 에러남  

![image](https://user-images.githubusercontent.com/6462456/167769818-d56d98d0-d88c-4d64-997e-ac0d188630d0.png)

```zsh
git commit -m "메시지"

# 대신...

gitmoji -c
```

`gitmoji-cli`를 사용하면 gitmoji 홈페이지에 매번 들락날락 거리지 않아도
적당한 키워드에 맞는 gitmoji를 추천해 준다.  
매우 편리하다... 나만 매번 들락날락 했나??  

## 7. Python

영상 처리부터 시작해서 딥 러닝, 코딩 테스트 문제 풀이 등
파이썬을 사용할 일도 많기 때문에, 관련 환경 설정 또한 필요하다.  

### 7-1. Anaconda 설치

![image](https://user-images.githubusercontent.com/6462456/176612299-aec8b9b9-fd94-415f-aa6f-aa944e8beed7.png)

Mac OS에는 기본적으로 파이썬이 설치되어 있다.  
다만, 3.0 이상의 버젼은 `python3` 명령어로 실행해야 하는 귀찮은
부분들도 있고, 여러 프로젝트에서 쓰일 환경을 애초부터 분리해
관리하는 게 여러 모로 편리하기 때문에 **Anaconda**를 설치한다.

[설치 관련 포스트](https://poodlepoodle.github.io/posts/what-is-anaconda/)

Anaconda의 설치에 관해서는 예전에 정리한 포스트가 있기 때문에
따로 중복되는 내용을 다시 적지는 않겠다.  

## 기타. 참고 링크

- [종합적으로 정리 잘 되어 있는 포스팅](https://subicura.com/2017/11/22/mac-os-development-environment-setup.html)
- ITerm 2
  [폰트 Naver D2coding으로 수정](https://acet.pe.kr/825)
- zsh
  [ITerm 2로 터미널 커스텀하기](https://ooeunz.tistory.com/21)
  [Mac OS 터미널을 이쁘게 꾸며보자](https://bcp0109.tistory.com/341)
  [macOS: 기본 쉘 (shell) 이 된 zsh 설정하기](https://xho95.github.io/macos/cli/shell/zsh/2020/03/04/Setting-Up-the-Zsh-shell-on-Mac.html)
- VScode
  [터미널에서 명령어로 VScode 열기](https://doyoon.tistory.com/1)
- Github Blog
  [Mac OS Ruby 버젼 관련 이슈 rbenv로 해결](https://jojoldu.tistory.com/288)
- Prettier
  [프리티어(Prettier) 설정 안내](https://different-headphones-8fa.notion.site/Prettier-01b90450580847cd8b92245ffc448873)

---

대충 이정도로 일단 마무리..  
생각나는 거 있을 때마다 추가로 기록 예정  
😓