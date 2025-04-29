these are like placeholders sa function

so ganito

```
def multiply(parameter):
	print(parameter)


multiply('This is the argument') 

the output of this will be the argument which is 'This is the argument'

```
![[Pasted image 20250429093857.png]]

---


kwargs:
### **What is `**kwargs`?**

- `**kwargs` means: "**catch any number of _named_ arguments**" (key-value pairs).
    
- **kwargs** turns the extra arguments into a **dictionary** inside the function.
    
- You can **loop** through them, **access** them by key, **print** them, etc.
    

---

**Think of it like this:**

> The function is holding a basket.  
> You throw **named things** into the basket (like `name="Alice"`).  
> Inside the function, it catches them all in a **dictionary** (`kwargs`)!

---

### **Super simple breakdown:**

|What you do|What happens|
|---|---|
|Pass `name="Alice"` to the function|It becomes `"name": "Alice"` inside `kwargs`|
|Pass `age=30`|It becomes `"age": 30` inside `kwargs`|
|Pass `city="New York"`|It becomes `"city": "New York"` inside `kwargs`|

**No, you don't always need a `for` loop** when using `**kwargs`.  
It **depends** on what you want to do.

Here’s the easy way to think about it:

|If you want to...|You...|
|---|---|
|Use **all** the key-value pairs|Use a `for` loop|
|Use **only one** specific key|Access it directly like a dictionary|

---

### Example 1:

✅ If you want to **show all** values → yes, you need a loop:

python

`def show_info(**kwargs):     for key, value in kwargs.items():         print(key, value)  show_info(name="Bob", age=25)`

---

### Example 2:

✅ If you **just want one thing** → no loop needed:

python

CopyEdit

`def greet(**kwargs):     print("Hello", kwargs["name"])  greet(name="Bob", age=25) # Only uses "name"`

---

🔵 **In short:**

- **Many values** → use `for` loop.
    
- **One specific value** → no need for a loop, just use `kwargs["key"]`.
```
def test(**kwargs):

    print('hello', kwargs['age'])

test(name = 'tite', age = 3)
```

pag gagamitan mo naman ng for loop para sa dictionary:

```
def test(**kwargs):
    for key, value in kwargs.items():
        print(f'hello {key}, pogi {value} ')

  

test(name = 'tite', age = 3)
```

- `key` ➔ `"name"` → the **label** 
- `value` ➔ `"tite"` → the **actual content**
![[Pasted image 20250429101121.png]]
pwede rin `*args and **args lang

`*args = tuple
**kwargs = dictionary


![[Pasted image 20250429151506.png]]