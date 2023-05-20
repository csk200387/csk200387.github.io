---
layout: default
title: 05 한 줄에 여러 명령어 실행하기
parent: Linux
nav_order: 5
---

# 한 줄에 여러 명령어 실행하기

### 리눅스에서는 일반적으로 아래와 같이 한 줄에 여러 명령어를 실행할 수 있다.

```bash
command1; command2; command3
```

### 세미콜론 외에도 다음과 같은 구분자를 사용할 수 있다.

<br>

`;` : 명령어를 구분하는 구분자. 앞의 명령어가 성공하든 실패하든 뒤의 명령어를 실행

```bash
ls -al; pwd; date
```

<br>

`&&` : 앞의 명령어가 성공했을 때만 뒤의 명령어를 실행

```bash
ls -al && pwd && date
```

<br>

`||` : 앞의 명령어가 실패했을 때만 뒤의 명령어를 실행

```bash
ls -al || pwd || date
```

<br>

`&` : 명령어를 백그라운드에서 실행

```bash
ls -al & pwd & date
```

<br>

`()` : 명령어를 그룹화

```bash
(ls -al; pwd; date)
```

<br>

`|` : 명령어의 출력을 다른 명령어의 입력으로 사용

```bash
ls -al | grep README.md
```

<br>

`|&` : 명령어의 출력과 에러를 다른 명령어의 입력으로 사용

```bash
ls -al |& grep README.md
```

## 사용 예시
기존에 `;`를 사용하여 c 컴파일과 실행을 한 줄에 실행하였다.
    
```bash
alias comp='gcc main.c -o Main -O2 -Wall -lm -static -std=gnu99; ./Main'
```
이 경우, `gcc` 명령어가 성공하든 실패하든 뒤의 `./Main` 명령어를 실행하였다.

하지만, `&&`를 사용하면 `gcc` 명령어가 성공했을 때만 `./Main` 명령어를 실행하도록 할 수 있다.

```bash
alias comp='gcc main.c -o Main -O2 -Wall -lm -static -std=gnu99 && ./Main'
```
그러나 차이를 모르겠다. `-Wall`옵션으로 에러내역이 출력되어도 컴파일은 제대로 수행되므로 Main의 실행은 정상으로  작동한다.

<hr>
위 내용은 github copilot의 도움을 받아 작성됨.