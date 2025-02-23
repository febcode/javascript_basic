A **closure** in JavaScript is a function that remembers the variables from its outer scope even after the outer function has finished executing. 
This allows functions to maintain state and encapsulate data.

### **Example of Closure:**
```javascript
function outerFunction(outerVariable) {
    return function innerFunction(innerVariable) {
        console.log(`Outer Variable: ${outerVariable}, Inner Variable: ${innerVariable}`);
    };
}

const newFunction = outerFunction("Hello");
newFunction("World"); // Output: Outer Variable: Hello, Inner Variable: World
```
### **How It Works:**
1. `outerFunction` is called with `"Hello"`, and it returns `innerFunction`.
2. `innerFunction` is assigned to `newFunction`.
3. When `newFunction("World")` is called, it still has access to `outerVariable` (`"Hello"`) because of closure.

---

### **Real-World Uses of Closures:**
1. **Data Encapsulation (Private Variables)**
   ```javascript
   function counter() {
       let count = 0;
       return function() {
           count++;
           console.log(count);
       };
   }

   const increment = counter();
   increment(); // 1
   increment(); // 2
   ```
   - Here, `count` is private and cannot be modified directly from outside.

2. **Maintaining State in Event Listeners**
   ```javascript
   function buttonClickHandler() {
       let count = 0;
       return function() {
           count++;
           console.log(`Button clicked ${count} times`);
       };
   }

   const button = document.getElementById("myButton");
   button.addEventListener("click", buttonClickHandler());
   ```

3. **Function Factories**
   ```javascript
   function multiplyBy(factor) {
       return function(number) {
           return number * factor;
       };
   }

   const double = multiplyBy(2);
   console.log(double(5)); // 10
   ```

---

### **Key Takeaways:**
✔ Closures allow functions to "remember" their lexical scope.  
✔ Useful for encapsulating private data.  
✔ Helps in creating function factories and maintaining state.  

Let me know if you need further clarification! 🚀
