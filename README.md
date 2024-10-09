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
</details>

<details>
  <summary style="font-size:30px; font-weight:bold; font-style:italic;">
    SPA와 Vue Router
  </summary>

  SPA란 하나의 페이지로 구성된 웹사이트를 말한다.  

  Vue는 SPA 구조로 이루어져 있으며, 특정 URL 요청이 들어오면 컴포넌트를 라우트 시킴으로써 페이지를 전환할 수 있는 효과를 줄 수 있다.

  ## VueRouter
  Router 방식은 미리 컴포넌트와 주소를 Router 내부 객체에 매핑시켜둔 뒤, 등록된 주소에 대한 요청이 들어왔을 때 라우터에서 해당 주소와 매핑되는 컴포넌트를 출력하게 된다.
  
  매핑되는 객체 단위를 route라고 부르며 이러한 route 객체를 배열로 구성하는 것이 routes 이다.  
  각 구조는 아래와 같다.  

  - route Object구조
    ```js
    {
      path: '/',
      name: 'home',
      component: Home
    }
    ```
  - routes 구조
    ```js
    [
      {
        path: '/',
        name: 'home',
        component: Home
      },
      {
        path: '/about',
        name: 'about',
        component: About
      }
    ]
    ```

  ## Vue 라우팅 컴포넌트
  이렇게 라우터에 등록된 컴포넌트를 요청이 들어왔을 때 특정 영역에 출력할 수 있게 해주는 태그가 있는데 `<router-view/>` 태그이다.  
  vue에서는 브라우저의 주소창 뿐만 아니라 클리커블 한 네비게이션 영역의 anchor태그 역할을 해주는것이 있으며 `<router-link to="/주소"></router-link>` 이다.

  - router-link/router-view
    ```html
    <template>
      <div id="app">
        <div id="nav">
          <router-link to="/">Home!</router-link>
          <router-link to="/">About!!!</router-link>
        </div>
        <router-view/>
      </div>
    </template>
    ```
</details>