---
layout: default
title: 02 깃(Git) 초기 세팅 (config, clone, push)
parent: GitHub
nav_order: 2
---

# 02 - 깃(Git) 초기 세팅 (config, clone, push)
* [git 계정정보 저장하는 방법](#1-git-계정정보-저장하는-방법)
* [깃허브의 프로젝트 파일을 로컬 저장소로 복사하는 방법](#2-깃허브의-프로젝트-파일을-로컬-저장소로-복사하는-방법)
* [로컬 저장소의 파일을 깃허브로 업로드 하는 방법](#3-로컬-저장소의-파일을-깃허브로-업로드-하는-방법)
    * 로컬에서 작업하는 내용을 깃허브에 업로드하여 커밋 기록을 남기며 작업하고 싶을 때
<hr>

## 1. git 계정정보 저장하는 방법
```bash
git config --global user.name "{UserID}"
git config --global user.email "{UserEmail}"
```
`--global` : 전역 옵션. 프로젝트별로 다른 계정을 사용하려면 해당 옵션을 제거하면 된다.
<br><br>
commit시 계정 정보를 일일이 입력할 필요가 없어진다.
<hr>

## 2. 깃허브의 프로젝트 파일을 로컬 저장소로 복사하는 방법
```bash
git clone {RepoURL} {Dir}
```
`RepoURL` : 로컬 저장소로 복사할 깃허브의 리포지토리 링크.

<img src="../../assets/images/github-02-image-1.png" alt="GetLink" width="90%" height="90%">

`Code` 의 HTTPS 탭에서 리포지토리의 주소를 복사할 수 있다.
<hr>

## 3. 로컬 저장소의 파일을 깃허브로 업로드 하는 방법
<br>

#### 1. git 저장소 초기화
```bash
git init
```
해당 명령어는 Git 저장소를 초기화하여 새로운 Git 저장소를 생성하거나 기존의 디렉토리를 Git 저장소로 변환할 수 있도록 필요한 파일과 디렉토리를 생성하는 명령어이다. <br>
해당 명령어 입력시 현재 디렉토리에 `.git` 폴더가 생성될 것이다.
<br><br>

#### 2. git 저장소로 파일 추가
```bash
git add .
```
`.` : 현재 디렉토리의 모든 파일&폴더
<br><br>

#### 3. git 저장소의 변경사항 기록하기
```bash
git commit -m "{Message}"
```
`-m` : 커밋 메시지를 입력하는 옵션
<br><br>

#### 4. 유저 정보 입력
```bash
git config user.name {GithubID}
git config user.email {GithubEmail}
```
<br><br>
## 임시간단정리
readme.md는 생성하지 않은 상태로 리포지토리 생성