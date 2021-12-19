# CRA에 tsconfig.paths.json 추가하기

**root 디렉토리에 `tsconfig.paths.json`** 파일을 추가한다.

```
{
  "compilerOptions" : {
    "baseUrl": "./src",
    "paths": {
      "@components": [
        "components/index"
      ],
      "@containers": [
        "containers/index"
      ],
      "@cores": [
        "cores/index"
      ],
      "@pages": [
        "pages/index"
      ],
      "@redux": [
        "redux/index"
      ],
      "@selectors": [
        "selectors/index"
      ],
      "@styles": [
        "styles/index"
      ],
      "@utils": [
        "utils/index"
      ],
      "@components/*": [
        "components/*"
      ],
      "@containers/*": [
        "containers/*"
      ],
      "@cores/*": [
        "cores/*"
      ],
      "@pages/*": [
        "pages/*"
      ],
      "@redux/*": [
        "redux/*"
      ],
      "@selectors/*": [
        "selectors/*"
      ],
      "@styles/*": [
        "styles/*"
      ],
      "@utils/*": [
        "utils/*"
      ]
    }
  }
}
```

**Craco 설치하기**

```
// Some code
# Using npm
npm install -D @craco/craco
npm install -D craco-alias

# Using yarn
yarn add -D @craco/craco
yarn add -D prettier craco-alias
```

**root 디렉토리에 craco.config.js 파일을 추가한다.**&#x20;

```
const CracoAlias = require('craco-alias')

module.exports = {
  plugins: [
    {
      plugin: CracoAlias,
      options: {
        source: 'tsconfig',
        baseUrl: './src',
        tsConfigPath: './tsconfig.paths.json',
      },
    },
  ],
}
```

**`package.json`** 파일에 **`scripts`**를 수정한다.&#x20;

```
"start": "craco start",
"build": "craco build"
```
