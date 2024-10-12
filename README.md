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
<details>
  <summary style="font-size:30px; font-weight:bold; font-style:italic;">
    CLI 기반 컴포넌트
  </summary>

  CLI 기반 Vue 프로젝트에서 컴포넌트는 .js 확장자가 아닌 .vue 확장자 파일로 작성한다.
  기본 구조는 아래와 같다

  - .vue 확장자 컴포넌트
    ```html
    <template>
      <ExComponent/>
    </template>
    <script>
    import ExComponent from '@/components/ExComponent.vue'
    export default {
      components: {
        ExComponent
      },
      data() {
        return {}
      },
      methods: {
        updateName() {
          this.name = 'YooHyeok School Updated'
        }
      }
      
    }
    </script>
    <style scoped>

    </style>
    ```
  
    `<style></style>` 태그에 scoped 속성을 적용하면, 해당 컴포넌트 내에서만 style이 적용된다.  
    컴포넌트 간 참조는 script> 영역에서 import 문을 사용한 뒤 components 속성에 객체로 등록해서 사용한다.  
    CDN 방식과 같으며, 하나 차이점은 ` template:`` ` 속성에 작성하던 html 표현식을 `<template></template>` 태그 안에 선언한다.  
    이때 주의할 점은 다중 태그를 하나의 최상위 태그로 묶어야만 한다.

    ```html
    <template>
      <div>div1</div>
      <div>div2</div>
    </template>
    ```
    위와 같이 작성하면 오류가 발생한다.
    ```html
    <template>
      <div>
        <div>div1</div>
        <div>div2</div>
      </div>
    </template>
    ```
    위와 같이 작성 최 상위 단일 태그로 묶어야만 한다.
</details>

<details>
  <summary style="font-size:30px; font-weight:bold; font-style:italic;">
    Props
  </summary>

  부모 컴포넌트에서 자식 컴포넌트로 데이터(state 혹은 value)를 전달할때 사용한다.  
  `v-bind:props명="props 혹은 value"` 혹은 축약형인   
  `:props명="props 혹은 value"` 를 사용하여 보낼 수 있다.  

  자식 컴포넌트에서는 props 속성을 통해 컴포넌트 내에서 재정의한 후 사용할 수 있다.  
  Array와 Object 두가지 타입으로 정의할 수 있으며, Object의 경우 propType을 지원한다.

  - 예시 코드  
      ```js
      export default {
        props: ['title']
      }
      ```

  - ## Props 정의와 PropType

    - **type**  
      넘겨 받은 prop의 타입을 지정한다. (String, Number Object Array 등)  
      타입스크립트를 사용한다면 사용자 정의 타입을 지정할 수 있다.  
      만약 String으로 지정한 후 Number 타입의 값 5를 넘긴다면  
      `Invalid prop: type check failed for prop "title". Expected String with value "5", got Number with value 5.`  
      Vue warn이 콘솔에 출력된다.

    - **required**  
      필수 여부를 지정한다.  
      만약 true로 지정한 후 값을 넘기지 않는다면  
      `Missing required prop: "prop명"`  
      Vue warn이 콘솔에 출력된다.

    - **default**  
      기본값을 지정한다.  
      부모 컴포넌트에서 prop 값을 적용하지 않았을 경우 해당 값이 기본 값으로 적용된다.

    - 예시 코드  
      ```js
      export default {
        props: {
          title: {
            type: String,
            required: true,
            default: "default title"
          }
        },
      }
      ```

  - 부모컴포넌트
    ```html
    <template>
      <자식컴포넌트 v-bind="props"/>
    </template>
    <script>
    import 자식컴포넌트 from '@/components/YooHyeokSchool.vue'
    export default {
      components: { 자식컴포넌트 },
      data() {
        return {
          name: 'YooHyeok School',
          props: {
            title: '타이틀'
          }
        }
      },
    }
    </script>
    ```
  - 자식컴포넌트
    ```html
    <template>
      <h1>{{ title }}</h1>
    </template>
    <script>
    export default {
       props: {
        title: {
          type: String,
          required: true,
          default: "default title"
        }
      },
    }
    </script>
    ```
  
    주의할 점으로는 primitive 타입의 props는 값을 직접 수정할 수 없다.
    그러나 Object 타입의 props는 해당 Object의 property 값을 직접 접근하여 수정할 수 있다.
    `[Vue Warn]: Avoid mutating a prop directlry since the value will be overwritten whenever the parent component re-renders. Instead, use a data or computed property based on the prop's value. Prop being mutatedL "props명"`
    또한 해당 컴포넌트의 state 즉, data property에 동일한 이름이 존재할 수 없다.
    `[Vue Warn]: The data property "props명" is already declared as a prop. Use prop default value instead`
</details>
<details>
  <summary style="font-size:30px; font-weight:bold; font-style:italic;">
    접은글 템플릿
  </summary>

  내용

  ## 주제
  내용

  - 예시코드
    ```js
    ```
  - 예시코드
    ```html
    ```
  
</details>