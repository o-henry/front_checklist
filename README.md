# front_checklist


- [ ] **CRA** or **Webpack** or **Next.js**
```
  ├─ 비용 고려 
  ├─ 확장성 / 시간
  ├─ Hook or Class
  └─ useCallback 필요 여부 체크
  
  CRA with TS
  └─ `npx create-react-app my-app --template typescript`
```
- [ ] **Basic**
```
  ├─ TS / JS
  │  └─ tsconfig / absolute import ( add baseUrl to tsconfig.json )
  ├─ Flux 
  │  └─ redux or mobx   
  ├─ prettier
  ├─ design pattern
  │  └─ atomic or container
  │     └─ divide business logic and GUI    
  └─ eslint
     └─ eslint-plugin-jsx-a11y : JSX내의 접근성 문제에 대한 즉각적 린팅 피드백 제공
     └─ https://brouk-devlog.netlify.app/react/create-react-app-with-typescript,-eslint,-prettier/
```
- [ ] **CSS & Library**
```
  직접 구현할 것인가 / 비용 고려하여 선택
  
  ├─ node-sass or style-component
  ├─ CSS Framework or Pure css or None
  │  └── Material or SPECTRE → 요소: 범용성 / 많은 관련 문서 / 가벼움(사이즈) / 구현 가능 여부
  │    └── bulma / spectre가 더 가볍긴 한데 bulma가 더 문서가 많고 별 차이 없다. with node-sass
  ├─ naming convention 
  └─ responsive 
     └─ media query / grid / flex  
```
- [ ] **설계**
```
  ├─ https://medium.com/@Charles_Stover/optimal-file-structure-for-react-applications-f3e35ad0a145
  ├─ https://medium.com/hackernoon/the-100-correct-way-to-structure-a-react-app-or-why-theres-no-such-thing-3ede534ef1ed
  ├─ 해당 컴포넌트가 전역으로 사용되는가
  └─ 데이터 유지가 필요한가
     └─ redux or Mobx or useReducer
```
- [ ] **Cross Browsing**
```
  ├─ normalize.css or reset.css 
  │  └── https://webdir.tistory.com/455
  └─ webkit .. mozila
```

- [ ] **웹 표준/접근성**
```
  눈으로 보거나 들을 수 있는 모든 정보의 대체 표현 수단을 제공하고 UX의 제한을 두지 마라. 
  
  ├─ img 태그의 alt
  ├─ 사용자에게 오류 안내 / alert, css 명확한 대비
  ├─ 포커스 컨트롤
  │  └─ ref
  ├─ skip 기능
  ├─ 올바른 문서 제목
  ├─ 저시력 사용자를 위한 충분한 색 대비
  ├─ 마우스 혹은 포인터 이벤트로 노출된 모든 기능을 키보드만으로 사용할 수 있도록 보장해야 한다.
  └─ 자동 으로 움직이는 컨텐츠 의 사용자 제어 기능 
  
  ** JS가 동작하지 않는 환경이라면?
 
```
- [ ] **구현**
```
  ├─ handle loader / skeleton UI or loading indicator 
  └─ event bubbling and event capture
  
```

- [ ] **SEO**
```
  검색 엔진의 크롤러 대비
  
  ├─ next.js or helmet
  │             └─ meta tag 동적 제어를 위한 사용
  ├─ semantic web (https://poiemaweb.com/html5-semantic-web)
  │  ├─ [x] : div, span
  │  └─ [o] : table, form, img, header, nav, aside, section, article, footer
  └─ react → Fragment
     └─ <input id="blahblah" type="text" name="name" />
     
```

- [ ] **Test**
```
  ├─ JEST
  └─ e2e TEST 
     └─ puppeteer
```

- [ ] **git**
``` 
  ├─ commit convention
  └─ git flow or github flow ..
```

- [ ] **문서화**
```
  └─ storybook
     └─ 비용  
```

- [ ] **CRA with Lint**
```
CRA로 생성한 프로젝트에 eslint를 입히게 되면 에러가 발생한다. ( 기존 설치된 버전과, manual하게 설치한 버전의 충돌이 일어난다. )

해결

$ yarn add -D eslint eslint-config-airbnb eslint-config-airbnb-typescript eslint-config-prettier eslint-config-react-app eslint-import-resolver-typescript eslint-loader eslint-plugin-flowtype eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks  @typescript-eslint/parser @typescript-eslint/eslint-plugin prettier prettier-eslint prettier-eslint-cli eslint-plugin-prettier

.eslintrc
{
  "plugins": ["prettier", "@typescript-eslint"],
  "extends": ["airbnb-typescript", "react-app", "prettier"],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "project": "./tsconfig.json"
  },
  "rules": {
    "import/no-cycle": 0
  }
}

.eslintignore
build/*
public/*
src/react-app-env.d.ts
src/serviceWorker.ts
node_modules/

$ package.json
scripts: {
    "lint": "eslint --ext .js,.jsx,.ts,.tsx src/",
    "lint:fix": "eslint --ext .js,.jsx,.ts,.tsx src/ --fix"
}

위 설정에서 새로운 라이브러리를 설치하면 린트 에러가 발생한다. ( 노드 모듈과 패키지를 삭제 후 재설치 하라는 에러 설명이 나오거나, 해당 lint config를 찾지 못했다는 에러 등 )
CRA로 설치할 경우 기본적으로 eslint를 설치하는데, 위와 같이 설치할경우 manual 하게 eslint를 설치하면서 충돌이 난다.

이를 해결하기 위해 manual 하게 설치한 eslint를 package.json에서 제거후 재설치 하면 해결된다. ( 임시 방편 )

그냥 webpack 쓸때 쓰면 맘 편하다.
```

- [ ] **Custom Hook**
```
  └─ https://usehooks-typescript.com/use-fetch/
```




---

<sup>1</sup> [웹 접근성](https://ko.reactjs.org/docs/accessibility.html)

<sup>2</sup> [Lint](https://medium.com/@brygrill/create-react-app-with-typescript-eslint-prettier-and-github-actions-f3ce6a571c97)
