# ReactStarter
React Quick start package.json file

{
  "name": "projectname",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@material-ui/core": "^1.0.0-rc.0",
    "@material-ui/icons": "^1.0.0-rc.0",
    "lodash": "^4.17.5",
    "material-ui": "^1.0.0-beta.47",
    "node-sass-chokidar": "^1.3.0",
    "npm-run-all": "^4.1.3",
    "react": "^16.2.0",
    "react-dom": "^16.2.0",
    "react-helmet": "^5.2.0",
    "react-lazy-load": "^3.0.13",
    "react-modal": "^3.3.2",
    "react-redux": "*",
    "react-router-dom": "^4.2.2",
    "react-scripts": "1.1.1",
    "redux": "^3.7.2",
    "redux-logger": "^3.0.6",
    "redux-thunk": "^2.2.0",
    "sort-by": "^1.2.0"
  },
  "scripts": {
    "build-css": "node-sass-chokidar src/Styles/SCSS -o src/Style/",
    "watch-css": "npm run build-css && node-sass-chokidar src/Styles/SCSS -o src/Styles/ --watch --recursive",
    "start.js": "react-scripts start",
    "start": "npm-run-all -p watch-css start.js",
    "build": "npm run build-css && react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  }
}
