### **What is `"use strict"` in JavaScript?**
**Strict mode** is a way to enforce stricter parsing and error handling in JavaScript. It helps catch common mistakes and makes debugging easier.
You can enable it by adding:

```javascript
"use strict";
```
at the beginning of a script or function.

---

### **How to Enable Strict Mode?**
1. **For the entire script:**
   ```javascript
   "use strict";
   console.log("Strict mode is enabled!");
   ```
   - This applies strict mode to the whole file.

2. **For a specific function:**
   ```javascript
   function myFunction() {
       "use strict";
       let x = 10;
       console.log(x);
   }
   myFunction();
   ```

---

### **Benefits of Using Strict Mode**
✔ Prevents accidental global variables  
✔ Throws errors for unsafe actions  
✔ Makes debugging easier  
✔ Helps JavaScript engines optimize performance  

---

### **Errors Caught by Strict Mode**
1. **Accidental Global Variables**
   ```javascript
   "use strict";
   x = 10; // ❌ Uncaught ReferenceError: x is not defined
   ```

2. **Assigning to Read-Only Properties**
   ```javascript
   "use strict";
   Object.defineProperty(this, "PI", { value: 3.14, writable: false });
   PI = 3.1415; // ❌ TypeError: Cannot assign to read only property 'PI'
   ```

3. **Deleting Variables or Functions**
   ```javascript
   "use strict";
   let a = 10;
   delete a; // ❌ SyntaxError: Delete of an unqualified identifier is not allowed
   ```

4. **Duplicate Function Parameters**
   ```javascript
   "use strict";
   function add(a, a) { // ❌ SyntaxError: Duplicate parameter name not allowed in strict mode
       return a + a;
   }
   ```

5. **Using Reserved Keywords (future-proofing)**
   ```javascript
   "use strict";
   let public = 5; // ❌ SyntaxError: Unexpected strict mode reserved word
   ```

---

### **When Should You Use Strict Mode?**
✅ Always use it for new JavaScript projects  
✅ When writing modular or large-scale applications  
✅ When debugging older code to catch hidden bugs  

---
