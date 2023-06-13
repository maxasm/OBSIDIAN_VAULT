To use `react-js` you need to add the following code in the `main.jsx` file

```js
import React from "react"
import ReactDOM from "react-dom/client"

// create the root element
const root = ReactDOM.createRoot(document.getElementById("root"));
// render in the root element
root.render(<App/>);
```

You can wrap the `<App/>` component using the `<React.StrictMode/>` component go get better checks while running the code.

*Note that in React JS you can only return a single component. If you have multiple components you can wrap them together using a `</>` empty tag to avoid introducing a new element such as a `div`

*Using an empty tag can be useful when printing out a list

```jsx
<> 
{items.map((item, index) => ( <p key={index}>{item}</p> ))} 
</>
```

Depending on the compiler and bundling tools you are using, you can import certain non-code resources such as images and css files. To do so, using `vite`

```js
import "./style.css"
import imgUrl from './img.png'
```

When creating a Component in its own file, you can use the following syntax to export it.

```jsx
function Component (){
	// code
}

export default Component;
```

## className and id

In `jsx` you use `className` instead of `class` . `id` remains the same.

```jsx
<div className="the_class_name" id="the_id"></div>
```

## Inlcuding Javascript

If you want to include some Javascript expression in your `jsx` you can use `{}`

```jsx
<div>{javascript_expression}</div>
```

## Conditional rendering

Conditional rendering lets you render an element based on a particular condition.

```jsx
let render = true;
let component;

if (render) {
	component = <div></div>
} else {
	component = <h1></h1>
}

/** You can also use the ? conditional opetor **/
component = render ? <div></div> : <h1></h1>
```

## Rendering Lists

When rendering a list in Javscript, you will want to use one of the following options
- `for of` loop
- `array.map` function
- `array.filter` function

- The `map` function is used to transform an array by applying a specified operation to each element and creating a new array with the results. It takes in a callback function as an argument and returns a new array of the same length as the original array. Here's how it works:
```jsx
array = [1,2,3,4,5];

array.map((index, value, array) => new_value)
```

- The `filter` function is used to create a new array that only contains elements from the original array that satisfy a certain condition. It also takes in a callback function as an argument.

```jsx
array = [1,2,3,4,5];

array.filter((index,value,array) => expression_if_true_filter_value_at_index_of_array)
```

- The `for...of` loop is used to iterate over iterable objects, such as arrays, strings, maps, sets, etc. It allows you to access the values directly without worrying about the object's properties or indices. The syntax for a "for...of" loop is as follows

```jsx
for (let value of iterable) {
  // code to be executed
}
```


## Events

Handling events in React is easy, all you have to do is create an event handler function then attach it to the react component. 

The following are some of the common React JS events.

- `onClick`: Triggered when an element is clicked.
- `onChange`: Fired when the value of an input, select, or textarea changes.
- `onSubmit`: Fired when a form is submitted.
- `onMouseOver`: Triggered when the mouse pointer enters the element.
- `onMouseOut`: Fired when the mouse pointer leaves the element.
- `onFocus`: Fired when an element receives focus.
- `onBlur`: Triggered when an element loses focus.
- `onKeyDown`: Fired when a key is pressed down.
- `onKeyUp`: Triggered when a key is released.
- `onKeyPress`: Fired when a key is pressed and released.
- `onTouchStart`: Triggered when a touch event starts.
- `onTouchMove`: Fired when a touch event moves.
- `onTouchEnd`: Triggered when a touch event ends.
- `onLoad`: Fired when an image or other media has finished loading.
- `onScroll`: Triggered when an element is scrolled.

To handle an event such as that of a button click:

```jsx
functon handleClick() {
	/** code to handle the button click event **/
}
<button onClick={handleClick}>Click Me</button>
```

## Props

Props (short for properties) are a fundamental concept in React that allow you to pass data from a parent component to its child components. They enable communication and data sharing between components in a hierarchical manner. Props are read-only and cannot be modified by the child components.

## Hooks

React Hooks are functions that allow you to use state and other React features in functional components without the need for class components. They were introduced in React 16.8 as a way to simplify the development process and make it easier to manage state and side effects in functional components.

There are several built-in hooks provided by React, such as `useState`, `useEffect`, `useContext`, and more. Additionally, you can create your own custom hooks to encapsulate reusable logic.

Here are a few commonly used React hooks:

1. useState:
   The `useState` hook allows you to add state to functional components. It returns an array with two elements: the current state value and a function to update that state value.

2. useEffect:
   The `useEffect` hook is used to perform side effects in functional components. It runs after the component has rendered and can be used to fetch data, set up subscriptions, or modify the DOM. It takes a callback function as its first argument and can optionally include a dependency array to control when the effect should be run.

3. useContext:
   The `useContext` hook allows you to access the value of a React context within a functional component. It takes a context object created by the `createContext` function and returns its current value.

4. useRef:
   The `useRef` hook returns a mutable ref object that persists across component re-renders. It can be used to store mutable values, access DOM elements, or maintain any other value that needs to persist between renders.

5. useMemo:
   The `useMemo` hook is used to memoize expensive computations within a functional component. It takes a function and a dependency array and returns a memoized value. The value is only recomputed if any of the dependencies have changed.

6. useCallback:
   The `useCallback` hook is similar to `useMemo` but is specifically used for memoizing callback functions. It returns a memoized version of the callback that only changes if any of the dependencies have changed.

These are just a few examples of the hooks available in React. Each hook serves a specific purpose and helps manage different aspects of functional components, such as state, side effects, context, and performance optimizations.

By leveraging hooks, you can write more concise, readable, and reusable code in functional components, making React development more efficient and straightforward.

### useState

```jsx
import React, {useState} from "react"
const App = ()=> {
    const [count, updateCount] = useState(0);
    function handleClick() {
        updateCount(count + 1);
    }
    return (
        <div className="container">
            <h1 className="counter_text">{count}</h1>
            <button onClick={handleClick} className="btn">+1</button>
        </div>
    )
}
export default App;
```

### useEffect

```jsx
const MyComponent = () => {
  useEffect(() => {
    // Code to run after the component renders
    // This code will run on every render

    // Cleanup function (optional)
    return () => {
      // Code to clean up the effect
      // This code will run before the component is unmounted
    };
  });
  // ...
};

/** You can also specify dependanies **/
const MyComponent = ({ data }) => {
  useEffect(() => {
    // Code to run when the "data" prop changes
  }, [data]);
  // ...
};

```

