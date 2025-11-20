React-এ **state** হলো **একটা object বা variable যা component-এর data বা UI কে represent করে এবং সময়ের সাথে পরিবর্তন হতে পারে।**

React-এর component যখন render হয়, state হলো সেই component-এর **mutable data storage**, যা **UI কে dynamic বানায়**।

---

# 🔹 Key Points about React State

1. **Component-specific**

   * প্রতিটি component নিজের state রাখে।
   * এক component-এর state অন্য component-এর state কে affect করে না।

2. **Dynamic / Mutable**

   * State পরিবর্তন করলে UI স্বয়ংক্রিয়ভাবে re-render হয়।
   * Example: button click → counter value বাড়ানো → UI update।

3. **Managed by React**

   * State কখনো direct mutate করা উচিত নয়।
   * সবসময় `useState` (functional component) বা `this.setState` (class component) ব্যবহার করে পরিবর্তন করতে হবে।

4. **Triggers re-render**

   * State change → React আবার render function চালায় → নতুন UI দেখায়।

---

# 🔹 Example: Counter Component

```jsx
import React, { useState } from "react";

function Counter() {
  // useState দিয়ে state declare করা
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1); // state update
  };

  return (
    <div>
      <h1>Count: {count}</h1> {/* state use করা */}
      <button onClick={increment}>Increment</button>
    </div>
  );
}
```

**Step-by-step ব্যাখ্যা:**

1. `useState(0)` → নতুন state variable তৈরি করে: `count`।
2. `setCount` → state update করার function।
3. Button click → `increment()` call → `setCount` state change করে।
4. React automatically render করে `<h1>` নতুন value সহ।

---

# 🔹 Important Notes

* State can be **primitive**: number, string, boolean
* State can be **object/array**: multiple values or list
* **[[direct mutation is forbidden]]**:

  ```js
  count = count + 1; // ❌
  ```

  Always use setter:

  ```js
  setCount(count + 1); // ✅
  ```

---

💡 **One-liner:**
**State = component-এর “memory” যা data save করে এবং change হলে UI automatically update করে।**

---

আপনি চাইলে আমি **state vs props** এর মধ্যে clear difference diagram আকারে দেখাতে পারি, যা React-এর basic বুঝতে খুব সাহায্য করবে।
আপনি কি সেটা চাইবেন?
