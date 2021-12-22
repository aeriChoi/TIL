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

### Eslint & **prettier** 설정 <a href="#eslint" id="eslint"></a>



```
# Using npm
npm install -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-airbnb-typescript
npm install -D prettier eslint-config-prettier eslint-plugin-prettier

# Using yarn
yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-airbnb-typescript
yarn add -D prettier eslint-config-prettier eslint-plugin-prettier

npx install-peerdeps --dev eslint-config-airbnb

```

#### **`.eslintrc.js` 파일을 생성**

**root 디렉토리에 `.eslintrc` 파일을 생성해준다.**

```
module.exports = {
  env: {
    browser: true,
    es6: true,
    node: true,
  },
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  extends: [
    'airbnb-typescript',
    'airbnb/hooks',
    'plugin:@typescript-eslint/recommended',
    'plugin:jest/recommended',
    'plugin:prettier/recommended',
  ],
  plugins: ['react', '@typescript-eslint'],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaFeatures: { jsx: true },
    ecmaVersion: 2018,
    sourceType: 'module',
    project: './tsconfig.json',
  },
  rules: {
    indent: [2, 2, { SwitchCase: 1 }],
    'linebreak-style': 'off',
    'prettier/prettier': [
      'error',
      {
        endOfLine: 'auto',
      },
    ],
    '@typescript-eslint/explicit-module-boundary-types': 'off',
    'react-hooks/exhaustive-deps': 'error',
    'no-alert': 'off',
    'no-console': 'off',
    'no-shadow': 'off',
    '@typescript-eslint/no-shadow': 'off',
    'arrow-parens': 'off',
    'react/no-array-index-key': 'off',
    'implicit-arrow-linebreak': 'off',
    'import/prefer-default-export': 'off',
    'import/no-cycle': 'off',
    'no-undef': 'off',
    'react/no-unescaped-entities': 'off',
    'import/extensions': 'off',
    'react/prop-types': 'off',
    'no-unused-vars': 'off',
    'import/no-unresolved': 'off',
    'react/jsx-props-no-spreading': 'off',
    '@typescript-eslint/no-non-null-assertion': 'off',
    'react/display-name': 'off',
    camelcase: 'off',
    'global-require': 'off',
    'react/jsx-wrap-multilines': 'off',
    'no-control-regex': 0,
    'no-use-before-define': 0,
    'import/no-extraneous-dependencies': 0,
    'react/jsx-filename-extension': [2, { extensions: ['.js', '.jsx', '.ts', '.tsx'] }],
    'jsx-a11y/no-noninteractive-element-interactions': 0,
  },
};

```

****

**package.json 파일에 스크립트를 추가한다.**

```
package.json

"scripts": {
    "format": "prettier --write src/**/*.ts{,x}",
    "lint": "tsc --noEmit && eslint src/**/*.ts{,x}"
  },
```



**`.prettierrc`** 파일 설정&#x20;

{% hint style="info" %}
prettier와 ESLint 들여쓰기 설정이 서로 중복 될 수 있.\
이를 해결하려면 `@typescript-eslint/indent`오류가 표시 되지 않도록 해야한다.
{% endhint %}

```
{
  "singleQuote": true,
  "semi": true,
  "tabWidth": 2,
  "trailingComma": "es5",
  "printWidth": 120,
  "bracketSpacing": true,
  "arrowParens": "avoid"
}
```

**`tsconfig.json`** 추가

```
include": [
    "src",
    ".eslintrc.js" // 추가하기
 ]
```

#### **참조**

* [Eslint 적용하기(React + Typescript + Prettier)](https://flamingotiger.github.io/javascript/eslint-setup/#2-1-eslint-config-airbnb-%EB%A1%9C-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0)
* [\[개발 초기 세팅하기\] ESLint (eslint-config-airbnb-typescript) + Prettier + React + TypeScript](https://velog.io/@9rganizedchaos/%EA%B0%9C%EB%B0%9C-%EC%B4%88%EA%B8%B0-%EC%84%B8%ED%8C%85%ED%95%98%EA%B8%B0-ESLint-eslint-config-airbnb-typescript-Prettier-React-TypeScript)
* [create-react-app Typescript 생성 및 세팅](https://kod4284.github.io/2020/03/03/create-react-app-typescript-setting/)
* [Create-React-App with TypeScript, ESLint, Prettier, and Github Actions](https://brygrill.medium.com/create-react-app-with-typescript-eslint-prettier-and-github-actions-f3ce6a571c97)
