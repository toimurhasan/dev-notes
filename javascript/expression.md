# ⭐ **Expression মানে কী? (একদম সহজ সংজ্ঞা)**

**Expression = এমন কোনো কোড, যেটা একটি single value রিটার্ন করে।**

যে কোড **একটি মান উৎপন্ন করে**, সেটাই expression।

---

# 🎯 **Expression-এর উদাহরণ (সবই value return করে)**

### 1️⃣ সরাসরি একটি value

```js
5
"Hello"
true
null
```

### 2️⃣ Variable

```js
x
username
```

কারণ variable পড়লে সে value রিটার্ন করে।

### 3️⃣ Math

```js
10 + 20
price * qty
```

### 4️⃣ Function call

```js
getUserName()
sum(2, 3)
```

Function return value দেয় → তাই expression।

### 5️⃣ Ternary

```js
isAdmin ? "Admin" : "User"
```

এটাও value return করে → তাই expression।

### 6️⃣ Array method like map

```js
items.map(i => i.name)
```

map পুরো array return করে → expression।

---

# 🎯 **Expression না—কি জিনিস? (Statement)**

Statement value দেয় না।  
Statement শুধু কিছু কাজ করে।

### ❌ Example (statement — value return করে না)

```js
if (x > 5) { }
```

```js
for (let i = 0; i < 10; i++) { }
```

```js
let x = 10;
```

```js
return;
```

Statement ≠ value return করে না  
Expression = value return করে

---

# 💡 **React JSX-এ `{ }` এর ভিতরে শুধু expression allowed**

JSX এ আমরা লিখি:

```jsx
<div>{name}</div>
<div>{count + 1}</div>
<div>{isLoggedIn ? "Welcome" : "Login"}</div>
```

কারণ এগুলো expression → value return করে।

কিন্তু নিচেরগুলো expression না, তাই React error দিবে:

```jsx
{ if (true) { } }      // ❌
{ for (let i=0; i<5; i++) } // ❌
{ while(true) {} }     // ❌
```

---

# 🧩 একদম ছোট সহজ সারাংশ

### ✔ Expression = যেকোনো কোড → একটি মান return করে

### ❌ Statement = কাজ করে, কিন্তু কোনো মান return করে না

### ✔ JSX `{}` = expression-only zone