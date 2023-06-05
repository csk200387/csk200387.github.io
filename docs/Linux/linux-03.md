---
layout: default
title: 03 Screen (백)
parent: Linux
nav_order: 3
---

# 03 - SSH 프로세스 유지 (Screen)
SSH 접속을 종료하여도 리눅스 시스템의 프로세스를 유지하는 명령어
<hr>

<!-- ## 1. Screen -->

### Screen 설치

```bash
sudo apt update
sudo apt install screen
```
위와 같이 설치할 수 있다.

### Screen 사용법

```bash
screen
```
위와 같이 입력 후 `Enter`를 누르면 새로운 세션이 생성된다.
<hr>

```bash
screen -S {session_name}
```
`-S` 옵션을 사용하여 세션 이름을 지정할 수 있다.

<br>  


```bash
screen -r {session_name}
```
`-r` 옵션으로 해당 세션에 접속할 수 있다.

<br>

```bash
screen -ls
```
`-ls` 옵션으로 현재 생성된 세션 목록을 확인할 수 있다.

<br>

```bash
screen -X -S {session_name} quit
```
기본적으로 세션은 `Ctrl + D`를 눌러 종료할 수 있으나 위와 같이 명령어를 사용하여 종료할 수도 있다.

<br>

```bash
screen -X -S {session_name} stuff {command}
```
`-X` 옵션으로 해당 세션에 명령어를 전달할 수 있다.  
쉘스크립트를 사용할 때 유용하게 사용할 수 있다.

<br>
