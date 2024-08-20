  root: true,
  env: { browser: true, es2020: true },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:react-hooks/recommended',
  ],
  ignorePatterns: ['dist', '.eslintrc.cjs'],
  parser: '@typescript-eslint/parser',
  plugins: ['react-refresh'],
  rules: {
    'react-refresh/only-export-components': [
      'warn',
      { allowConstantExport: true },
    ],
  },
}
 24 changes: 24 additions & 0 deletions24  
.gitignore
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,24 @@
# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
lerna-debug.log*

node_modules
dist
dist-ssr
*.local

# Editor directories and files
.vscode/*
!.vscode/extensions.json
.idea
.DS_Store
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?
 30 changes: 30 additions & 0 deletions30  
README.md
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,30 @@
# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
    project: ['./tsconfig.json', './tsconfig.node.json'],
    tsconfigRootDir: __dirname,
  },
}
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list
 13 changes: 13 additions & 0 deletions13  
index.html
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React + TS</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
 4,242 changes: 4,242 additions & 0 deletions4,242  
package-lock.json
Large diffs are not rendered by default.

 31 changes: 31 additions & 0 deletions31  
package.json
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,31 @@
{
  "name": "hamster-kombat-telegram-mini-app-clone",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc -b && vite build",
    "lint": "eslint . --ext ts,tsx --report-unused-disable-directives --max-warnings 0",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.3.1",
    "react-dom": "^18.3.1"
  },
  "devDependencies": {
    "@types/react": "^18.3.3",
    "@types/react-dom": "^18.3.0",
    "@typescript-eslint/eslint-plugin": "^7.13.1",
    "@typescript-eslint/parser": "^7.13.1",
    "@vitejs/plugin-react": "^4.3.1",
    "autoprefixer": "^10.4.19",
    "eslint": "^8.57.0",
    "eslint-plugin-react-hooks": "^4.6.2",
    "eslint-plugin-react-refresh": "^0.4.7",
    "postcss": "^8.4.38",
    "tailwindcss": "^3.4.4",
    "typescript": "^5.2.2",
    "vite": "^5.3.1"
  }
}
 6 changes: 6 additions & 0 deletions6  
postcss.config.js
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,6 @@
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
 1 change: 1 addition & 0 deletions1  
public/vite.svg
Loading
 42 changes: 42 additions & 0 deletions42  
src/App.css
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,42 @@
#root {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.react:hover {
  filter: drop-shadow(0 0 2em #61dafbaa);
}

@keyframes logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@media (prefers-reduced-motion: no-preference) {
  a:nth-of-type(2) .logo {
    animation: logo-spin infinite 20s linear;
  }
}

.card {
  padding: 2em;
}

.read-the-docs {
  color: #888;
}
 35 changes: 35 additions & 0 deletions35  
src/App.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,35 @@
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'

function App() {
  const [count, setCount] = useState(0)

  return (
    <>
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.tsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
    </>
  )
}

export default App
 1 change: 1 addition & 0 deletions1  
src/assets/react.svg
Loading
 13 changes: 13 additions & 0 deletions13  
src/icons/Coins.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
import { IconProps } from "../utils/types";


const Coins: React.FC<IconProps> = ({ size = 24, className = "" }) => {

    const svgSize = `${size}px`;

    return (
        <svg fill="currentColor" className={className} height={svgSize} width={svgSize} viewBox="0 0 512 512" xmlns="http://www.w3.org/2000/svg"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"><path d="M0 405.3V448c0 35.3 86 64 192 64s192-28.7 192-64v-42.7C342.7 434.4 267.2 448 192 448S41.3 434.4 0 405.3zM320 128c106 0 192-28.7 192-64S426 0 320 0 128 28.7 128 64s86 64 192 64zM0 300.4V352c0 35.3 86 64 192 64s192-28.7 192-64v-51.6c-41.3 34-116.9 51.6-192 51.6S41.3 334.4 0 300.4zm416 11c57.3-11.1 96-31.7 96-55.4v-42.7c-23.2 16.4-57.3 27.6-96 34.5v63.6zM192 160C86 160 0 195.8 0 240s86 80 192 80 192-35.8 192-80-86-80-192-80zm219.3 56.3c60-10.8 100.7-32 100.7-56.3v-42.7c-35.5 25.1-96.5 38.6-160.7 41.8 29.5 14.3 51.2 33.5 60 57.2z"></path></g></svg>
    );
};

export default Coins;
 13 changes: 13 additions & 0 deletions13  
src/icons/Friends.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
import { IconProps } from "../utils/types";


const Friends: React.FC<IconProps> = ({ size = 24, className = "" }) => {

    const svgSize = `${size}px`;

    return (
        <svg viewBox="0 0 28 28" version="1.1" xmlns="http://www.w3.org/2000/svg" fill="currentColor" className={className} height={svgSize} width={svgSize}><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <g id="🔍-Product-Icons" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"> <g id="ic_fluent_people_community_28_filled" fill="currentColor" fill-rule="nonzero"> <path d="M17.75,18 C18.7164983,18 19.5,18.7835017 19.5,19.75 L19.5,21.7519766 L19.4921156,21.8604403 C19.1813607,23.9866441 17.2715225,25.0090369 14.0667905,25.0090369 C10.8736123,25.0090369 8.93330141,23.9983408 8.51446278,21.8965776 L8.5,21.75 L8.5,19.75 C8.5,18.7835017 9.28350169,18 10.25,18 L17.75,18 Z M18.2439108,11.9999135 L24.25,12 C25.2164983,12 26,12.7835017 26,13.75 L26,15.7519766 L25.9921156,15.8604403 C25.6813607,17.9866441 23.7715225,19.0090369 20.5667905,19.0090369 L20.3985759,19.007437 C20.0900029,17.9045277 19.1110503,17.0815935 17.9288034,17.0057197 L17.75,17 L16.8277704,17.0007255 C17.8477843,16.1757619 18.5,14.9140475 18.5,13.5 C18.5,12.9740145 18.4097576,12.4691063 18.2439108,11.9999135 Z M3.75,12 L9.75608915,11.9999135 C9.59024243,12.4691063 9.5,12.9740145 9.5,13.5 C9.5,14.8308682 10.0777413,16.0267978 10.996103,16.8506678 L11.1722296,17.0007255 L10.25,17 C8.9877951,17 7.92420242,17.85036 7.60086562,19.0094363 L7.5667905,19.0090369 C4.37361228,19.0090369 2.43330141,17.9983408 2.01446278,15.8965776 L2,15.75 L2,13.75 C2,12.7835017 2.78350169,12 3.75,12 Z M14,10 C15.9329966,10 17.5,11.5670034 17.5,13.5 C17.5,15.4329966 15.9329966,17 14,17 C12.0670034,17 10.5,15.4329966 10.5,13.5 C10.5,11.5670034 12.0670034,10 14,10 Z M20.5,4 C22.4329966,4 24,5.56700338 24,7.5 C24,9.43299662 22.4329966,11 20.5,11 C18.5670034,11 17,9.43299662 17,7.5 C17,5.56700338 18.5670034,4 20.5,4 Z M7.5,4 C9.43299662,4 11,5.56700338 11,7.5 C11,9.43299662 9.43299662,11 7.5,11 C5.56700338,11 4,9.43299662 4,7.5 C4,5.56700338 5.56700338,4 7.5,4 Z" id="🎨-Color"> </path> </g> </g> </g></svg>
    );
};

export default Friends;
 13 changes: 13 additions & 0 deletions13  
src/icons/Hamster.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
import { IconProps } from "../utils/types";


const Hamster: React.FC<IconProps> = ({ size = 24, className = "" }) => {

    const svgSize = `${size}px`;

    return (
        <svg fill="currentColor" className={className} height={svgSize} width={svgSize} version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg"  viewBox="0 0 512 512"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <g> <g> <path d="M0,135.434c0,27.786,13.637,54.737,37.605,71.028c18.611-53.476,51.532-106.098,95.693-142.701 C76.535,26.245,0,66.968,0,135.434z"></path> </g> </g> <g> <g> <path d="M378.702,63.759c43.385,35.965,76.691,88.103,95.692,142.702C498.321,190.199,512,163.267,512,135.434 C512,66.961,435.457,26.251,378.702,63.759z"></path> </g> </g> <g> <g> <path d="M256.003,49.597c-0.012,0-0.031,0-0.044,0C141.939,49.634,53.684,193.404,53.684,302.856 c0,111.622,89.237,159.667,202.316,159.667c113.018,0,202.316-48.063,202.316-159.667 C458.316,193.417,370.064,49.597,256.003,49.597z M335.505,162.289c12.198,0,22.086,9.888,22.086,22.086 s-9.888,22.086-22.086,22.086s-22.086-9.888-22.086-22.086S323.307,162.289,335.505,162.289z M176.495,162.289 c12.198,0,22.086,9.888,22.086,22.086s-9.888,22.086-22.086,22.086c-12.198,0-22.086-9.888-22.086-22.086 S164.297,162.289,176.495,162.289z M346.837,357.468c-11.685,8.312-25.551,12.62-39.522,12.623v30.149 c0,9.22-7.475,16.696-16.696,16.696H221.38c-9.22,0-16.696-7.475-16.696-16.696v-30.148c-13.968-0.002-27.828-4.306-39.508-12.615 c-18.199-12.948-28.638-33.164-28.638-55.465c0-9.22,7.475-16.696,16.696-16.696s16.696,7.475,16.696,16.696 c0,11.355,5.323,21.654,14.603,28.257c23.145,16.467,54.771-0.336,54.771-28.257c0-1.198,0.131-2.364,0.372-3.489l-33.528-38.715 c-9.33-10.774-1.678-27.626,12.621-27.626h74.464c14.253,0,21.981,16.816,12.621,27.625l-33.528,38.715 c0.239,1.126,0.372,2.293,0.372,3.491c0,27.809,31.539,44.783,54.784,28.249c9.272-6.597,14.589-16.893,14.589-28.249 c0-9.22,7.475-16.696,16.696-16.696c9.22,0,16.696,7.475,16.696,16.696C375.46,324.314,365.027,344.527,346.837,357.468z"></path> </g> </g> </g></svg>
    );
};

export default Hamster;
 13 changes: 13 additions & 0 deletions13  
src/icons/Info.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
import { IconProps } from "../utils/types";


const Info: React.FC<IconProps> = ({ size = 24, className = "" }) => {

    const svgSize = `${size}px`;

    return (
        <svg fill="currentColor" className={className} height={svgSize} width={svgSize} viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"><path d="M12,2A10,10,0,1,0,22,12,10,10,0,0,0,12,2Zm1,15a1,1,0,0,1-2,0V11a1,1,0,0,1,2,0ZM12,8a1.5,1.5,0,1,1,1.5-1.5A1.5,1.5,0,0,1,12,8Z"></path></g></svg>
    );
};

export default Info;
 13 changes: 13 additions & 0 deletions13  
src/icons/Mine.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
import { IconProps } from "../utils/types";


const Mine: React.FC<IconProps> = ({ size = 24, className = "" }) => {

    const svgSize = `${size}px`;

    return (
        <svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32" fill="currentColor" className={className} height={svgSize} width={svgSize}><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <path d="M11.707,17.707c-0.195-0.195-0.451-0.293-0.707-0.293s-0.512,0.098-0.707,0.293l-6.586,6.586 C3.512,24.488,3.256,24.586,3,24.586s-0.512-0.098-0.707-0.293l-0.637-0.637c-0.973-0.973-1.159-2.484-0.451-3.665L6,12L3,9 L2.391,7.173c-0.24-0.719-0.052-1.511,0.483-2.047l2.252-2.252C5.507,2.493,6.018,2.288,6.54,2.288c0.212,0,0.425,0.034,0.632,0.103 L9,3l3,3l7.991-4.795c0.479-0.287,1.013-0.428,1.542-0.428c0.776,0,1.544,0.3,2.122,0.879l0.637,0.637 c0.391,0.391,0.391,1.024,0,1.414l-6.586,6.586c-0.391,0.391-0.391,1.024,0,1.414l0.586,0.586c0.383,0.383,0.385,0.997,0.017,1.389 l-4.628,4.628C13.49,18.49,13.246,18.586,13,18.586c-0.256,0-0.512-0.098-0.707-0.293L11.707,17.707z M30.586,26.586L18.707,14.707 l-4,4l11.879,11.879c0.391,0.391,0.902,0.586,1.414,0.586s1.024-0.195,1.414-0.586l1.172-1.172 C31.367,28.633,31.367,27.367,30.586,26.586z"></path> </g></svg>
    );
};

export default Mine;
 13 changes: 13 additions & 0 deletions13  
src/icons/Settings.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
import { IconProps } from "../utils/types";


const Settings: React.FC<IconProps> = ({ size = 24, className = "" }) => {

    const svgSize = `${size}px`;

    return (
        <svg fill="currentColor" className={className} height={svgSize} width={svgSize} viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g id="SVGRepo_tracerCarrier" stroke-linecap="round" stroke-linejoin="round"></g><g id="SVGRepo_iconCarrier"> <path fill-rule="evenodd" clip-rule="evenodd" d="M14.2788 2.15224C13.9085 2 13.439 2 12.5 2C11.561 2 11.0915 2 10.7212 2.15224C10.2274 2.35523 9.83509 2.74458 9.63056 3.23463C9.53719 3.45834 9.50065 3.7185 9.48635 4.09799C9.46534 4.65568 9.17716 5.17189 8.69017 5.45093C8.20318 5.72996 7.60864 5.71954 7.11149 5.45876C6.77318 5.2813 6.52789 5.18262 6.28599 5.15102C5.75609 5.08178 5.22018 5.22429 4.79616 5.5472C4.47814 5.78938 4.24339 6.1929 3.7739 6.99993C3.30441 7.80697 3.06967 8.21048 3.01735 8.60491C2.94758 9.1308 3.09118 9.66266 3.41655 10.0835C3.56506 10.2756 3.77377 10.437 4.0977 10.639C4.57391 10.936 4.88032 11.4419 4.88029 12C4.88026 12.5581 4.57386 13.0639 4.0977 13.3608C3.77372 13.5629 3.56497 13.7244 3.41645 13.9165C3.09108 14.3373 2.94749 14.8691 3.01725 15.395C3.06957 15.7894 3.30432 16.193 3.7738 17C4.24329 17.807 4.47804 18.2106 4.79606 18.4527C5.22008 18.7756 5.75599 18.9181 6.28589 18.8489C6.52778 18.8173 6.77305 18.7186 7.11133 18.5412C7.60852 18.2804 8.2031 18.27 8.69012 18.549C9.17714 18.8281 9.46533 19.3443 9.48635 19.9021C9.50065 20.2815 9.53719 20.5417 9.63056 20.7654C9.83509 21.2554 10.2274 21.6448 10.7212 21.8478C11.0915 22 11.561 22 12.5 22C13.439 22 13.9085 22 14.2788 21.8478C14.7726 21.6448 15.1649 21.2554 15.3694 20.7654C15.4628 20.5417 15.4994 20.2815 15.5137 19.902C15.5347 19.3443 15.8228 18.8281 16.3098 18.549C16.7968 18.2699 17.3914 18.2804 17.8886 18.5412C18.2269 18.7186 18.4721 18.8172 18.714 18.8488C19.2439 18.9181 19.7798 18.7756 20.2038 18.4527C20.5219 18.2105 20.7566 17.807 21.2261 16.9999C21.6956 16.1929 21.9303 15.7894 21.9827 15.395C22.0524 14.8691 21.9088 14.3372 21.5835 13.9164C21.4349 13.7243 21.2262 13.5628 20.9022 13.3608C20.4261 13.0639 20.1197 12.558 20.1197 11.9999C20.1197 11.4418 20.4261 10.9361 20.9022 10.6392C21.2263 10.4371 21.435 10.2757 21.5836 10.0835C21.9089 9.66273 22.0525 9.13087 21.9828 8.60497C21.9304 8.21055 21.6957 7.80703 21.2262 7C20.7567 6.19297 20.522 5.78945 20.2039 5.54727C19.7799 5.22436 19.244 5.08185 18.7141 5.15109C18.4722 5.18269 18.2269 5.28136 17.8887 5.4588C17.3915 5.71959 16.7969 5.73002 16.3099 5.45096C15.8229 5.17191 15.5347 4.65566 15.5136 4.09794C15.4993 3.71848 15.4628 3.45833 15.3694 3.23463C15.1649 2.74458 14.7726 2.35523 14.2788 2.15224ZM12.5 15C14.1695 15 15.5228 13.6569 15.5228 12C15.5228 10.3431 14.1695 9 12.5 9C10.8305 9 9.47716 10.3431 9.47716 12C9.47716 13.6569 10.8305 15 12.5 15Z" fill="currentColor"></path> </g></svg>
    );
};

export default Settings;
 Binary file addedBIN +7.02 KB 
src/images/binance-logo.png
Loading
 Binary file addedBIN +228 KB 
src/images/daily-cipher.png
Loading
 Binary file addedBIN +224 KB 
src/images/daily-combo.png
Loading
 Binary file addedBIN +234 KB 
src/images/daily-reward.png
Loading
 Binary file addedBIN +13.4 KB 
src/images/dollar-coin.png
Loading
 Binary file addedBIN +32.7 KB 
src/images/hamster-coin.png
Loading
 Binary file addedBIN +33.3 KB 
src/images/hamster-exchange.png
Loading
 19 changes: 19 additions & 0 deletions19  
src/images/index.ts
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,19 @@
import hamsterExchange from "./hamster-exchange.png";
import binanceLogo from "./binance-logo.png";
import dollarCoin from "./dollar-coin.png";
import dailyReward from "./daily-reward.png";
import dailyCipher from "./daily-cipher.png";
import dailyCombo from "./daily-combo.png";
import mainCharacter from "./main-character.png";
import hamsterCoin from "./hamster-coin.png";

export {
    hamsterExchange,
    binanceLogo,
    dollarCoin,
    dailyReward,
    dailyCipher,
    dailyCombo,
    mainCharacter,
    hamsterCoin
};
 Binary file addedBIN +43.6 KB 
src/images/main-character.png
Loading
 3 changes: 3 additions & 0 deletions3  
src/index.css
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,3 @@
@tailwind base;
@tailwind components;
@tailwind utilities;
 10 changes: 10 additions & 0 deletions10  
src/main.tsx
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,10 @@
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.tsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
 4 changes: 4 additions & 0 deletions4  
src/utils/types.ts
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,4 @@
export type IconProps = {
    size?: number;
    className?: string;
}
 1 change: 1 addition & 0 deletions1  
src/vite-env.d.ts
Original file line number	Diff line number	Diff line change
@@ -0,0 +1 @@
/// <reference types="vite/client" />
 12 changes: 12 additions & 0 deletions12  
tailwind.config.js
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,12 @@
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

 27 changes: 27 additions & 0 deletions27  
tsconfig.app.json
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,27 @@
{
  "compilerOptions": {
    "composite": true,
    "tsBuildInfoFile": "./node_modules/.tmp/tsconfig.app.tsbuildinfo",
    "target": "ES2020",
    "useDefineForClassFields": true,
    "lib": ["ES2020", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "skipLibCheck": true,

    /* Bundler mode */
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "moduleDetection": "force",
    "noEmit": true,
    "jsx": "react-jsx",

    /* Linting */
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
  },
  "include": ["src"]
}
 11 changes: 11 additions & 0 deletions11  
tsconfig.json
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,11 @@
{
  "files": [],
  "references": [
    {
      "path": "./tsconfig.app.json"
    },
    {
      "path": "./tsconfig.node.json"
    }
  ]
}
 13 changes: 13 additions & 0 deletions13  
tsconfig.node.json
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,13 @@
{
  "compilerOptions": {
    "composite": true,
    "tsBuildInfoFile": "./node_modules/.tmp/tsconfig.node.tsbuildinfo",
    "skipLibCheck": true,
    "module": "ESNext",
    "moduleResolution": "bundler",
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "noEmit": true
  },
  "include": ["vite.config.ts"]
}
 7 changes: 7 additions & 0 deletions7  
vite.config.ts
Original file line number	Diff line number	Diff line change
@@ -0,0 +1,7 @@
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
})
