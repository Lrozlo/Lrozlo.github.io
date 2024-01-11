---
title: "마크다운 문법"
excerpt: "첫 블로그 포스트"

categories:
  - Github
tags:
  - [markdown, blog, github]

permalink: /github/myfirstpost/

toc: true
toc_sticky: true

date: 2023-11-28
last_modified_at: 2023-12-18
---
# 마크다운 문법
## 📒 안녕하세요  
블로그에 글 잘 올라가나 테스트 해보려구요. <br> 줄 바꿈

문단도<br>나누기


  - 들여쓰기 하고 싶으면
  - 스페이스바를 두번 누르면 되네요
    - 스페이스바 네번 눌렀습니다
   - 스페이스바 세번은 두번으로 치네요
     - 스페이스바 다섯번도 네번으로 치네요
       - 스페이스바 일곱번
        - 스페이스바 8


# 헤더1
## 헤더2
### 헤더3
#### 헤더4
##### 헤더5
###### 헤더6
####### 헤더7같은건 없네요

*기울어진 텍스트*
_기울어진_
**강조된 텍스트**
__강조된__
~~취소된 텍스트~~

<u>밑줄 친 텍스트</u>

<span style="color:red">빨간 글씨</span>

## 가장 중요한 코드 블록

    탭 한번으로 코드 블록

<pre>
<code>
이렇게도 코드 입력가능  
</code>
</pre>

```cpp
#include <string>
#include <vector>

string s = "abc";
```

```java
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```

## 인용문
>인용문1
>>인용문2
>>>인용문3

<cite>기울임체로 인용한 출처 남기기</cite>

구분선
***
---

## 링크

<https://ansohxxn.github.io/blog/markdown/>

[Google](https://google.com, "google link")


## 이미지 첨부

![image](/assets/images/포항갈매기사진.jpeg)

![image](/assets/images/감자1.jpeg)

- 아
  * 에
    + 이
    - 오


1. 순서
2. 순서
    1. 순서
    2. 순서
    - 순서
        1. 순서
        2. 순서

- [ ] check
- [X] checkno


