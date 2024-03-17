---
layout: post
author: pascal
tags: [tutorial, ubuntu]
---

# Ubuntu 초기 세팅 

## Ubuntu 설치

1. 설치 USB 준비
- 프로그램 사용해서 Ubuntu 22.04 LTS iso 이미지 다운

|OS|Tool|
|---|---|
|Windows|Rufus|
|Ubuntu|Startup Disk Creator|

2. Ubuntu 설치
- 바이오스 진입(msi: del 연타) 후 준비한 USB를 부팅 1순위로 변경
- Try or install Ubuntu 선택
- 설치 형식 -> 기타
- Partition 설정
  - swap: RAM의 2배 크기
  - EFI: 512MB. 부팅에 사용
  - root: ext4로 설정. 남은 공간 모두 할당.(/home 따로 안나눠도됨)
- 한국어 설정
- Region & Language -> Language: '한국어'로 변경
- 재시동
- 키보드 -> 입력 소스: '한국어(Hangul)' 추가
- Ubuntu 상단 bar 우측에서 'ko'를 '한국어'로 변경
- 키보드 바로 가기 -> 바로 가기 보기 및 사용자 설정-> 입력 중-> '사용 않음'으로 변경
- 다시 시작

## Basic Setup

- mirror 서버를 kakao로 변경
- Compiler
  - gcc
  - clang, clangd
- Build system
  - CMake
- CI/CD
  - Git 설치 + 구성
```
$ git config --global user.name "your_username_example"
$ git config --global user.email "your_useremail_example"
```
  - GitHub
- vim, vim-gtk3
- zsh, oh-my-zsh
- tmux
- VS Code
- docker, docker-desktop
- pyenv
- goenv
- nvm

## Git-GitHub Repository 연동

### Generate a new SSH key and add it to the ssh-agent

- Generate a new SSH key
```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
- Start the ssh-agent
```
$ eval "$(ssh-agent -s)"
```
- Add your SSH private key to the ssh-agent
```
$ ssh-add ~/.ssh/id_rsa
```
- Copy your SSH public key
```
$ cat ~/.ssh/id_rsa.pub
```
- Add your SSH public key to the GitHub account

### Git과 GitHub Repository 연동

- 현재 디렉토리에서 Git 저장소 초기화
```
$ git init
```
- Github에서 Repository 생성
- Git과 GitHub 원격 저장소를 연결
```
$ git remote add origin <Repository URL>
```
- 작업 후 push
```
$ git add test.txt
$ git commit -sm "Test commit"
$ git push -u origin main
```
### GitHub 명령어
- stage 할 파일 추가
```
$ git add .
```
- 다음 commit에 포함될 staged된 파일과 staged되지 않은 파일 확인
```
$ git status
```
- commit된 파일과 현재 상태 비교
```
$ git diff
```
- 히스토리 이름 지어주기
```
$ git commit -m "history_name_example"
```
- GitHub repository와 내 local project와 연결
```
$ git remote add origin repository_URL_example
```
- 잘 되었는지 확인
```
$ git remote -v
```
- GitHub로 올리기
```
$ git push origin master
```
  
### Install GitHub desktop on Ubuntu
```
$ wget -qO - https://apt.packages.shiftkey.dev/gpg.key | gpg --dearmor | sudo tee /usr/share/keyrings/shiftkey-packages.gpg > /dev/null
$ sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/shiftkey-packages.gpg] https://apt.packages.shiftkey.dev/ubuntu/ any main" > /etc/apt/sources.list.d/shiftkey-packages.list'
$ sudo apt update && sudo apt install github-desktop
```
