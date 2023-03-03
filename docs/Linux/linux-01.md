---
layout: default
title: 01 GCP SSH 연결
parent: Linux
nav_order: 1
---

# 01 - GCP SSH 연결
로컬 터미널에서 GCP VM 인스턴스 터미널 접속하기
<hr>

## SSH 키 생성
```bash
ssh-keygen -t rsa -f ~/.ssh/{KeyName} -C {Username}
```

`KeyName` : 생성될 Key의 파일명.  
`Username` : VM 인스턴스에서 사용할 사용자명. 클라우드 콘솔에서 접속한 ssh의 사용자명과 통일하는 것을 추천.

명령어 입력시 질문이 뜰텐데 엔터로 넘어가면 된다.

SSH 키를 생성했다면, `~/.ssh` 경로에 파일이 2개 생성되었을 것이다.

`KeyName` : 개인키  
`KeyName.pub` : 공개키
<hr>

## SSH 키 등록
설정 → 메타데이터 → SSH키 → 수정  
`KeyName.pub` 의 내용을 입력한다.  

<img src="../../assets/images/linux-03-image-1.png" alt="Capture" width="90%" height="90%">

<hr>

## SSH 접속

```bash
ssh -i ~/.ssh/{PrivateKey} {Username}@{IP}
```

`PrivateKey` : 개인키 파일명  
`Username` : 키 생성할 때 입력한 사용자명  
`IP` : GCP VM 인스턴스의 외부IP

<hr>

## 기타
`alias` 로 단축 명령어를 생성하여 사용할 수 있다.

```bash
alias sshconnect='ssh -i ~/.ssh/{PrivateKey} {Username}@{IP}'
```
[alias 란?](linux-04.md)

<br>

```bash
ssh-keygen -t rsa -f ~/.ssh/{KeyName} -C {Username}@{IP}
```
원래 위의 방법처럼 `Username` 뒤에 `IP` 를 붙여 키를 등록하였지만, 한 프로젝트에 여러개의 VM 인스턴스가 있을 경우 `Username` 만 기입하고 접속시 외부 IP만 다르게 입력하면 정상적으로 접속이 가능한 것을 확인하였다. 보안적인 측면에선 인스턴스마다 다른 키를 발급받는 것도 좋아보인다.