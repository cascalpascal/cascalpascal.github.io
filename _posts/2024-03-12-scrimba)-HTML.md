---
layout: post
author: Cascal Pascal
tags:
  - devroad
  - full stack
  - language
  - HTML
---

>**Course**
>
>[[DevRoad] Full Stack Developer](https://cascalpascal.github.io/devroad-full-stack-developer)

>**Bookmarks**
>
>- [Intro](#html-&-css-&-js)
>
>- [Build your website](#build-your-website)

---


# HTML & CSS & JS

![HTML & CSS & JS(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312144718.png?raw=true)

자동차 제작에 비유하면, HTML에서 부품을 제작해 자동차를 만들고 CSS에서 자동차를 색칠하고 JavaScript에서 자동차에 엔진을 넣는다고 볼 수 있다.
이를 홈페이지 제작에 적용하면 다음과 같다.

![HTML & CSS & JS(2)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312144905.png?raw=true)

HTML로 버튼, 사진, 내용과 같이 홈페이지를 구성하는 요소를 작성하고 CSS로 홈페이지에 색을 입혀주고 JavaScript를 통해 데이터 베이스를 관리하거나 유저 간 거래를 생성하는 등의 기능을 입혀준다.



# Build your website



### 앞뒤 헤딩을 통해 글씨 크기 조정

```
<h1>Who are you?</h1>  
<h3>Hi, my name is Pascal.</h3>  
<p>Nice to meet you.</p>
```

![html-heading(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312163529.png?raw=true)



### 같은 디렉토리 안에 있는 이미지 넣고 사이즈 스케일링 하기

```
<img src="이미지파일명.jpg" width="50%">
```

![html-imagescale(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312163500.png?raw=true)



### 코드를 편하게 관리하기 위해 문단 나누기 - div 사용

```
<div>  
    <h1>Who are you?</h1>  
    <h3>Hi, my name is Pascal.</h3>  
    <p>Nice to meet you.</p>  
    <div>
	    <img src="test0.jpeg" width="50%">  
    </div>
</div>
```


### button 생성

```
<button>  
    Nice!  
</button>
```

![html-button(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312163434.png?raw=true)


### Input 칸 추가

```
<input type="text" placeholder="What's your name?">
```

![html-input(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312163336.png?raw=true)

#### - input type의 종류
- date
- time
- password
- color
- file: 파일 선택


### Anchor tag 사용하여 링크 연결

```
Allow me to provide more details about myself <a href="연결할 파일 또는 주소">here.</a>
```

![html-anchor(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312165717.png?raw=true)

- 만약 새 창으로 링크를 열게 하고 싶다면 target 추가

```
<a href="연결할 파일 또는 주소" target="_blank">here.</a>
```



### Proper document structure

```
<!DOCTYPE html>  
<html>  
<head>  
	<!-- Fill in -->
</head>  
<body>  
	<!-- Fill in -->
</body>  
</html>
```

- !DOCTYPE: 어떤 파일을 작성할 것인지
- html
- head: 인터넷 창의 탭에 뜨는 요소를 작성
- body: 인터넷 창의 페이지에 뜨는 요소를 작성

![html-structure(1)](https://github.com/cascalpascal/cascalpascal.github.io/assets/133131020/22a27a2c-b895-468a-a8ad-17c2d770916f)



### Lists

- ol(ordered list)

```
<p>Here are some of my favorite nicknames. Call me whatever you like!</p>  
<ol>  
    <li>Mr.Frog</li>  
    <li>Froggy</li>  
    <li>Caspal</li>  
    <li>Lizardus</li>  
</ol>
```

![html-orderedlist(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312163500.png?raw=true)

- ul(unordered list)

```
<p>Here are some of my favorite nicknames. Call me whatever you like!</p>  
<ul>  
    <li>Mr.Frog</li>  
    <li>Froggy</li>  
    <li>Caspal</li>  
    <li>Lizardus</li>  
</ul>
```

![html-unorderedlist(1)](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312174234.png?raw=true)






---

#### Reference

-  https://scrimba.com/learn/htmlandcss
