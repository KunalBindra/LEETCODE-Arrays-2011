# LEETCODE-Arrays-2011
---

### **Code:**

```java
class Solution {
    public int finalValueAfterOperations(String[] operations) {
        int ans = 0;
        for (String s : operations) {
            ans += s.charAt(1) == '+' ? 1 : -1;
        }
        return ans;
    }
}
```

---

### **Understanding the problem**

This code is for the LeetCode problem **"Final Value of Variable After Performing Operations"**.

Each string in the array `operations` is one of these:

* `"++X"`
* `"X++"`
* `"--X"`
* `"X--"`

Each operation **increments or decrements** the variable `ans` by 1.

---

### **Key logic**

```java
s.charAt(1)
```

👉 gets the **middle character** of the string.

For each operation:

* if the middle character is `'+'`, it means increment.
* else (i.e. `'-'`), it means decrement.

So:

```java
ans += s.charAt(1) == '+' ? 1 : -1;
```

is a shorthand for:

```java
if (s.charAt(1) == '+') ans += 1;
else ans -= 1;
```

---

### **Dry Run Example**

#### Input:

```java
operations = {"--X", "X++", "++X"}
```

#### Step-by-step:

| Step | Operation | s.charAt(1) | Condition (`'+'?`) | Change to ans | ans after operation |
| ---- | --------- | ----------- | ------------------ | ------------- | ------------------- |
| 1    | "--X"     | '-'         | false              | -1            | 0 → -1              |
| 2    | "X++"     | '+'         | true               | +1            | -1 → 0              |
| 3    | "++X"     | '+'         | true               | +1            | 0 → 1               |

✅ **Final Output:** `1`

---

### **Summary**

* The code loops through each operation.
* Checks the middle character.
* Adds +1 for `'+'`, subtracts 1 for `'-'`.
* Returns the final value.

---
