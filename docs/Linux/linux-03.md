---
layout: default
title: 03 SSH 프로세스 유지
parent: Linux
nav_order: 3
---

# 03 - SSH 프로세스 유지
SSH 접속을 종료하여도 리눅스 시스템의 프로세스를 유지하는 명령어
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

<img src="/assets/images/linux-03-image-1.png" alt="Capture" width="50%" height="50%">

## SSH 키 등록
프로젝트 페이지 → 설정 → 메타데이터 → SSH키


<hr>

## SSH 접속
```bash
ssh -i ~/.ssh/{PrivateKey} {Username}@{IP}
```

`PrivateKey` : 개인키 파일명  
`Username` : 키 생성할 때 입력한 사용자명  
`IP` : GCP VM 인스턴스의 외부IP

