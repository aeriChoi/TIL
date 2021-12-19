# CRA에 tsconfig.paths.json 추가하기

**`tsconfig.paths.json`** 추가하기

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
