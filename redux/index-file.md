1. Import createStore to create the store. Import combineReducers to get all of the reducers together under one reducer. Import applyMiddleware to deal with promises and other async promises.
2. Import all of the reducers for the combined reducer method.
3. Import additional middleware (i.e. logger and thunk) for creating the applyMiddleware
4. Create the rootReducer variable that will combine all of the reducers to create the shape of the store state.
5. Export the createStore method with the rootReducer and all of the middleware.

Should look something like this:

```js
//Step 1
import { createStore, combineReducers, applyMiddleware } from "redux";
//Step 2
import todosReducer from "./todos/reducer";
//Step 3
import logger from "redux-logger";
import thunk from "redux-thunk";

//Step 4
const rootReducer = combineReducers({
  todos: todosReducer
});

//Step 5
export default createStore(rootReducer, applyMiddleware(thunk, logger));
```
