---
layout: post
author: Cascal Pascal
tags:
  - language
  - rust
  - TRPL
---

>**Course**
>
>[[DevRoad] Rust Developer: The Rust Programming Language](https://cascalpascal.github.io/devroad-rust-developer)

>**Bookmarks**
>
>- [Installing rustup](#installing-rustup-on-linux-or-macos)
>
>- [Hello World!](#hello-world!)
>
>- [Anatomy of a Rust program](#anatomy-of-a-rust-program)
>
>- [Cargo를 사용하여 프로젝트 생성하기](#cargo를-사용하여-프로젝트-생성하기)


---


# Installing rustup on Linux or macOS

```
# rust 설치
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh

Rust is installed now. Great!

# Rust가 컴파일된 출력을 하나의 파일로 합치는 데 사용하는 linker 설치
# 일반적으로 linker가 포함된 c 컴파일러 설치
$ sudo apt update
$ sudo apt install build-essential

# 환경 변수 설정
$ sudo gedit ~/.zshrc

# 파일에 path 추가
export PATH="$HOME/.cargo/bin:$PATH"

# .zshrc 업데이트
$ source ~/.zshrc

# 잘 적용되었는지 확인
$ echo $PATH

# Rust 설치 확인
$ rustc --version
```

# Hello World!

## Create a project directory

```
$ mkdir ~/projects 
$ cd ~/projects 
$ mkdir hello_world 
$ cd hello_world
```

## Writing and running a Rust program

- Filename: main.rs

```
fn main() {
    println!("Hello, world!");
}
```

- main.rs 저장하고 터미널에 다음 명령어 입력

```
# 컴파일
$ rustc main.rs

# 실행파일이 생성되었는지 확인
# ls

# 실행
$ ./main
Hello, world!
```


# Anatomy of a Rust program

```
fn main() {

}
```

위 라인은 러스트의 function을 정의한다. main이라는 특별한 함수는 모든 실행가능한 러스트 프로그램 내에서 첫번째로 실행되는 코드이다. 첫 번째 라인은 parameter가 없고 아무것도 반환하지 않는 main이라는 이름의 함수를 정의한다. 만일 parameter가 있었다면, parameter들이 ()괄호 기호 안에 위치했을 것이다.
함수의 본체가 중괄호 기호 {}로 감싸져 있다. 러스트는 모든 함수 본체들에 이 기호가 필요하다.
*rustfmt는 자동 포맷팅 도구이다. 만일 여러분이 러스트 프로젝트에 표준 스타일을 고수하길 원한다면, rustfmt가 코드를 특정한 스타일로 포매팅해줄 수 있다.*

main 함수 내부(body)에는 다음과 같은 코드가 있다. 작성한 프로그램은 '스크린에 텍스트를 출력' 역할을 한다. 

```
    println!("Hello, world!");
```

첫째, 러스트 스타일은 탭이 아닌 네 개의 스페이스로 들여쓰기를 한다. 둘째, ```println!```는 러스트 **매크로(macro)** 이다. ```!``` 이 보통의 함수 대신 매크로를 호출하고 있음을 의미한다. ```!``` 없이 ```println```으로 입력되었다면 함수였을 것이다. 셋째, ```"Hello, world!"```는 string이다. 우리는 이 string을 ```println!```의 인자로 넘기고, 이를 화면에 출력한다. 넷째, 라인을 끝낼 때는 세미콜론 ```;```을 작성하는데, 이는 이 표현식이 끝났고 다음 것이 시작될 준비가 되었음을 나타낸다.



## Hello, Cargo!

Cargo는 러스트의 시스템 및 패키지 매니저이다. Cargo는 코드를 빌드하고, 코드가 의존하고 있는 라이브러리를 다운로드해주고, 그 라이브러리들을 빌드하는 등 많은 작업을 다룬다.

```
# Cargo가 설치되어 있는지 확인
$ cargo --version
```



# Cargo를 사용하여 프로젝트 생성하기

```
# 이전에 생성했던 프로젝트 디렉토리로 이동하여 다음 실행
$ cargo new hello_cargo --bin
```

첫 커맨드는 *hello_cargo*라고 명명된 새로운 디렉토리와 프로젝트를 생성한다. 그리고 Cargo는 디렉토리에 이 프로젝트의 파일들을 생성한다. ```cargo new``` 에게 넘겨지는 ```--bin``` 인자로 라이브러리가 아닌 실행 가능한 어플리케이션으로 만들었다.

```
# 생성된 hello_cargo 디렉토리로 가서 파일 리스트 보기
$ cd hello_cargo
$ ls
Cargo.toml  src
```

*hello_cargo* 디렉토리로 가서 파일 리스트를 보면 Cargo가 우리를 위해 *Cargo.toml* 파일과 안에 *main.rs*를 담고 있는 *src* 디렉토리를 생성한 것을 볼 수 있다. 그리고 *.gitignore*와 함게 새로운 Git 저장소도 초기화되어 있다.

*Cargo.toml*을 텍스트 에디터로 열어보자.

```
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2021"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```

이 파일은 Cargo의 환경설정 포맷을 나타내고 있으며, TOML(Tom's Obvious, Minimal Language) 포맷으로 작성되었다.

첫 라인 ```[package]``` 는 패키지 환경설정 섹션의 시작지점이다. 우리는 이 파일에 더 많은 정보를 추가하기 위해, 다른 섹션들을 추가할 것이다. 그 다음 세 라인들은 Cargo가 당신의 프로그램을 컴파일하기 위해 필요로 하는 정보에 대한 설정을 합니다.: 이름, 버전, 에디션이다. Cargo는 당신의 환경으로부터 당신의 이름과 이메일 정보를 얻어내므로, 만일 정보가 정확하지 않다면, 지금 수정하고 파일을 저장해야 한다. ```[dependencies]``` 는 당신의 프로젝트의 의존성들의 리스트를 적을 수 있는 섹션의 시작점이다. 러스트에서는 코드의 패키지를 **크레이트(crate)** 라고 부른다. 여러 개의 크레이트들로 구성된 복잡한 프로젝트와 함께라면 그냥```rustc```를 이용하는 것보다 Cargo를 사용하는 것이 빌드를 조직화하도록 하는 것이 훨씬 쉽다. 

*src/main.rs*를 텍스트 에디터로 열어보자.

```
fn main() {
    println!("Hello, world!");
}
```

Cargo는 우리가 이전에 hello_world 디렉토리에 작성했던 것과 똑같이 "Hello, world!" 프로그램을 작성했다. 우리의 이전 프로젝트와 CArgo가 만든 프로젝트 간의 차이점은 Cargo가 코드를 src 디렉토리 안에 위치시킨다는 점, 최상위 디렉토리에 Cargo.toml 환경 파일을 가진다는 점이다.

Cargo는 여러분의 소스 파일들이 src 디렉토리 안에 있을 것으로 예상한다. 최상위 프로젝트는 디렉토리는 그저 README 파일들, 라이센스 정보, 환경 파일들, 그리고 여러분의 코드와는 관련이 없는 다른 것들 뿐이다. Cargo를 이용하는 것은 여러분이 프로젝트를 조직화하는 데에 도움을 준다. 
> There’s a place for everything, and everything is in its place.

만일 당신이 Hello, world! 프로젝트에서 했던 것처럼 Cargo를 사용하지 않은 프로젝트를 시작했다면, Cargo를 사용한 프로젝트로 이를 바꿀 수 있다. 



## Cargo 프로젝트를 빌드하고 실행하기

이제 Cargo로 만든 "Hello, world!" 프로젝트를 빌드하고 실행할 때의 차이점을 살펴보자.

```
# hello_cargo 디렉토리에서 프로젝트를 빌드한다.
$ cargo build
   Compiling hello_cargo v0.1.0 (/home/pascal/profile/Golden/Course/Rust/The Rust Programming Language(2nd edit)/projects/hello_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.13s
```

이 커맨드는 당신의 현재 디렉토리 대신 *target/debug/hello_cargo*에 실행 파일을 생성한다. 

```
# 생성한 실행 파일 실행
$ ./target/debug/hello_cargo
Hello, world!
```

처음으로 cargo build를 실행하면 Cargo가 최상위 디렉토리에 *Cargo.lock*이라는 새로운 파일을 생성한다. 이 프로젝트는 어떠한 의존성도 가지고 있지 않으므로, 파일의 내용이 얼마 없다. 우리가 이 파일을 손수 변경할 필요는 없다, Cargo가 우리를 위해 이 파일의 내용을 관리한다.

```
# 한번의 커맨드로 코드를 컴파일하고 결과 실행파일을 실행 수 있다.
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.00s
     Running `target/debug/hello_cargo`
Hello, world!
```

```cargo check```는 코드가 컴파일 되는지 빠르게 확인해주지만 실행파일을 생성하지는 않는다.

```
$ cargo check
    Checking hello_cargo v0.1.0 
    Finished dev [unoptimized + debuginfo] target(s) in 0.02s
```

실행파일을 생성하는 단계를 생략하기 때문에 ```cargo check```가 ```cargo build```에 비해 훨씬 빠르다. 만일 지속적으로 작업물을 검사한다면 ```cargo check```를 이용하여 검사 과정을 빠르게 마무리할 수 있다. 이후 실행 파일을 사용할 준비가 되었을 때 ```cargo build```를 실행한다.



## 릴리즈 빌드

```
$ cargo build --release
```

당신의 프로젝트가 릴리즈를 위한 준비를 마쳤다면, 위의 커맨드를 사용하여 최적화와 함께 이를 컴파일할 수 있다. 이 커맨드는 *target/debug* 대신 *target/release*에 실행파일을 생성할 것이다. 최적화는 당신의 러스트 코드를 더 빠르게 만들어주지만, 최적화를 켜는 것은 당신의 프로그램을 컴파일하는데 드는 시간을 길게 할 것이다: 이것이 바로 두 개의 서로 다른 프로파일이 있는 이유이다. 하나는 당신이 빠르게, 자주 다시 빌드하기 위한 개발용, 그리고 다른 하나는 반복적으로 다시 빌드를 할 필요 없이 가능한 빠르게 실행되어 당신이 사용자들에게 제공할 최종 프로그램을 빌드하기 위한 용도이다. 만약 당신이 코드의 실행 시간을 벤치마킹 중이라면, ```cargo build --release```를 실행하고 *target/release*의 실행파일을 가지고 벤치마킹하고 있음을 상기해야 한다.


---
## Reference
[https://doc.rust-lang.org/book/ch01-00-getting-started.html](https://doc.rust-lang.org/book/ch01-00-getting-started.html)
[https://rinthel.github.io/rust-lang-book-ko/ch01-00-getting-started.html](https://rinthel.github.io/rust-lang-book-ko/ch01-00-getting-started.html)
