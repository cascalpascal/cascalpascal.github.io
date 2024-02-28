---
layout: post
author: pascal
tags: [tutorial, ubuntu]
---

# Ubuntu 초기 세팅 

## Ubuntu 설치

1. 설치 USB 준비

- 프로그램 사용해서 Ubuntu 22.04 LTS iso 이미지 다운

| OS            | Tool                 |
|:-------------:|:--------------------:|
| Windows       | Rufus                |
| Ubuntu        | Startup Disk Creator |


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
