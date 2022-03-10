## React Hooks: useState

A key component of a web application is the **state**. Taken directly from the beta(new) version of the ReactJS Docs:
> Think of state as the minimal set of changing data that your app needs to remember. For example, if you’re building a shopping list, you can store the items as an array in state.

Now, how do we manage state inside a React Component? So, in this tutorial we'll be talking just about that!

## Prerequisites
- Basic knowledge of ReactJS

## What are React Hooks?
First, let's start with what is a React Hook. The beta docs of ReactJS says the following:
> Functions starting with use are called Hooks. useState is a built-in Hook provided by React. You can find other built-in Hooks in the [React API reference](https://beta.reactjs.org/apis). You can also write your own Hooks by combining the existing ones.
> Hooks are more restrictive than regular functions. You can only call Hooks at the top level of your components (or other Hooks). If you want to useState in a condition or a loop, extract a new component and put it there.

So basically, if you know a little history about React, you would know that React used to be mainly comprised of something called Class-Based Components. But now, the community is starting to move to Function-Based Components. Now, React Hooks allow the functional components to have access to state and other React Features.

## Setting up the app
Create a project using the following command
```sh
npx create-react-app react-hooks-tutorial
```
Then edit your `src/App.js` to look like this
```jsx
function App() {
  return (
    <div>
      <h1>Hello, World</h1>
      <p>1</p> // this will update based on the state after this tutorial
      <button>Increase counter</button>
    </div>
  );
}

export default App;
```

## `useState` hook
Now, the way the `useState` hook is used in React is very interesting. In a conventional, class based component you'd do something like this

```js
state = {
    color: "red"
}
```
and then access it via `this.state`. But using the `useState` hook you'd do something like this
```diff
+ import { useState } from "react"
  function App() {
+   const [count, setCount] = useState(1);
    return (
```
Now the useState hook returns two things:
1. The first variable is the actual state variable. For eg. **count** in this case is **1**.
2. `setCount` is a function which you can use to change the value of the `count` state.

## Using the count state variable to show data
First, update the hardcoded value of 1 with the count variable like so
```diff
       <h1>Hello, World</h1>
-      <p>1</p>
+      <p>{count}</p>
       <button>Increase counter</button>
```

## Using setCount to update state
Now to make this work, let's make the click of the button increase the **count** variable by 1.
```diff
       <p>{count}</p>
-      <button>Increase counter</button>
+      <button onClick={() => setCount(count + 1)}>Increase counter</button>
```

### Using previous state to update state
Now, let's try something. Change the button line to the following
```diff
-     <button onClick={() => setCount(count + 1)}>Increase counter</button>
+     <button onClick={incrementCount}>Increase counter</button>
```
```diff
  const [count, setCount] = useState(1);
+ function incrementCount() {
+   setCount(count + 1);
+   setCount(count + 1);
+   setCount(count + 1);
+ }
```
Now this will give you an issue. Straight from the docs again (little modified according to our app):
>This is because calling the set function does not update the `count` state variable in the already running code. So each `setCount(count + 1)` call becomes `setCount(2)`.

To fix this issue, you can reference the previous state and then update the current state using that. So change your code like this
```diff
-  function incrementCount() {
-    setCount(count + 1);
-    setCount(count + 1);
-    setCount(count + 1);
-  }
+  function incrementCount() {
+    setCount((prevCount) => prevCount + 1);
+    setCount((prevCount) => prevCount + 1);
+    setCount((prevCount) => prevCount + 1);
+  }
```
So, you get the `prevCount` argument and increment the current state according to that and this should work!
> Note: This is obviously not a real life scenario. To increment by 3, you'd probably do something like `setCount(count+3)` but it's good to know when you can use the previous state variable as a reference.

That is it for this tutorial! You final code should look like this:
```jsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState(1);
  function incrementCount() {
    setCount((prevCount) => prevCount + 1);
    setCount((prevCount) => prevCount + 1);
    setCount((prevCount) => prevCount + 1);
  }
  return (
    <div>
      <h1>Hello, World</h1>
      <p>{count}</p>
      <button onClick={incrementCount}>Increase counter</button>
    </div>
  );
}

export default App;
```