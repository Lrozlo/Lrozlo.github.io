---
title: "Github Blog 폰트 바꾸기"
excerpt: "jekyll minimal mistake 테마 기준"

categories:
  - Github
tags:
  - [github, blog]

permalink: /github/github1/

toc: true
toc_sticky: true

date: 2023-12-18
last_modified_at: 2023-12-18
---
## Github 블로그 폰트 변경 방법

### 1. 원하는 폰트 찾기 
  [구글 폰트 사이트](https://fonts.google.com/?sort=popularity&subset=korean&noto.script=Kore) 에서 한글이 지원되는 원하는 폰트를 찾는다. 본인은 'Noto Serif KR'을 선택하였다.

### 2. 웹 폰트 코드 복붙
  @import를 이용하여 main.scss에 붙여넣는다.<br>
  파일 경로 : assets > css > main.scss

  ```scss
  @import url('https://fonts.googleapis.com/css2?family=Noto+Serif+KR&display=swap');
  ```

### 3. 폰트 이름 추가
  새로운 폰트 이름 '**Noto Serif KR**' 을 $sans-serif, $menufont **맨 앞**에 추가한다.<br>
  파일 경로 : _sass > minimal-mistakes > _variables.scss 
  
  ```scss
  /* system typefaces */
  $serif: Georgia, Times, serif !default;
  /* font change */
  $sans-serif: 'Noto Serif KR', -apple-system, BlinkMacSystemFont, 'Apple SD Gothic Neo', "Montserrat", "Pretendard", "Merriweather", sans-serif !default;
  $monospace: "Fira Mono", "Pretendard", Monaco, Consolas, "Lucida Console", monospace !default;
  
  /* sans serif typefaces */
  $sans-serif-narrow: $sans-serif !default;
  $helvetica: Helvetica, "Helvetica Neue", Arial, sans-serif !default;
  $menufont: "Noto Serif KR", -apple-system, BlinkMacSystemFont, 'Apple SD Gothic Neo', "Montserrat", "BioRhyme", "Pretendard", sans-serif !default;
  ```

  
  
