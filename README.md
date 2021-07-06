<h1>Step 1. Setup CRA (Create React App) </h1>

```jsx
npx create-react-app 프로젝트 폴더명
```
설치완료 후
```jsx
cd 프로젝트 폴더명
```

<h1>Step 2. 불필요한 파일 삭제</h1>
<h2>public 폴더</h2>
1) logo192.png 삭제 <br />
2) logo512.png 삭제 <br />
3) robots.txt 삭제 <br />
<h2>src 폴더</h2>
1) app.js 삭제 <br />
2) app.test 삭제 <br />
3) logo.svg 삭제 <br />
4) reportWebVitals.js 삭제 <br />
5) setupTests.js 삭제 <br />
<br />
삭제 후 <br />

![image](https://user-images.githubusercontent.com/80687334/122764197-2fb49780-d2da-11eb-90d8-c3e904c28d06.png)

<h1>Step 3. Prettier 및 Eslint 설정 </h1>
※ https://prettier.io/docs/en/integrating-with-linters.html 를 참고하여 작성하였다. <br />
<br />
1. Eslint와 Prettier를 통합하고 충돌을 없애주기 위한 패키지를 설치한다.<br />

```jsx
npm install --save-dev eslint-config-prettier
npm install --save-dev eslint-plugin-prettier
```
<br/>
2. 최상위 폴더에 .eslintrc.json, .prettierrc, .settings.json 파일을 만들어 준다.<br />
<br />
3. 각 파일에 대해 필요한 설정들을 입력해 준다. <br /> 
단, 이는 사용자와 프로젝트에 따라 다르므로 상황에 맞게 입력해야 한다. <br />
<br /> 
1) .eslintrc.json

```jsx
{
  "extends": ["react-app", "plugin:prettier/recommended"],
  "rules": {
    "prettier/prettier": [
      "error",
      {
        "endOfLine": "auto"
      }
    ]
  }
}
```
<br /> 
2) .prettierrc

```jsx
{
  "tabWidth": 2,
  "endOfLine": "lf",
  "arrowParens": "avoid",
  "singleQuote": true
}
```
<br /> 
3) .settings.json

```jsx
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.tabSize": 2,
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "javascript.format.enable": false,
  "prettier.eslintIntegration": true,
  "prettier.disableLanguages": ["js"],
  "eslint.alwaysShowStatus": true,
  "files.autoSave": "onFocusChange"
}
```

<h1>Step 4. 코드 정리</h1>
<h3>public 폴더</h3>
<h4>1. index.html</h4>

수정 후<br />

![image](https://user-images.githubusercontent.com/80687334/122748739-8369b580-d2c7-11eb-890f-c1ffbd4ccbee.png)<br />

프로젝트에 따라 사용하게 될 부분은 주석처리로 남겨둠

<h4>2.index.js</h4>

수정 후<br />

![image](https://user-images.githubusercontent.com/80687334/122763603-7a81df80-d2d9-11eb-844c-336feaaf16f8.png)

<h4>3.index.css</h4>
모든 내용을 삭제한다.<br />

<h1>Step 5. React Router 설치 및 설정</h1>
1) React Router 설치

```jsx
npm install react-router-dom
```
<br />
2) src 폴더에 Routes.jsx 파일을 만든다.<br />
<br />
3) 기본 코드를 입력해 준다.

```jsx
import React, { Component } from 'react';
import { BrowserRouter as Router, Switch, Route } from 'react-router-dom';

class Routes extends Component {
  render() {
    return (
      <Router>
        <Switch>
          <Route />
        </Switch>
      </Router>
    );
  }
}

export default Routes;
```
<br />
4) index.js에 Routes.jsx를 import 해준다.

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import Routes from './Routes';

ReactDOM.render(<Routes />, document.getElementById('root'));
```
<br />
<h1>Step 6. Reset.css 설정</h1>
1) src 폴더 내에 styles 폴더를 만들고 그 안에 Reset.css 파일을 만든다.<br />
<br />
2) 설정을 입력해준다.<br />
가장 기본적인 Reset 설정은 여기를 참고하면 된다.<br />
https://meyerweb.com/eric/tools/css/reset/ <br /><br />
3) index.js에 Reset.css를 import 해준다. <br />
단, index.css보다 먼저 import 해야 한다. 그래야 초기화 후 css 적용이 이루어진다.

```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import './styles/Reset.css';
import './index.css';
import Routes from './Routes';

ReactDOM.render(<Routes />, document.getElementById('root'));
```

<h1>이외 고려할 사항들</h1>
1. SASS(SCSS), Stylus, Less 등과 같은 CSS 전처리기 설치 <br />
2. 프로젝트 성격에 맞게 폴더 구조 및 파일 이름 convention 통일 <br />
3. 해당 프로젝트의 github에 연결하기
