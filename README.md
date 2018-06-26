# ReactStarter
React Quick start package.json file
```
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
    "sort-by": "^1.2.0",
    "redux-mock-store": "^1.5.1",
    "enzyme": "^3.1.0",
    "enzyme-adapter-react-16": "^1.0.2"
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
}`

#

```let rootReducer = combineReducers({
  ...reducers name here...
});
export default rootReducer

```import React from 'react';
import ReactDOM from 'react-dom';
import './Styles/main.css';
import App from './Components/App';
import {createStore, applyMiddleware, compose} from 'redux'
import {BrowserRouter} from 'react-router-dom'
import registerServiceWorker from './registerServiceWorker';
import {Provider} from 'react-redux'
import reducers from './Store/index'
import thunk from 'redux-thunk'
import logger from 'redux-logger'
let middleware = applyMiddleware(thunk, logger)

const store = createStore(
  reducers,
  compose (middleware, window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__())
)

ReactDOM.render(
  <BrowserRouter>
  <Provider store={store}>
    <App/>
  </Provider>
</BrowserRouter>, document.getElementById('root'));
registerServiceWorker();


```import React, { Component } from 'react';
import '../Styles/App.css';
import Community from './Community/Community'
import {Route} from 'react-router-dom'

//import NOTFOUND from '../Components/NotFound/NotFound'
class App extends Component {
  render() {
    return (
      <div className="App">
          <Route exact path="/" render={() => <Community path=""/>}/>
          <Route exact path="/react" render={() => <Community path="react"/>}/>
          <Route exact path="/react/:postId" render={() => <Community hasPost postId={window.location.pathname.split('/')[2]} path={'react'}/>}/>
      </div>
    );
  }
}

export default App


