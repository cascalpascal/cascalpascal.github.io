---
layout: post
author: Cascal Pascal
tags:
  - devroad
  - language
  - css
---

>**Course**
>
>[[DevRoad] Full Stack Developer](https://cascalpascal.github.io/devroad-full-stack-developer)

>**Bookmarks**
>
>- [CSS syntax](#css-syntax)
>- [CSS classes](#css-classes)
>- [Margins](#margins)
>- [Padding](#padding)
>- [Border](#border)
>- [Flexbox](#flexbox)

---

<br>

# CSS syntax

CSS 는 page의 특정 element(HTML의 특정 element)를 선택하여 스타일링한다. 

![[Pasted image 20240326101409.png]]

<br>

```css
/* styles.css*/

body {
    background: green;     /* red, blue, yellow, hexcode etc.  */
    color: white;             /* red, blue, yellow, etc */
    font-size: 20px;        /* 0px - 100px and beyond */
    font-weight: normal;   /* lighter, normal, bold  */
    text-align: center;      /* left, center or right  */ 
    margin-top: 8px;        /* From 0px and upwards   */
}
```

![[Pasted image 20240326101933.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326101933.png?raw=true)

<br>
## Link to the CSS file

```html
<!--index.html-->

<html>
    <head>
     <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        <img src="google.png" />
        <input type="text" />
    </body>
</html>
```

![[Pasted image 20240326103239.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326103239.png?raw=true)

<br>

```css
/* styles.css*/

img {
    width: 300px;
}

input {
    width: 400px;
}
```

![[Pasted image 20240326103558.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326103558.png?raw=true)

<br>

## Inline & block elements

Elements를 가로로 나열하고 싶으면 inline 사용.

![[Pasted image 20240326103957.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326103957.png?raw=true)

Elements를 세로로 나열하고 싶으면 block 사용.

![[Pasted image 20240326104118.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326104118.png?raw=true)

<br>

![[Pasted image 20240326103844.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326103844.png?raw=true)

```css
/* styles.css*/

img {
    display: block;
    width: 300px;
}

input {
    display: block;
    width: 400px;
}
```

![[Pasted image 20240326104747.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326104747.png?raw=true)

<br>

## Margin top

```css
/* styles.css*/

img {
    margin-top: 100px;
    display: block;
    width: 300px;
}

input {
    display: block;
    width: 400px;
}
```

![[Pasted image 20240326105019.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326105019.png?raw=true)

<br>

# CSS classes

### div에 class 속성을 주고 변수 할당하기

```html
<!--index.html-->

<html>
    <head>
    <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div class="main">
            <!-- Challenge - part 1: 
            Add a class to each of these two elements -->
            <img class="logo-img" src="google.png" />
            <input class="search-input" type="text" />
        </div>  
    </body>
</html>
```

```css
/* styles.css*/

.main {
    margin-top: 100px;
}

.logo-img {
    display: block;
    width: 300px;
}

.search-input {
    display: block;
    width: 400px;
}
```

![[Pasted image 20240326105019.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326105019.png?raw=true)

<br>

# Margins

margin-top, margin-left, margin-right, margin-bottom 에 값을 지정해서 공백 크기를 조절할 수 있다. 단, 위아래 연속적인 a, b element가 있다고 가정할 때, a element의 margin-bottom과 b element의 margin-top은 충돌하여 둘 중 더 큰 margin만 적용된다.

```css
/* styles.css*/

.main {
    margin-top: 100px;
}

.logo-img {
    display: block;
    width: 300px;
    margin-bottom: 20px;
}

.search-input {
    display: block;
    width: 400px;
}
```

![[Pasted image 20240326112043.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326112043.png?raw=true)


## Centering elements

Element를 중앙 정렬 시키기 위해선 ```display: block```으로 수평의 공간을 모두 차지하고 ```width```를 가지고 있어야 한다. 그리고 ```margin left/right: auto``` 로 하여 왼쪽, 오른쪽의 모든 available한 공간을 공백으로 두어  element를 중앙에 정렬할 수 있다.

```css
/* styles.css*/

.main {
    margin-top: 100px;    
}

.logo-img {
    display: block;
    width: 300px;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
}

.search-input {
    display: block;
    width: 400px;
    margin-left: auto;
    margin-right: auto;
}
```

![[Pasted image 20240326112917.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326112917.png?raw=true)

<br>

# Padding

padding을 통해 element 내에 작성한 글자에 상하좌우 공백을 줄 수 있다. margin과 비슷하지만 margin은 전체 페이지와 element간의 공백을 다루고 padding은 element 내에서 다룬다.

### Padding example

```css
.card {
    color: #222222;
    background: lightgray;
    width: 300px;
    margin-top: 50px;
    margin-left: auto;
    margin-right: auto;

    padding-top: 100px;
    padding-right: 100px;
}
```

![[Pasted image 20240326113648.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326113648.png?raw=true)

<br>

# Border

```css
.card {
    color: #222222;
    background: lightgray;
    width: 300px;
    margin-top: 50px;
    margin-left: auto;
    margin-right: auto;
    
    border: 8px solid blue;
    
    padding-top: 20px;
    padding-right: 20px;
    padding-bottom: 20px;
    padding-left: 20px;
}
```

![[Pasted image 20240326113952.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326113952.png?raw=true)

border 모서리를 둥글게 하고 싶다면 다음을 추가한다.

```css
border-radius: 30px;
```

![[Pasted image 20240326114116.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326114116.png?raw=true)

<br>

### button 꾸미기

```css
button {
    color: #0f1419;
    border: 1px solid #cfd9de;
    border-radius: 20px;
    background: white;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 20px;
    padding-right: 20px;
    font-weight: bold;
}
```

![[Pasted image 20240326114956.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326114956.png?raw=true)

<br>

### Google 따라하기

```css
/* styles.css*/

.main {
    margin-top: 100px;    
}

.logo-img {
    display: block;
    width: 300px;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
}

.search-input {
    display: block;
    width: 400px;
    margin-left: auto;
    margin-right: auto;
    line-height: 24px;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 30px;
    padding-right: 30px;
    border: 1px solid #dfe1e5;
    border-radius: 24px;
}
```

![[Pasted image 20240326115551.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326115551.png?raw=true)

<br>

**button 추가**

```html
<!--index.html-->

<html>
    <head>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div class="main">
            <img class="logo-img" src="google.png" />
            <input class="search-input" type="text" />
            <button class="btn">Google Search</button>
        </div>
    </body>
</html>
```

```css
/* styles.css*/

.btn {
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-top: 30px;
    background: #dfe1e5;
    border: none;
    padding-top: 8px;
    padding-bottom: 8px;
    padding-left: 16px;
    padding-right: 16px;
    border-radius: 4px;
    font-size: 14px;
}
```

![[Pasted image 20240326120714.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240326120714.png?raw=true)

<br>

# Flexbox

Flex layout always consists of a container and its direct children.

```html
<!--index.html-->

<html>
    <head>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        <div class="nav-wrapper">
            <div class="item">▽ Shoes</div>
            <div class="item">▽ Hoodies</div>
            <div class="item">▽ T Shirts</div>
        </div>
    </body>
</html>
```

```css
/*styles.css*/

.nav-wrapper {
    display: flex;
    justify-content: center;
}

.item {
    text-align: center;
    border: 1px solid black;
    padding: 10px;
    margin-top: 10px;
    margin-bottom: 10px;
    margin-left: 10px;
    margin-right: 10px;
}
```


![[Pasted image 20240402091953.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240402091953.png?raw=true)

<br>

### Google 따라하기 예제

```html
<!-- index.html-->

<html>
    <head>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div class="main">
            <img class="logo-img" src="google.png" />
            <input class="search-input" type="text" />
            <div class="btn-wrapper">
                <button class="btn">Google Search</button>
                <button class="btn">I'm Feeling Lucky</button>
            </div>
        </div>
    </body>
</html>
```

```css
/*styles.css*/

.main {
    margin-top: 100px;    
}

.logo-img {
    display: block;
    width: 300px;
    margin-bottom: 20px;
    margin-left: auto;
    margin-right: auto;
}

.search-input {
    display: block;
    width: 400px;
    margin-left: auto;
    margin-right: auto;
    line-height: 24px;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 30px;
    padding-right: 30px;
    border: 1px solid #dfe1e5;
    border-radius: 24px;
}

.btn-wrapper {
    display: flex;
    justify-content: center;
}

.btn {
    margin-left: 4px;
    margin-right: 4px;
    margin-top: 30px;
    background: #dfe1e5;
    border: none;
    padding-top: 8px;
    padding-bottom: 8px;
    padding-left: 16px;
    padding-right: 16px;
    border-radius: 4px;
    font-size: 14px;
}
```

![[Pasted image 20240402092946.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240402092946.png?raw=true)

<br>

# 내 프로젝트에 적용

```html
<!--index.html-->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="styles.css">
    <title>Title</title>
</head>
<body>
<div class="main">
    <div class="intro">
        <h1>Who are you?</h1>
        <h3>Hi, my name is Pascal.</h3>
        <p>Nice to meet you.</p>
    </div>
    <div class="selfie">
        <img src="test0.jpeg" width="50%">
    </div>
    <div class="btn-wrapper">
        <input type="text" placeholder="What's your name?">
        <button class="btn">
            Nice!
        </button>
    </div>
    <div class="profile">
        <p>Allow me to provide more details about myself <a href="https://github.com/cascalpascal" target="_blank">here.</a></p>
    </div>
    <div class="nicknamelist">
        <p>Here are some of my favorite nicknames. Call me whatever you like!</p>
        <ul>
            <li>Mr.Frog</li>
            <li>Froggy</li>
            <li>Caspal</li>
            <li>Lizardus</li>
        </ul>
    </div>
</div>
</body>
</html>
```

```css
/*style.css*/

.main{
    margin-top: 30px;
}

.intro{
    display: block;
    width: 550px;
    margin-left: auto;
    margin-right: auto;
}

.selfie{
    display: block;
    width: 550px;
    margin-bottom: 10px;
    margin-left: auto;
    margin-right: auto;
}

.btn-wrapper{
    display: block;
    width: 550px;
    margin-left: auto;
    margin-right: auto;
}

.btn{
    color: #0f1419;
    font-weight: bold;
    background-color: white;
    border: 1px solid #0f1419;
    border-radius: 8px;

    padding-top: 2px;
    padding-bottom: 2px;
    padding-left: 6px;
    padding-right: 6px;

}

.profile{
    color: green;
    display: block;
    width: 550px;
    margin-left: auto;
    margin-right: auto;
}

.nicknamelist{
    display: block;
    margin-left: auto;
    margin-right: auto;

    background: palegreen;
    width: 550px;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 10px;
    padding-right: 10px;

    border: 5px solid green;
    border-radius: 20px;
}
```

![[Pasted image 20240402113339.png]](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/Course/Pasted%20image%2020240402113339.png?raw=true)


<br>


---

### Reference

[Scrimba: Build a Google.com clone](https://scrimba.com/playlist/p5aGYHD)