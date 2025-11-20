parent:: [[expression]]


React-এ “**expression slot**” বলতে আসলে বোঝানো হয়—  
**JSX এর মধ্যে যেসব জায়গায় তুমি `{}` এর ভিতরে JavaScript expression লিখতে পারো।**

---

# ✅ **React Expression Slot — সহজ ভাষায়**

React-এ যখন তুমি JSX লেখো:

```jsx
<div>{ something }</div>
```

এই `{ something }` অংশটাই expression slot।

এখানে তুমি **variable, function call, ternary, map, condition—সব লিখতে পারো**, যতক্ষণ সেটা expression।

Example:

```jsx
<div>{ name }</div>
<div>{ count + 1 }</div>
<div>{ isLoggedIn ? "Welcome" : "Login" }</div>
<div>{ items.map(i => <p>{i}</p>) }</div>
```

এক বাক্যে:

> **JSX-এর সেই জায়গা যেখানে `{ }` এর মধ্যে JavaScript expression লেখা যায় = expression slot।**

---

# ❌ Expression slot এ কী লেখা যায় না?

### 👉 **Statements allowed না**

যেমন:

```jsx
{ if (true) { } }      // ❌ ভুল  
{ for (let i=0; i<5) } // ❌ ভুল  
```

কারণ `{}` এর ভিতরে শুধু **expression** থাকবে, statement না।

---

# ✔ Expression slot এ কী লেখা যায়?

### 1) Variable

```jsx
{username}
```

### 2) Function call

```jsx
{getUserName()}
```

### 3) Ternary

```jsx
{isDark ? "Dark Mode" : "Light Mode"}
```

### 4) Map loop

```jsx
{users.map(u => <div>{u.name}</div>)}
```

### 5) Template literal

```jsx
{`Hello ${name}`}
```

### 6) Logical AND

```jsx
{isAdmin && <AdminPanel />}
```

সবই expressions।

---

# 🎯 **React expression slot কে slot কেন বলা হয়?**

কারণ JSX এ `{}` একটা “hole” এর মতো জায়গা,  
যেখানে তুমি JavaScript inject করতে পারো।

Like:

```
<div> JSX এখানে 
      { এই জায়গা = JS expression slot }
</div>
```

---

# ⭐ Bonus: React এর আরেক ধরনের slot = **children**

Example:

```jsx
<MyCard>
   <h1>Hello</h1>
</MyCard>
```

এটা children-based slot system, Vue-এর slot-এর মতো।

---

# 🔥 Final Summary

### **React Expression Slot = JSX এর `{}` যেখানে expression লেখা যায়।**

✔ expression allowed  
❌ statement allowed না

এটা React-এর অন্যতম core concept।

---
