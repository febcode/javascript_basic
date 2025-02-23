### **`call()`, `apply()`, and `bind()` in JavaScript**
These methods allow you to **change the `this` context** of a function and invoke it in different ways.

---

## **1️⃣ `call()` Method**
**Syntax:**
```javascript
functionName.call(thisArg, arg1, arg2, ...);
```
- Calls the function **immediately**.
- Passes arguments **individually**.

🔹 **Example:**
```javascript
const person = { name: "Alice" };

function greet(age, city) {
    console.log(`Hello, my name is ${this.name}, I am ${age} years old and live in ${city}.`);
}

greet.call(person, 25, "New York");
```
**Output:**
```
Hello, my name is Alice, I am 25 years old and live in New York.
```

---

## **2️⃣ `apply()` Method**
**Syntax:**
```javascript
functionName.apply(thisArg, [arg1, arg2, ...]);
```
- Calls the function **immediately**.
- Passes arguments as an **array**.

🔹 **Example:**
```javascript
greet.apply(person, [25, "New York"]);
```
**Output:**
```
Hello, my name is Alice, I am 25 years old and live in New York.
```
✔ `apply()` is useful when you have an array of arguments.

---

## **3️⃣ `bind()` Method**
**Syntax:**
```javascript
const newFunction = functionName.bind(thisArg, arg1, arg2, ...);
```
- **Does not call** the function immediately.
- Returns a **new function** with the `this` value set.

🔹 **Example:**
```javascript
const boundGreet = greet.bind(person, 25, "New York");
boundGreet(); // Calls the function later
```
**Output:**
```
Hello, my name is Alice, I am 25 years old and live in New York.
```
✔ Useful when you want to set `this` but call the function later.

---

## **Comparison Table**
| Method  | Calls Function? | Arguments Format | Returns New Function? |
|---------|---------------|------------------|----------------------|
| `call()`  | ✅ Yes | Individual values | ❌ No |
| `apply()` | ✅ Yes | Array of values  | ❌ No |
| `bind()`  | ❌ No  | Individual values | ✅ Yes |

---

## **Use Cases**
✅ **call()** – When you want to invoke a function immediately with a custom `this`  
✅ **apply()** – When passing arguments as an array (useful for `Math.max.apply(null, [1, 2, 3])`)  
✅ **bind()** – When you need to save a function with a predefined `this` for later use  

