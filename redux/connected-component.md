# Connecting a component to the store

1. Import connect to allow react and redux to talk to eachother.
2. Add props as an arguement to your app function so that we can have access to it (functional component)
3. Getting the application state from the store state, mapping the piece that you asked for as props to this component
4. Use the connect() function to connect to the store via the mapStateToProps function, and then use the result of that to re-render App.

```js
import React from "react";
import "./App.css";
//Step 1
import { connect } from "react-redux";
import { addTodo } from "./store/todos/actions";

//Step 2
function App(props) {
  function handleClick(e) {
    props.dispatch(addTodo("do the dishes"));
  }
  console.log("props in app", props);
  return (
    <div className="App">
      <p>Hello world</p>
      <button onClick={handleClick}>Click me</button>
    </div>
  );
}

//Step 3

function mapStateToProps(state) {
  return {
    todos: state.todos
  };
}

//Step 4
export default connect(mapStateToProps)(App);
```
