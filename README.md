# Vue 2 기초 (CLI)

<details>
  <summary style="font-size:30px; font-weight:bold; font-style:italic;">
    Vue CLI 란?
  </summary>

  CLI란? Command Line Interface에 대한 약자이다.  
  터미널에서 명령어를 통해 Vue를 설치하거나 Vue와 관련된 package를 추가할 때 명령어로 간단하게 실행할 수 있게 도와주는 도구이다.   
</details>

<details>
<summary style="font-size:30px; font-weight:bold; font-style:italic;">Vue CLI Install</summary>
<br>

- ### vue/cli 설치

  ```bash
  npm install -g @vue/cli
  ```

- ### vue-cli 설치 확인

  ```bash
  vue --version
  ```
- ### vue project 생성

  ```bash
  vue create {프로젝트명}
  ```

- ### 개발 환경 구축 옵션 선택
  선택을 통해 개발환경을 구축할 수 있다
  ```text/plain
  Vue CLI v5.0.8
  ? Please pick a preset: (Use arrow keys)
    Default ([Vue 3] babel, eslint)
    Default ([Vue 2] babel, eslint)
  > Manually select features
  ```

- ### 기본적으로 사용할 라이브러리 선택 (Babel, Router, Vuex)  
  Select는 `Space`-Key Next는 `Enter`-Key  
  (Ctrl + A는 전체선택이다.)  

  ```text/plain
  Vue CLI v5.0.8
  ? Please pick a preset: Manually select features
  ? Check the features needed for your project: (Press <space> to select, <a> to toggle all, <i> to invert selection, and
  <enter> to proceed)
  (*) Babel
  ( ) TypeScript
  ( ) Progressive Web App (PWA) Support
  (*) Router
  (*) Vuex
  ( ) CSS Pre-processors
  (*) Linter / Formatter
  ( ) Unit Testing
  ( ) E2E Testing
  ```

- ### Vue version 2.x 선택
  ```text/plain
  Vue CLI v5.0.8
  ? Please pick a preset: Manually select features
  ? Check the features needed for your project: Babel, Router, Vuex
  ? Choose a version of Vue.js that you want to start the project with (Use arrow keys)
    3.x
  > 2.x
  ```

- ### 라우터 History 모드 사용 여부 - Yes(Y)

  ```text/plain
  Vue CLI v5.0.8
  ? Please pick a preset: Manually select features
  ? Check the features needed for your project: Babel, Router, Vuex
  ? Choose a version of Vue.js that you want to start the project with 2.x
  ? Use history mode for router? (Requires proper server setup for index fallback in production) (Y/n)
  ```

- ### ESLint with error prevention only 선택

  ```text/plain
  ? Pick a linter / formatter config: (Use arrow keys)
  > ESLint with error prevention only
    ESLint + Airbnb config
    ESLint + Standard config
    ESLint + Prettier
  ```

- ### Lint on save 선택

  ```text/plain
  ? Pick additional lint features: (Press <space> to select, <a> to toggle all, <i> to invert selection, and <enter> toproceed)
  > (*) Lint on save
    ( ) Lint and fix on commit
  ```

- ### 개발 환경 관리 파일 - package.json으로 선택
  ```text/plain
  Vue CLI v5.0.8
  ? Please pick a preset: Manually select features
  ? Check the features needed for your project: Babel, Router, Vuex
  ? Choose a version of Vue.js that you want to start the project with 2.x
  ? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
  ? Where do you prefer placing config for Babel, ESLint, etc.?
    In dedicated config files
  > In package.json
  ```

- ### 현재 선택한 개발 환경을 저장할 것인지 여부- No(n)
  ```text/plain
  Vue CLI v5.0.8
  ? Please pick a preset: Manually select features
  ? Check the features needed for your project: Babel, Router, Vuex
  ? Choose a version of Vue.js that you want to start the project with 2.x
  ? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
  ? Where do you prefer placing config for Babel, ESLint, etc.? In package.json
  ? Save this as a preset for future projects? (y/N)
  ```


- ## npx를 통한 설치
  cli를 사용하지 않고 설치하는 방식이다.
  ```bash
  npx @vue/cli crate 프로젝트명
  ```

<details>
  <summary style="font-size:30px; font-weight:bold; font-style:italic;">
    목차 접은글 기본 템플릿
  </summary>

</details>