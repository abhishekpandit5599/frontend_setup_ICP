# React Native greet_app

Install npm pacakges
`npm install --save react react-dom`
`npm install --save-dev typescript ts-loader`
`npm i react-router-dom`

## Create `tsconfig.json` file in root directory of project
```js
{
    "compilerOptions": {
      "target": "es2018",        /* Specify ECMAScript target version: 'ES3' (default), 'ES5', 'ES2015', 'ES2016', 'ES2017', 'ES2018', 'ES2019' or 'ESNEXT'. */
      "lib": ["ES2018", "DOM"],  /* Specify library files to be included in the compilation. */
      "allowJs": true,           /* Allow javascript files to be compiled. */
      "jsx": "react",            /* Specify JSX code generation: 'preserve', 'react-native', or 'react'. */
    },
    "include": ["src/**/*"],
}
```

```js
    entry: {
      // The frontend.entrypoint points to the HTML file for this build, so you need
      // to replace the extension to `.js`.
      index: path.join(__dirname, asset_entry).replace(/\.html$/, ".jsx"),
    },
```

```js
module: {
      rules: [
        { test: /\.(js|ts)x?$/, loader: "ts-loader" }
      ]
    },

This setting enables the project to use the `ts-loader` compiler for a React JavaScript `index.jsx` file. Note that there’s a commented section in the default `webpack.config.js` file that you can modify to add the `module` key.
```

## Create index.jsx file
```js
import React from "react";
import { createRoot } from "react-dom/client";
import App from "./App";

const rootElement = document.getElementById("root");
const root = createRoot(rootElement);
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

# Create App.jsx file in src/<Frontend Folder>/src
```js
import { BrowserRouter as Router, Routes,Route,} from "react-router-dom";

function App() {
  return (
    <div className="App">
       <Router>
        <Routes>
          <Route path="/" element={<YOUR_COMPONENT />}/>
        </Routes>
      </Router>
    </div>
  );
}

export default App;
```