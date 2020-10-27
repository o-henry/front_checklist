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
  │  └─ tsconfig / absolute import 
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
  ├─ CSS Framework or NONE
  │  └── Material or SPECTRE → 요소: 범용성 / 많은 관련 문서 / 가벼움(사이즈) / 구현 가능 여부
  ├─ naming convention 
  └─ responsive 
     └─ media query / grid / flex  
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
```


---

<sup>1</sup> [웹 접근성](https://ko.reactjs.org/docs/accessibility.html)

<sup>2</sup> [Lint](https://medium.com/@brygrill/create-react-app-with-typescript-eslint-prettier-and-github-actions-f3ce6a571c97)
