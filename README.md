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
1) logo.192.png 삭제 <br />
2) logo.512.png 삭제 <br />
3) robots.txt 삭제 <br />
<h2>src 폴더</h2>
1) app.test 삭제 <br />
2) logo.svg 삭제 <br />
3) reportWebVitals.js 삭제 <br />
4) setupTests.js 삭제 <br />
<br />
삭제 전<br />

![image](https://user-images.githubusercontent.com/80687334/122746014-8dd68000-d2c4-11eb-96ad-f23b22058fe5.png)

삭제 후 <br />

![image](https://user-images.githubusercontent.com/80687334/122749116-e9eed380-d2c7-11eb-95f4-4c85710c1d63.png)

<h1>Step 3. Prettier 및 Eslint 설정 </h1>
※ https://prettier.io/docs/en/integrating-with-linters.html 를 참고하여 작성하였다. <br />
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
수정 전<br />

![image](https://user-images.githubusercontent.com/80687334/122748791-8e244a80-d2c7-11eb-9b95-85342e57ff43.png)

수정 후<br />

![image](https://user-images.githubusercontent.com/80687334/122748739-8369b580-d2c7-11eb-890f-c1ffbd4ccbee.png)<br />

프로젝트에 따라 사용하게 될 부분은 주석처리로 남겨둠

<h4>2. App.js</h4>
수정 전<br />

![image](https://user-images.githubusercontent.com/80687334/122758199-7bb00e00-d2d3-11eb-9980-318462c8a00a.png)

수정 후<br />

![image](https://user-images.githubusercontent.com/80687334/122758272-8f5b7480-d2d3-11eb-83aa-d030373b1e5c.png)

<h4>3. App.css</h4>
모든 내용을 지워준다.

<h4>4.index.js</h4>
수정 전<br />

![image](https://user-images.githubusercontent.com/80687334/122758388-b4e87e00-d2d3-11eb-85d8-c118420e01b7.png)

수정 후<br />

![image](https://user-images.githubusercontent.com/80687334/122758472-cb8ed500-d2d3-11eb-90a8-c5ed47c87be5.png)




