# 🔹 **React এর useReducer কী?**

`useReducer` হলো **React hook** যা **complex state logic** handle করার জন্য ব্যবহার করা হয়।

- এটা `useState` এর মতই state manage করে, কিন্তু বড় বা nested state update করার জন্য বেশি উপযুক্ত।
    
- Redux এর **reducer concept** এর মতো কাজ করে।


---

# 🔹 **useReducer এর basic syntax**

```js
const [state, dispatch] = useReducer(reducer, initialState);
```

- `state` → current state
    
- `dispatch` → function যা action পাঠায়
    
- `reducer` → function যা state update করে
    
- `initialState` → state এর শুরু মান
    

---

# 🔹 **Reducer function structure**

```js
function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { ...state, count: state.count + 1 };
    case "decrement":
      return { ...state, count: state.count - 1 };
    default:
      return state;
  }
}
```

**কী হচ্ছে এখানে:**

- Reducer receives **old state + action**
    
- এবং **new state return করে**
    
- Direct mutation forbidden → নতুন object return করতে হবে
    

---

# 🔹 **Complete Example: Counter**

```jsx
import React, { useReducer } from "react";

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { ...state, count: state.count + 1 };
    case "decrement":
      return { ...state, count: state.count - 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <div>
      <h1>Count: {state.count}</h1>
      <button onClick={() => dispatch({ type: "increment" })}>
        Increment
      </button>
      <button onClick={() => dispatch({ type: "decrement" })}>
        Decrement
      </button>
    </div>
  );
}
```

---

# 🔹 **useReducer এর সুবিধা**

1. **Complex state management**
    
    - Nested objects বা multiple values handle করতে সহজ
        
2. **Predictable updates**
    
    - সব update centralized reducer function এ হয়
        
3. **Action-based updates**
    
    - Multiple actions handle করা সহজ
        
4. **Redux-like pattern**
    
    - বড় apps এ scalable, future-ready
        

---

# 🔹 **Quick difference: useState vs useReducer**

|useState|useReducer|
|---|---|
|ছোট/simple state|বড়/complex state|
|direct setter (`setState`)|action + reducer pattern|
|simple logic|central logic + multiple actions|
|less boilerplate|more boilerplate but predictable|

---

💡 **One-liner:**  
**`useReducer` = useState এর advanced version যেখানে state update logic centralized, predictable এবং scalable হয়।**
