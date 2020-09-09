# full-stack-template

## Setup Guide

1. New repo on Github (ReadMe, Gitignore auf node, MIT License)
2. Clone it to local
3. package.json als Manifest Datei (npm init -y)
4. Author, License (MIT), „private” : true
5. Touch server.js and change main in package.json
6. npm install express
7. Add express starter code to server.js and add start script to package.json
8. server.js -> process.env.PORT || 3000
Commit for Heroku //PR#1
9. Switch to HEROKU
10. Create new pipeline and connect with Github repo
11. Enable review apps / Create new check use Europe
12. Add app in production / Create new app with unique name (Europe)
13. Click on app name (configure Dino if needed (Hobby Dino)) -> Deploy -> Automatic deploys -> Enable
14. Manual deploy -> deploy branch
15. Switch to VS Code
16. npm install --save-dev prettier // Echo {}> .prettierrc.json for prettier configuration
17. Add prettierignore with build coverage
18. npx prettier —write . For check
19.add script for nix prettier: “prettify”: “prettier --write .”
20. Npm install eslint —save-dev // VSCode question Allow
21. Downgrade eslint to „^6.6.0" with npm install eslint@^6.6.0 —save-dev
22. npx eslint --init: check syntax and find problems // Common JS // None of these // No // Node // JSON
23. eslint config prettier, damit sich nichts beißt with $ npm install --save-dev eslint-config-prettier
24. in der eslintrc extends Array und prettier hinzufügen
25. install lint staged wit npx mrm lint-staged
26. Add json to lint-staged
27. Create react app to client with npx create-react-app client
28. Run build script in client-Level ausführen noch nicht nötig
29. ES LINT FAILURE : 
Gemeinsame ESLint
Client package.json  “eslintConfig”: {
  “extends”: “react-app”
 },
Entfernen
Define global eslint config eslintrc-< add/change it to: {
 “env”: {
  “browser”: true,
  “commonjs”: true,
  “es6”: true,
  “node”: true
 },
 “extends”: [
  “react-app”,
  “eslint:recommended”,
  “plugin:react/recommended”,
  “prettier”
 ],
 “globals”: {
  “Atomics”: “readonly”,
  “SharedArrayBuffer”: “readonly”
 },
 “parserOptions”: {
  “ecmaFeatures”: {
   “jsx”: true
  },
  “ecmaVersion”: 2018,
  “sourceType”: “module”
 },
 “plugins”: [“react”],
 “rules”: {}
}
And install with $ npm install --save-dev eslint-config-react-app @typescript-eslint/eslint-plugin@2.x @typescript-eslint/parser@2.x babel-eslint@10.x eslint@6.x eslint-plugin-flowtype@4.x eslint-plugin-import@2.x eslint-plugin-jsx-a11y@6.x eslint-plugin-react@7.x eslint-plugin-react-hooks@2.x
30. testscript für client im toplevel anlegen lint script
31. lintscript
32. eslintignore
33. Add lint to test script
34. Add build script to top-level and test it
35. Add static route (client/build) in use to server.js
// change server.js
const express = require(“express”);
const app = express();
const path = require(“path”);
const port = process.env.PORT || 3000;
app.use(express.static(path.join(__dirname, “client/build”)));
app.listen(port, () => {
 console.log(`Example app listening at http://localhost:${port}`);
});
36. Add post install s
37.Enable Github CI => Register Actions => Node.js Set up to this workflow
38. Add husky: pre-push // ADD CI with true
39. Change to client and install storybook with npx sb init 
40. Quote die Args in der >Page.js sonst werden diese als Fehler angezeigt
41. verschieben der client dev dependencies in dependencies da Heroku diese ignoriert
42. npm install aufrufen
43. Add npm run build-storybook to top-level build script an run it in toplevelg
44. Add storybook static to gitignore
45. Add app.use for storybook
CHECK!!!
46. client lvl: npm install react-router-dom
47. In <App.js> auskommentiert:
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";
48. client lvl: npm install @emotion/styled @emotion/core
49. client lvl: npm i react-query
50. client lvl: npm i prop-types
51. top lvl: npm i dotenv
52. top lvl: npm i node-fetch (b
