---
layout: post
title: ๐  Mac OS ์ฒ์๋ถํฐ ์ธํํ๊ธฐ - ๊ฐ๋ฐ
date: 2022-05-04 02:55:00 +0900
published: true
categories: [coding, mac os]
tags: [mac os, xcode, vscode, zsh]
---

## 0. ๊ธฐ๋ณธ ์ฌ์ฉ์ ์ค์ ๊น์ง ๋๋ธ ๋จ๊ณ

![image](https://user-images.githubusercontent.com/6462456/166516525-0a32a19e-43fa-4d6e-97f1-652fda6f25ee.png)

[์ ๋ฒ ํฌ์คํ](https://poodlepoodle.github.io/posts/mac-os-setting-basics/)์์ ๋๋ถ๋ถ์ Mac OS ์ฌ์ฉ์ ํ๊ฒฝ ์ค์ ์ ์๋ฃํ๋ค.  
์ด์  ์ฌ์ฉํ๋ ๊ฐ๋ฐ ํ๊ฒฝ์ ๋ณต๊ตฌํด ๋ณด์.....  

## 1. Xcode

![image](https://user-images.githubusercontent.com/6462456/166204362-425d756b-7ded-4dba-977c-15dc7b1399d7.png)

Xcode๋ Mac ์ฑ์คํ ์ด์์ ์ค์นํ  ์ ์๋ค.  
์๋ฐ์ดํธ๋ฅผ ์ ์ ํ๊ณ  ์จ์ ๋ชฐ๋๋๋ฐ ์ต์  ๋ฒ์ ์ **Mac OS 12.0 Monterey ์ด์**์ ํ์๋ก ํ๋ค๊ณ  ํ๋ค.  
๋ด ๋งฅ๋ถ์ด Big Sur๊น์ง๋ง ์ง์ํ๋ ๊ฑธ ์ด๋ป๊ฒ ํ๋ฆฌ... ๊ทธ๋ฅ **์ด์  ๋ฒ์  ๋ค์ด๋ก๋** ๋๋ฅธ๋ค...  

### 1-1. Command Line Tools ์ค์น

```zsh
xcode-select --install
```

Xcode๋ฅผ ์ค์นํ์ง ์๊ณ  `git`, `gcc` ๋ฑ์ ์ฌ๋ฌ ๋๊ตฌ๋ค์ ์ฌ์ฉํ๊ธฐ ์ํ ๋ฐฉ๋ฒ์ผ๋ก๋ **Command Line Tools** ์ค์น๊ฐ ์๋ค. ๋ฌผ๋ก  Xcode๋ฅผ ์ค์นํ๋ฉด ์๋์ผ๋ก ์ค์น๋๋ ๊ฒ์ผ๋ก ํ์ธํ๊ธฐ ๋๋ฌธ์ ๋ณธ์ธ ์ ํ์ ๋ฐ๋ผ ๋ฐฉ๋ฒ์ ๊ณ ๋ฅด๋ฉด ๋  ๊ฒ ๊ฐ๋ค. ๋๋ RN ๊ฐ๋ฐ ์ ์๋ฎฌ๋ ์ดํฐ ์ฌ์ฉ์ด๋ OpenCV ๊ฐ๋ฐํ๊ฒฝ ๋ฑ๋ฑ ๊ณ ๋ คํด์ Xcode๋ฅผ ์์ ์ค์นํ๋ ๊ฒ ๋ ๋์ ๊ฒ์ผ๋ก ํ๋จํ๋ค.  

![image](https://user-images.githubusercontent.com/6462456/166407719-dfffe84b-a93d-43a8-9fdd-553fa13fa7f1.png)

Xcode ํ๋ก์ ํธ ์์ฑ ์ Command Line Tool ์ต์์ด ๋จ๋ฉด ์ ์ค์น๋ ๊ฑฐ์  

### 1-2. Xcode OpenCV-C++ ๊ฐ๋ฐํ๊ฒฝ ์ค์ 

[์์ ์ ์์ฑํ ๋ธ๋ก๊ทธ ๊ธ ์ฐธ๊ณ ](https://poodlepoodle.github.io/posts/opencv-installation-windows-mac/)  

## 2. ITerm 2

![image](https://user-images.githubusercontent.com/6462456/166201976-c67abdfd-61a7-40e3-a96b-8745ae4620bf.png)

[์ค์น ๋งํฌ](https://iterm2.com)  

Mac OS์ ๊ธฐ๋ณธ ํฐ๋ฏธ๋์ ์ฌ์ฉํ  ์๋ ์์ง๋ง,
**ITerm 2**๋ฅผ ์ฌ์ฉํ๋ ๊ฒฝ์ฐ ์ข ๋ Appearence ๋ฉด์์ ์ปค์คํฐ๋ง์ด์ง์ด ๊ฐ๋ฅํ๋ค.  

![image](https://user-images.githubusercontent.com/6462456/166203789-af95c1ce-8f22-4404-9fb9-528a76ddc5d5.png)

๋ง ์ค์นํ Vanilla ์ํ์ ITerm 2  
์ด์ ๋ถํฐ ํฐ๋ฏธ๋ ๋ช๋ น์ด๋ก ์ค์นํ๊ณ  ์ค์ ํด์ผ ํ๋ ๊ฒฝ์ฐ๋ค์ ๋ชจ๋ ๊ธฐ๋ณธ ํฐ๋ฏธ๋์ด ์๋ ITerm์ผ๋ก ์งํํ๊ฒ ๋ค.  

### 2-1. ITerm 2 ํ๋ง ์ค์ 

#### 2-1-1. Color Scheme ์ค์  - **Afterglow**

![image](https://user-images.githubusercontent.com/6462456/166436419-33dd9c5e-a025-4952-a1b2-a04405f5a50a.png)

[color scheme ๋๋ฌ๋ณด๊ธฐ](https://iterm2colorschemes.com)  

์์ ๋งํฌ์์ `.itermcolors` ํ์ผ์ ๋ค์ด๋ฐ์ ํ  
**Preference > Profile > Colors** ์ค์ ์์ **Color Presets...**๋ฅผ ๋๋ฌ ๋ถ๋ฌ์์ค ํ ์ ์ฉํ๋ค.  

#### 2-1-2. ํฐํธ ์ค์  - **Naver D2coding**

![image](https://user-images.githubusercontent.com/6462456/166438876-014731d3-a0b4-4a22-90ab-e42da4d7deb4.png)

[์ค์น ๋งํฌ](https://github.com/naver/d2codingfont/releases/tag/VER1.3.2)  

์ ๋งํฌ์์ ํฐํธ ์ค์น ํ **Profiles > Text**์์ ์ ์ฉ  
ํฐํธ ํฌ๊ธฐ๋ ํ 13px ์ฏค ์ค์ ํ๋ฉด ๊ด์ฐฎ์๋ฏ  

#### 2-1-3. Word jump ๋จ์ถํค ์ค์  - **Natural Text Editing**

![image](https://user-images.githubusercontent.com/6462456/166448868-bc518384-7722-4125-aae5-b24559bb4600.png)

ITerm 2์์ ๊ธฐ๋ณธ์ ์ผ๋ก option + ๋ฐฉํฅํค๋ cmd + ๋ฐฉํฅํค ํน์ ์ญ์  ๋จ์ถํค๊ฐ ์ ๋จนํ์ ์ถ๊ฐ๋ก Keys ํญ ๊ฐ์ ์ค์ ํ๊ณ  ์๋ค๊ฐ Stackoverflow์์  
**Profiles > Keys > Preset...** ์์ **Natural Text Editing**์ผ๋ก ์์ ํ๋ฉด ๋๋ค๋ ๊ฑธ ์์๋ค.  

#### 2-1-4. ๊ธฐํ ์ค์ 

- **General > Closing > Confirm "Quit ITerm 2"** ์ฒดํฌ ํด์ 
- **Appearence > General > Theme - Mininal**๋ก ์ค์ 
- **Profiles > Text > Cursor - Vertical Bar** ์ฒดํฌ ๋ฐ **Blinking cursor** ์ฒดํฌ
- **Profiles > Window > Transparency** ๊ด๋ จ ์ค์  ๋ชจ๋ ํด์ 

### 2-2. Homebrew ์ค์น

[์ค์น ๋งํฌ](https://brew.sh/index_ko)  

```zsh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Homebrew** : Mac OS ์ ์ฉ ํ๋ก๊ทธ๋จ๋ค์ ์ค์นํ  ์ ์๋ **ํจํค์ง ๊ด๋ฆฌ์**  
์ค์นํ๋๋ฐ ์๊ฐ ์ข ๊ฑธ๋ฆผ  

![image](https://user-images.githubusercontent.com/6462456/166426354-3f250887-1286-4cca-87de-480252d371f5.png)

์์์ Xcode ๊น๋ฉด์ Command Line Tools ์ค์น๋ ๊ฑธ๋ก ์์๋๋ฐ ๋ ์ค์นํ ๊ฑฐ๋๊ณ  ๋ฌผ์ด๋ณธ๋ค. ์์ผ๊น...?  
์ผ๋จ์ ๋ฌด์ง์ฑ ์ํฐ ์น๊ณ  ์ข ๊ธฐ๋ค๋ฆฌ๋ฉด ์ค์น๊ฐ ์๋ฃ๋๋ค  

```zsh
brew install wget
```

๋น์ฅ ์๊ฐ๋๋ ๊ฒ ์์ผ๋ `wget` ์ ๋๋ง ์ค์นํด ์ฃผ๊ณ  ๋์ด๊ฐ  

### 2-3. Oh-my-zsh ์ค์น ๋ฐ zsh ์ค์ 

[์ค์น ๋งํฌ](https://ohmyz.sh/#install)  

```zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

๋ค์์ผ๋ก๋ **oh-my-zsh**์ ์ค์นํด ์ค ์ฐจ๋ก์ด๋ค.  
oh-my-zsh์ zsh ์ค์ ์ ๊ด๋ฆฌํด ์ฃผ๋ ์คํ์์ค ํ๋ ์์ํฌ์ด๋ค.  
Catalina ์ดํ๋ถํฐ์ธ๊ฐ Mac OS์ ๊ธฐ๋ณธ ํฐ๋ฏธ๋์ด `bash`์์ `zsh`๋ก ๋ฐ๋์๋ค๊ณ  ํ๋๋ฐ
์๋๋ถํฐ zsh์ ์ฌ์ฉํ๋ ์ฌ๋๋ค์๊ฒ๋ ์ต์ํ ์ด๋ฆ์ด๋ค.  
์ด์ฐจํผ ๊นกํต ์ํ์์ ๊น๋ค๊ณ  ์๊ฐํด `~/.zshrc` ์ ๋ด์ฉ์ ๋น์ด ์๋ค๊ณ  ๊ฐ์ ํ๊ณ  ๋ฐฑ์ ์์ด ๊ทธ๋ฅ ์ค์นํจ  

![image](https://user-images.githubusercontent.com/6462456/166429055-b18adbda-40a8-4365-83f4-54d3dc11e1c6.png)

์ค์น๊ฐ ์๋ฃ๋๋ฉด ๊ต์ฅํ ์๋ก๋ฌ๋กํด์ง ๊ฑธ ๋ณผ ์ ์๋๋ฐ ์ด๋๋ก ์ธ ๊ฑด ์๋๋๊น ๋ช ๊ฐ์ง ์ถ๊ฐ ์ค์ ์ ํด์ค์ผ ํจ  

#### 2-3-1. zsh ํ๋ง ์ค์  - **powerlevel10k**

[ํ๋ง ๋๋ฌ๋ณด๊ธฐ](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)  
[powerlevel10k ์ค์น ์๋ด](https://github.com/romkatv/powerlevel10k#manual)  

์์ ํ๋ง ๋๋ฌ๋ณด๊ธฐ ๊ฐ๋ฉด ์ ์ฉํ  ์ ์๋ ๋ค์ํ zsh ํ๋ง๋ค์ด ์๋ค.  
์ด๋ค ๊ฑธ ๊ณ ๋ฅด๋๋์ ๋ฐ๋ผ ์์์ด๋ ๋ชจ์์ ๊พธ๋ฐ ์ ์์ง๋ง ํน๋ณํ ๊ธฐ๋ฅ์ด ๊ฐ๋ ฅํด์ ๋ง์ด ์ ํ๋ฐ๋ ๋ช ๊ฐ์ง ์ ํ์ง๊ฐ ์๋ค.  
๋๋ ๊ทธ ์ค์์ **powerlevel10k**๋ฅผ ์ค์นํด๋ณด๋ ค๊ณ  ํจ  

```zsh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

![image](https://user-images.githubusercontent.com/6462456/166489912-066967de-ed35-4948-9189-4f398aa9c9da.png)

๋ค์ด๋ฐ์ ์ค ๋ค์ `~/.zshrc` ํ์ผ ๋ด๋ถ์ `ZSH_THEME="powerlevel10k/powerlevel10k"` ๋ถ๋ถ์ ์์ ํด์ฃผ๋ฉด ๋๋ค.  
์ดํ `source ~/.zshrc` ํน์ ITerm ์ฌ ์คํ  

![image](https://user-images.githubusercontent.com/6462456/166490599-9c0e709f-129d-4fc9-bd9b-551aa0b823e5.png)

์๋์ผ๋ก powerlevel10k์ configuration script๊ฐ ์คํ๋๋ค.  
์ทจํฅ์ ๋ง๊ฒ ์ ๋นํ ๊ณจ๋ผ์ฃผ๋ฉด์ ๋์ด๊ฐ๋ฉด ๋จ  
๋ง์ฝ ์ค์ ์ ๋ง์ณค๋๋ฐ ๋ค์ ๊ณ ๋ฅด๊ณ  ์ถ๋ค๋ฉด `p10k configure` ์คํ ใฑใฑ  

#### 2-3-2. zsh ์ถ๊ฐ ์ปค์คํฐ๋ง์ด์ง

- ๋ช๋ น์ด ์คํ ์๋ง๋ค ์์ ๋ถ๋ ์ฌ์ฉ์ ๋ฐ ์ปดํจํฐ ์์ ๊ธฐ  

{% raw %}
```zsh
prompt_context() { 
	if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then 
    	prompt_segment black default "%(!.%{%F{yellow}%}.)$USER" 
    fi 
}
```
{% endraw %}

`~/.zshrc` ์๋ ๋ถ๋ถ์ ์ ๋ด์ฉ์ ๋ถ์ฌ ์ฃผ๋ฉด ์์จ ์ ์๋ค.  

- zsh Syntax Highlighting ๋ฐ auto-suggestion ์ค์น ํ ์ ์ฉ  

```zsh
# install zsh syntax highlighting plugin
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
# install zsh auto-suggestion plugin
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# ~/.zshrc ํ์ผ ๋ด์ ์์ 
plugins=(
  git
  zsh-syntax-highlighting
  zsh-autosuggestions
)
```

- ํฐ๋ฏธ๋ ์คํ ์ ๋จ๋ `last login : ....์ผ์ On ttys..` ์ ๋จ๋๋ก ์ค์   

```zsh
touch .hushlogin
```

ํฐ๋ฏธ๋ ์คํ ํ `root` ๊ฒฝ๋ก์์ ๋น `.hushlogin` ํ์ผ ์์ฑ ํ ํฐ๋ฏธ๋ ๋ค์ ์์ํ๋ฉด ์ ์ฉ๋จ  

## 3. VScode

[์ค์น ๋งํฌ](https://code.visualstudio.com)  

Stable build๋ก ์ค์น  

### 3-1. VScode ํ๋ง ์ค์  - **Shades of Purple**

![image](https://user-images.githubusercontent.com/6462456/166473998-a740ca49-f894-4dc9-8c56-f87dcaac29fe.png)

์์ ์ ์ฐ๋ ํ๋ง๊ฐ ๋ญ์ง ๊ธฐ์ต์ด ์๋์ ๊ทธ๋ฅ ๊ด์ฐฎ์ ๋ณด์ด๋ ๊ฑธ๋ก ์ค์นํ๋ค

### 3-2. zsh์์ code ๋ช๋ น์ด๋ก ์คํํ๋๋ก ์ค์ 

![image](https://user-images.githubusercontent.com/6462456/166474428-8eba120a-6828-40f3-acd3-38fe150302b3.png)

**Cmd + Shift + P** ๋๋ฅธ ๋ค์  
**Shell Command: Install 'code' command in PATH** ์ ํ  

## 4. Git

```zsh
brew install git git-lfs
```

๊ธฐ๋ณธ์ผ๋ก ์ค์น๋์ด ์์ผ๋ ์ต์  ๋ฒ์ ์ผ๋ก ์๊ทธ๋ ์ด๋  

```zsh
git config --global user.name "poodlepoodle"
git config --global user.email "chammal97@naver.com"
git config --global core.precomposeunicode true
git config --global core.quotepath false
```

๊ณ์  ์ค์  ๋ฐ ํ๊ธ ๊ด๋ จ ๋ช๊ฐ์ง ์ถ๊ฐ ์ค์ ์ ํด ์ค๋ค.  

## 5. Github Blog

```zsh
git clone https://github.com/poodlepoodle/poodlepoodle.github.io.git
```

๋จผ์  github์ ์ฌ๋ฆฐ ๋ด์ฉ๋ค์ cloneํด ์จ๋ค  

### 5-1. rbenv๋ฅผ ํตํ ruby ๋ฒ์  ๋ณ๊ฒฝ

```zsh
brew install rbenv ruby-build
rbenv versions
rbenv install 3.1.2
```

![image](https://user-images.githubusercontent.com/6462456/166504804-9482268c-95c5-4f37-84d2-5c6015d4004e.png)

์ ๋ช๋ น์ด๋ฅผ ์น๋ฉด ํ์ฌ Mac OS์ ๊น๋ ค ์๋ ruby๊ฐ system ๋ฒ์ ผ์ ์ฌ์ฉํ๊ณ  ์์์ ์ ์ ์๋ค.  
๊ทธ๋๋ก `bundle` ๋ช๋ น์ด๋ฅผ ์ํํ๊ฒ ๋๋ฉด ์ค๋ฅ๊ฐ ๋ฐ์ํ๊ธฐ ๋๋ฌธ์,
`rbenv install -l` ๋ช๋ น์ด๋ก ์ค์น ๊ฐ๋ฅํ stable ๋ฒ์ ๋ค์ ํ์ธํ ํ ๊ณจ๋ผ์ ๊น์์ค๋ค.  
_(2022-05-04 ๊ธฐ์ค์ผ๋ก 3.1.2 ์ค์น)_  

```zsh
# ruby ๋ฒ์  ๋ฐฉ๊ธ ์ค์นํ 3.1.2๋ก ์ง์ 
rbenv global 3.1.2

# ~/.zshrc ๋ด ์๋ ๋ด์ฉ ์ถ๊ฐ
[[ -d ~/.rbenv  ]] && \
  export PATH=${HOME}/.rbenv/bin:${PATH} && \
  eval "$(rbenv init -)"
```

์ค์นํ ๋ฒ์ ผ์ ๊ธ๋ก๋ฒ ๋ฒ์ ์ผ๋ก ์ง์ ํด ์ค ๋ค์,
์์ ๋ด์ฉ์ `~/.zshrc` ๋ง์ง๋ง์ ์ถ๊ฐํด ์ค๋ค.  

![image](https://user-images.githubusercontent.com/6462456/166509263-7ba98095-69f7-422b-ae9a-a30d9bf973da.png)

์ดํ `bundle` ๋ช๋ น์ด๋ฅผ ์คํํ๋ฉด ์๋์ผ๋ก ํจํค์ง๋ค์ด ์ ๊น๋ฆฐ๋ค.  

```zsh
# ๋ก์ปฌ์์ ๋ธ๋ก๊ทธ ์คํ
bundle exec jekyll serve

# ํฌ์คํธ ์ฌ๋ฆด ๋ commit message ์์
git commit -m ":memo: [docs]: edit some posts"
git push origin main
```

๊ตณ์ด ๋ก์ปฌ์์ ์ ๋๋ ค๋ด๋ **typora** ๊ฐ์ ๋งํฌ๋ค์ด ์๋ํฐ๋ก ๋ฏธ๋ฆฌ ๋ณด๊ณ  ๋ฐํํ  ๋๋ง pushํด๋ ๋  ๋ฏ..  

## 6. React, Typescript

ํ๋ ๋ ๋ผ๊ฐ๋ฉด์ ํ๋ก ํธ์๋ ๊ณผ์  ๋ Prettier ๋ค์ ์ธํํด์ผ๊ฒ ๋ค๋
๊ฑฑ์ ์ด ๋ค์๋๋ฐ ์ ์ Node ๋ ๋ผ๊ฐ ๊ฑด ์๊ฐ ๋ชปํ๋ค....  

### 6-1. Node.js ์ค์น

![image](https://user-images.githubusercontent.com/6462456/167136932-08b34465-b20d-45b7-9aac-aa4032e37370.png)

[์ค์น ๋งํฌ](https://nodejs.org/en/)

์ผ์ชฝ์ **LTS**๋ก ์ ํํด์ ๋ค์ด๋ก๋ ํ ์ค์น  

```zsh
sudo npm install npx -g
```

์ ๋ช๋ น์ด๋ฅผ ํตํด npx ์ต์  ๋ฒ์  ์ค์น  
์ด๋ฏธ ํ์ผ์ด ์๋ค๋ ๋ฅ ์๋ฌ๊ฐ ๋จ๋๋ฐ ใฑใ๋ค๊ณ  ํจ  

```zsh
node -v # v16.15.0
npm -v #8.5.5
npx -v #8.5.5
```

22-05-06 ๊ธฐ์ค ์ค์น๋ ๋ฒ์ ผ ์ฒดํฌ  
React ๊ฐ๋ฐ ์ node ๋ฒ์ ์ 13 ์ดํ, 17์ ํผํด์ ์ค์นํ๋ผ๊ณ  ํ๋ค...  

```zsh
npm install
```

`react-scripts: command not found` ์๋ฌ ๋ณด๊ณ  ์ถ์ง ์๋ค๋ฉด  
ํ๋ก์ ํธ ์คํํ๊ธฐ ์ ์ ์์ง ๋ง์...  

### 6-2. Styled-Components ์ค์น

```zsh
npm install styled-components
```

Css ์คํ์ผ๋ง ๋ฐฉ์ ์ค `Styled-Components`๋ฅผ ์ฌ์ฉํ๊ธฐ ์ํด ์ค์น  

![image](https://user-images.githubusercontent.com/6462456/167169820-8e2fa7c2-6130-48fe-b7fb-fd294174999c.png)

VScode์์ Styled-Components **์๋ ์์ฑ ๊ธฐ๋ฅ**์ ์ฌ์ฉํ๊ธฐ ์ํ ํ์ฅ์  

### 6-3. Prettier ์ค์ 

![image](https://user-images.githubusercontent.com/6462456/167231278-c3479af8-a98f-497c-9df5-1b17d87364e5.png)

Extentions ํญ์ ๋ค์ด๊ฐ Prettier๋ฅผ ์ค์น  

![image](https://user-images.githubusercontent.com/6462456/167231309-d736117e-afe5-4d43-b092-4f2b138d6638.png)

Settings > **Prettier: Config Path**์ `.prettierrc` ์๋ ฅ  
์ด๋ ๊ฒ ํ๋ฉด VSCode๋ก ์ฌ๋ ๋ชจ๋  ํด๋์ `.prettierrc` ํ์ผ์ ๋ฐ์ํ์ฌ ์๋ํฐ์์ ํ์ผ์ ์ ์ฅํ  ๋๋ง๋ค ์ ์ฉ๋จ  

![image](https://user-images.githubusercontent.com/6462456/167264773-0fb30459-44c6-470b-9726-20f25dcd59fb.png)

๊ทธ ๋ค์์ผ๋ก Settings > **Default Formatter**๋ฅผ
**Prettier - Code formatter**๋ก ์ค์   

![image](https://user-images.githubusercontent.com/6462456/167264808-f4bd430f-3cbf-4644-be31-ee9673924ec6.png)

์ด์ด์ Settings > **Format On Save** ์ฒดํฌ  

```json
{
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true
}
```

๋ง์ง๋ง์ผ๋ก ํ๋ก์ ํธ ๋ฃจํธ ํด๋์ `.prettierrc` ํ์ผ ์์ฑ ํ
์์ฒ๋ผ prettier ์ ์ฉ ๊ท์น์ ์์ฑํด ์ฃผ๋ฉด
์ด์  ์ ์ฅํ ๋๋ง๋ค ์์์ด ์ ๋ฆฌ๋์ด ์ ์ฉ๋๋ค.  

```zsh
# 1. Prettier๋ฅผ ๊ธ๋ก๋ฒ๋ก ์ค์น
sudo npm i -g prettier

# 2. Prettier๋ฅผ ์ด์ฉํ์ฌ ํด๋ ํน์ ํ์ผ์ ๊ฒ์ฌ
prettier --check . # .(ํ์ฌ ๋๋ ํ ๋ฆฌ)

# 3. ํด๋ ํน์ ํ์ผ ๋ด ์ ์ฒด ํ์ผ์ ํฌ๋งทํํ์ฌ ์ ์ฅ
prettier --write . # ์ ์ฒด ๋๋ ํ ๋ฆฌ๊ฐ ์์ ๋๋ ์ฃผ์
```

๋ฌผ๋ก  Command Line์ผ๋ก ์์ ๊ฐ์ด Prettier๋ฅผ ์ฌ์ฉํ๋ ๋ฐฉ๋ฒ๋ ์์ผ๋,  
์์ฒ๋ผ VScode ํ์ฅ์ ์ด์ฉํด ์ค์ ํ๋ฉด ์ ์ฅ ์ ์๋ ํฌ๋งทํ์ด ์ ์ฉ๋๋ฏ๋ก
๋ฐ๋ก commit ๋๋ง๋ค ์ ๊ฒฝ์ฐ์ง ์์๋ ๋๋ค๋ ์ ์ด ํธ๋ฆฌํจ  

### 6-4. Gitmoji-cli ์ค์ 

```zsh
sudo npm i -g gitmoji-cli
```

Github commit message๋ฅผ ์์ฑํ  ๋ `gitmoji`๋ฅผ ํ์ฉํ๋ฉด ๋ณด๊ธฐ๋ ์ข๊ณ 
๋จ์ commit์ ๋ชฉ์ ์ ๋ชํํ๊ฒ ๋ํ๋ผ ์ ์์ด์ ์ข๋ค.  
์ค์นํ  ๋ sudo ์ ๋ถ์ผ๋ฉด ์๋ฌ๋จ  

![image](https://user-images.githubusercontent.com/6462456/167769818-d56d98d0-d88c-4d64-997e-ac0d188630d0.png)

```zsh
git commit -m "๋ฉ์์ง"

# ๋์ ...

gitmoji -c
```

`gitmoji-cli`๋ฅผ ์ฌ์ฉํ๋ฉด gitmoji ํํ์ด์ง์ ๋งค๋ฒ ๋ค๋ฝ๋ ๋ฝ ๊ฑฐ๋ฆฌ์ง ์์๋
์ ๋นํ ํค์๋์ ๋ง๋ gitmoji๋ฅผ ์ถ์ฒํด ์ค๋ค.  
๋งค์ฐ ํธ๋ฆฌํ๋ค... ๋๋ง ๋งค๋ฒ ๋ค๋ฝ๋ ๋ฝ ํ๋??  

## 7. Python

์์ ์ฒ๋ฆฌ๋ถํฐ ์์ํด์ ๋ฅ ๋ฌ๋, ์ฝ๋ฉ ํ์คํธ ๋ฌธ์  ํ์ด ๋ฑ
ํ์ด์ฌ์ ์ฌ์ฉํ  ์ผ๋ ๋ง๊ธฐ ๋๋ฌธ์, ๊ด๋ จ ํ๊ฒฝ ์ค์  ๋ํ ํ์ํ๋ค.  

### 7-1. Anaconda ์ค์น

![image](https://user-images.githubusercontent.com/6462456/176612299-aec8b9b9-fd94-415f-aa6f-aa944e8beed7.png)

Mac OS์๋ ๊ธฐ๋ณธ์ ์ผ๋ก ํ์ด์ฌ์ด ์ค์น๋์ด ์๋ค.  
๋ค๋ง, 3.0 ์ด์์ ๋ฒ์ ผ์ `python3` ๋ช๋ น์ด๋ก ์คํํด์ผ ํ๋ ๊ท์ฐฎ์
๋ถ๋ถ๋ค๋ ์๊ณ , ์ฌ๋ฌ ํ๋ก์ ํธ์์ ์ฐ์ผ ํ๊ฒฝ์ ์ ์ด๋ถํฐ ๋ถ๋ฆฌํด
๊ด๋ฆฌํ๋ ๊ฒ ์ฌ๋ฌ ๋ชจ๋ก ํธ๋ฆฌํ๊ธฐ ๋๋ฌธ์ **Anaconda**๋ฅผ ์ค์นํ๋ค.

[์ค์น ๊ด๋ จ ํฌ์คํธ](https://poodlepoodle.github.io/posts/what-is-anaconda/)

Anaconda์ ์ค์น์ ๊ดํด์๋ ์์ ์ ์ ๋ฆฌํ ํฌ์คํธ๊ฐ ์๊ธฐ ๋๋ฌธ์
๋ฐ๋ก ์ค๋ณต๋๋ ๋ด์ฉ์ ๋ค์ ์ ์ง๋ ์๊ฒ ๋ค.  

- ํฐ๋ฏธ๋ ์คํ ์ ์๋์ผ๋ก **(base)** ํ๊ฒฝ ์๋ ํ์ฑํ ํด์   

```zsh
conda config --set auto_activate_base false
```

Anaconda๋ฅผ ์ค์นํ๊ณ  ๋์ ํฐ๋ฏธ๋์ ์๋ก ์ผค ๋๋ง๋ค
`(base)` ํ๊ฒฝ์ด ํ์ฑํ๋ ์ฑ๋ก ์ด๋ฆฌ๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.  

์์ ๋ช๋ น์ด๋ฅผ ํตํด ์๋ ํ์ฑํ๋ฅผ ํด์ ํ๋ฉด
๋งค๋ฒ ์๋ก์ด ์ธ์์ด๋ ํฐ๋ฏธ๋์ ์ด ๋
๋๋ ์ด๊ฐ ๋์ ๋๊ฒ ๋ ๊ฑธ๋ฆฌ๋ ๊ฒ์ ํ์ธํ  ์ ์๋ค.  

## ๊ธฐํ. ์ฐธ๊ณ  ๋งํฌ

- [์ขํฉ์ ์ผ๋ก ์ ๋ฆฌ ์ ๋์ด ์๋ ํฌ์คํ](https://subicura.com/2017/11/22/mac-os-development-environment-setup.html)
- ITerm 2  
  [ํฐํธ Naver D2coding์ผ๋ก ์์ ](https://acet.pe.kr/825)  
- zsh  
  [ITerm 2๋ก ํฐ๋ฏธ๋ ์ปค์คํํ๊ธฐ](https://ooeunz.tistory.com/21)  
  [Mac OS ํฐ๋ฏธ๋์ ์ด์๊ฒ ๊พธ๋ฉฐ๋ณด์](https://bcp0109.tistory.com/341)  
  [macOS: ๊ธฐ๋ณธ ์ (shell) ์ด ๋ zsh ์ค์ ํ๊ธฐ](https://xho95.github.io/macos/cli/shell/zsh/2020/03/04/Setting-Up-the-Zsh-shell-on-Mac.html)  
- VScode  
  [ํฐ๋ฏธ๋์์ ๋ช๋ น์ด๋ก VScode ์ด๊ธฐ](https://doyoon.tistory.com/1)  
- Github Blog  
  [Mac OS Ruby ๋ฒ์ ผ ๊ด๋ จ ์ด์ rbenv๋ก ํด๊ฒฐ](https://jojoldu.tistory.com/288)  
- Prettier  
  [ํ๋ฆฌํฐ์ด(Prettier) ์ค์  ์๋ด](https://different-headphones-8fa.notion.site/Prettier-01b90450580847cd8b92245ffc448873)  

---

๋์ถฉ ์ด์ ๋๋ก ์ผ๋จ ๋ง๋ฌด๋ฆฌ..  
์๊ฐ๋๋ ๊ฑฐ ์์ ๋๋ง๋ค ์ถ๊ฐ๋ก ๊ธฐ๋ก ์์   
๐