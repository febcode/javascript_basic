### **Observables vs Promises in JavaScript**  

Both **Observables** and **Promises** handle asynchronous operations, but they have key differences in how they work.

---

## **1️⃣ Promise**
A **Promise** represents a **single** asynchronous operation that either **resolves** (success) or **rejects** (failure).

### **Example:**
```javascript
const myPromise = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Promise resolved!");
    }, 2000);
});

myPromise.then(result => console.log(result));
```
⏳ **After 2 seconds:**
```
Promise resolved!
```
🔹 **Key Features of Promises:**
- Executes **once** and **cannot be canceled**.
- Returns **a single value** (or error).
- Uses `.then()`, `.catch()`, and `.finally()`.
- **Example Use Case:** Fetching data from an API.

---

## **2️⃣ Observable (RxJS)**
An **Observable** is a **stream** of multiple values over time. It can emit multiple values and be **canceled**.

### **Example (Using RxJS Library):**
```javascript
import { Observable } from 'rxjs';

const myObservable = new Observable(observer => {
    observer.next("First value");
    observer.next("Second value");
    setTimeout(() => observer.next("Third value"), 2000);
});

myObservable.subscribe(value => console.log(value));
```
⏳ **Immediate Output:**
```
First value
Second value
```
⏳ **After 2 seconds:**
```
Third value
```

🔹 **Key Features of Observables:**
- Can emit **multiple values** over time.
- Supports **cancellation** via `.unsubscribe()`.
- Uses `.subscribe()` to handle values.
- **Example Use Case:** Handling UI events (like mouse clicks, keystrokes).

---

## **3️⃣ Comparison Table**
| Feature        | Promise | Observable |
|---------------|---------|------------|
| **Emits**      | Single value | Multiple values |
| **Execution**  | Runs immediately | Runs when subscribed |
| **Can be canceled?** | ❌ No | ✅ Yes (`unsubscribe()`) |
| **Lazy Execution?** | ❌ No | ✅ Yes (executes only on subscription) |
| **Chaining** | ✅ `.then()` | ✅ `.pipe()` |
| **Best For** | API calls | UI events, WebSockets |

---

## **4️⃣ When to Use What?**
✅ **Use Promises when** you need a **one-time** async operation (e.g., fetching data from an API).  
✅ **Use Observables when** you need a **stream** of data (e.g., listening to user inputs, WebSockets, real-time updates).  

