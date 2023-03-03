---
layout: default
title: 03 SSH 프로세스 유지
parent: Linux
nav_order: 3
---

# 03 - SSH 프로세스 유지
원격으로 접속한 터미널에서 프로세스를 실행하고 접속을 종료할 경우, 해당 프로세스는 종료된다.<br>
접속을 종료해도 프로세스가 유지되는 명령어를 소개한다.
<hr>

## 1. Screen
```bash
ssh-keygen -t rsa -f ~/.ssh/{KeyName} -C {Username}
```

`KeyName` : 생성될 Key의 파일명  
`Username` : VM 인스턴스에서 사용할 사용자명

명령어 입력시 질문이 뜰텐데 엔터로 넘어가면 된다.

SSH 키를 생성했다면, `~/.ssh` 경로에 파일이 2개 생성되었을 것이다.

`KeyName` : 개인키  
`KeyName.pub` : 공개키
<hr>

## SSH 키 등록
사진 첨부
<hr>

## SSH 접속
```bash
ssh -i ~/.ssh/{PrivateKey} {Username}@{IP}
```

`PrivateKey` : 개인키 파일명  
`Username` : 키 생성할 때 입력한 사용자명  
`IP` : GCP VM 인스턴스의 외부IP

