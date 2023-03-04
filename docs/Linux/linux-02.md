---
layout: default
title: 02 GCP SCP 파일 전송
parent: Linux
nav_order: 2
---

# 02 - GCP SCP 파일 전송
구글 클라우드 콘솔에 방문하지 않고 터미널에서 파일 주고받기
<hr>

## 1. 로컬 저장소 -> 원격 저장소

```bash
scp -i ~/.ssh/{PrivateKey} {File} {Username}@{IP}:{Dir}
```
`PrivateKey` : 개인키 파일명  
`File` : 원격 서버로 전송할 파일명  
`Username` : 사용자명  
`IP` : VM 인스턴스의 외부IP  
`Dir` : 전송한 파일이 저장될 디렉토리  
<br>

```bash
scp -i ~/.ssh/{PrivateKey} -r {Folder} {Username}@{IP}:{Dir}
```
폴더를 전송할 땐 위와 같이 `-r` 옵션을 넣어주면 된다.
<hr>

## 2. 원격 저장소 -> 로컬 저장소

```bash
scp -i ~/.ssh/{PrivateKey} {Username}@{IP}:{File} {Dir}
```
`PrivateKey` : 개인키 파일명  
`File` : 원격 서버에서 가져올 파일(경로)  
`Username` : 사용자명  
`IP` : VM 인스턴스의 외부IP  
`Dir` : 받아온 파일이 저장될 디렉토리  
<br>

```bash
scp -i ~/.ssh/{PrivateKey} -r {Username}@{IP}:{Folder} {Dir}
```
폴더를 받아올 땐 위와 같이 `-r` 옵션을 넣어주면 된다.