
# ES6 Classes

Classes in ES6 are the fundamental building blocks for creating objects in JavaScript and serve as blueprints for object-oriented programming (OOP). Using classes helps in structuring and organizing code, enabling inheritance and encapsulation, which are key OOP principles.

---

## Creating a Class in ES6

You can define a class using the `class` keyword. A class can contain:
1. **Properties** - Attributes associated with the class.
2. **Methods** - Functions that define the behavior of the class.

### Example:

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  introduce() {
    console.log(`Hi, my name is ${this.name} and I am ${this.age} years old.`);
  }

  celebrateBirthday() {
    this.age += 1;
    console.log(`Happy Birthday, ${this.name}! You are now ${this.age} years old.`);
  }
}

const person1 = new Person("Alice", 30);
person1.introduce(); // Hi, my name is Alice and I am 30 years old.
person1.celebrateBirthday(); // Happy Birthday, Alice! You are now 31 years old.

```
## Access Specifiers.  
In ES6, JavaScript does not have strict public, private, and protected keywords like some other languages. However, as of the ES2022 update, private fields are supported by prefixing the property with #.  
### Example: Private Properties
```javascript  
class BankAccount {
  #balance; // Private field

  constructor(initialBalance) {
    this.#balance = initialBalance;
  }

  deposit(amount) {
    this.#balance += amount;
    console.log(`Deposited ${amount}. New balance: ${this.#balance}`);
  }

  getBalance() {
    return this.#balance;
  }
}

const account = new BankAccount(100);
account.deposit(50); // Deposited 50. New balance: 150
console.log(account.getBalance()); // 150
```  
## Inheritance.  
Inheritance allows you to create a class based on another class, which enables reusability of code. In ES6, inheritance is achieved using the extends keyword.  
### Example: Using Inheritance.  
```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Dog extends Animal {
  speak() {
    console.log(`${this.name} barks.`);
  }
}

const dog = new Dog("Rex");
dog.speak(); // Rex barks.


```   
### static Methods  
Static methods belong to the class itself rather than to instances of the class. They are often used for utility functions.  
```javascript  
class MathHelper {
  static add(a, b) {
    return a + b;
  }
}

console.log(MathHelper.add(5, 3)); // 8
 ```
 ### Getters and Setters.  
 Getters and setters allow you to control how properties are accessed and modified.
 ```javascript
 class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  get area() {
    return this.width * this.height;
  }

  set dimensions(dimensions) {
    this.width = dimensions.width;
    this.height = dimensions.height;
  }
}

const rect = new Rectangle(10, 5);
console.log(rect.area); // 50
rect.dimensions = { width: 4, height: 8 };
console.log(rect.area); // 32
```
##  BY: 
### Lucy Wambui
### Florida Gatwiri
### Nina Namalwa