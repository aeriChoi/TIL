---
description: create-react-app-typescript 프로젝트를 생성하고 기본적인 세팅을 알아보았다.
---

# Create-React-App Typescript 프로젝트 생성 및 기본세팅.

create-react-app(CRA)-typescript 프로젝트를 생성해보자.

```
npx create-react-app [프로젝트명] --template typescript

# or

yarn create-react-app [프로젝트명] --template typescript2.
```

### Eslint 설정 <a href="#eslint" id="eslint"></a>

#### Eslint 설

```
# Using npm
npm install -D eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser
npm install eslint-config-airbnb-typescript --save-dev

# Using yarn
yarn add --dev eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser
yarn add --dev eslint-config-airbnb-typescript

```

#### **`.eslintrc` 파일을 생성**

**root 디렉토리에 `.eslintrc` 파일을 생성해준다.**

```
.eslintrc

{
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"],
  "extends": ["plugin:@typescript-eslint/recommended"]
}
```

****

**package.json 파일에 스크립트를 추가한다.**

```
package.json

"scripts": {
    "lint": "eslint './src/**/*.{ts,tsx,js,jsx}'",
    "lint:fix": "eslint --fix './src/**/*.{ts,tsx,js,jsx}'"
  },
```
