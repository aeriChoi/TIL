---
description: create-react-app-typescript 프로젝트를 생성하고 기본적인 세팅을 알아보았다.
---

# Create-React-App Typescript 프로젝트 생성 및 기본세팅.

### create-react-app 생성하기

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

# Using yarn
yarn add --dev eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser


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



### React eslint Airbnb 설정 <a href="#2-react-eslint-airbnb" id="2-react-eslint-airbnb"></a>

```
npx install-peerdeps --dev eslint-config-airbnb
```

```
.eslintrc

{
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"],
  "extends": ["airbnb", "airbnb/hooks", "plugin:@typescript-eslint/recommended"]
}
```

****

### **Prettier 설정**

**prettier 설**

```
# Using npm
npm install -D prettier eslint-config-prettier eslint-plugin-prettier

# Using yarn
yarn add --dev prettier eslint-config-prettier eslint-plugin-prettier
```



**`.prettierrc`** 파일 설정&#x20;

{% hint style="info" %}
prettier와 ESLint 들여쓰기 설정이 서로 중복 될 수 있.\
이를 해결하려면 `@typescript-eslint/indent`오류가 표시 되지 않도록 해야한다.
{% endhint %}

```
.prettierrc

{
  "singleQuote": true,
  "parser": "typescript",
  "semi": true,
  "useTabs": true,
  "printWidth": 120
}
```



**package.json 파일에 스크립트를 추가한다.**

```
package.json

"scripts": {
    "prettier": "prettier --write --config ./.prettierrc './src/**/*.{ts,tsx}'",
  },
```

```
"parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"],
  "extends": [
    "prettier",
    "airbnb",
    "airbnb/hooks",
    "prettier/react",
    "plugin:@typescript-eslint/recommended",
    "prettier/@typescript-eslint",
    "plugin:prettier/recommended"
  ]
```

#### ****

#### **참조**

* [Eslint 적용하기(React + Typescript + Prettier)](https://flamingotiger.github.io/javascript/eslint-setup/#2-1-eslint-config-airbnb-%EB%A1%9C-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0)
* [\[개발 초기 세팅하기\] ESLint (eslint-config-airbnb-typescript) + Prettier + React + TypeScript](https://velog.io/@9rganizedchaos/%EA%B0%9C%EB%B0%9C-%EC%B4%88%EA%B8%B0-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0-ESLint-eslint-config-airbnb-typescript-Prettier-React-TypeScript)
* [create-react-app Typescript 생성 및 세팅](https://kod4284.github.io/2020/03/03/create-react-app-typescript-setting/)
