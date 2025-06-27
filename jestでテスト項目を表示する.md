
`package.json`の”test”に‘jest --verbose‘を記載する
```diff
  "scripts": {

    "dev": "vite",

    "build": "tsc -b && vite build",

    "lint": "eslint .",

    "preview": "vite preview",

+    "test": "jest --verbose"
-    "test": "jest"

  },
```
