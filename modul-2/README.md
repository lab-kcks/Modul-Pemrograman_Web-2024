# Modul 2 - Java Script

## 1. JavaScript Basics

JavaScript adalah bahasa pemrograman yang digunakan untuk menambahkan interaktivitas dan logika ke halaman web.
Dalam modul ini, klean akan mempelajari dasar-dasar JavaScript.

### 1.1. Menambahkan JavaScript ke HTML

1. **Inline JavaScript**: Menggunakan atribut seperti `onclick`.

   ```html
   <button onclick="alert('Hello World!')">Click Me</button>
   ```

2. **Internal JavaScript**: Menambahkan di dalam tag `<script>`.

   ```html
   <script>
     function greet() {
       alert("Hello, World!");
     }
   </script>
   ```

3. **External JavaScript**: Menghubungkan file eksternal.

   ```html
   <script src="script.js"></script>
   ```

### 1.2. Sintaks Dasar

- **Variabel**: Menggunakan `var`, `let`, dan `const`.

  ```javascript
  let name = "Alice"; // variabel yang dapat diubah
  const age = 25; // variabel konstan
  ```

- **Tipe Data**:

  - String
  - Number
  - Boolean
  - Null
  - Undefined
  - Object
  - Array

  ```javascript
  let str = "Hello";
  let num = 10;
  let isTrue = true;
  let nothing = null;
  ```

### 1.3. Fungsi

- **Mendefinisikan Fungsi**:

  ```javascript
  function greet(name) {
    return `Hello, ${name}!`;
  }
  ```

- **Fungsi Ekspresi**:

  ```javascript
  const greet = function (name) {
    return `Hello, ${name}!`;
  };
  ```

- **Fungsi Panah**:

  ```javascript
  const greet = (name) => `Hello, ${name}!`;
  ```

### 1.4. Pengkondisian

- **If-Else**:

  ```javascript
  let score = 85;

  if (score > 90) {
    console.log("Excellent");
  } else if (score > 70) {
    console.log("Good");
  } else {
    console.log("Needs Improvement");
  }
  ```

### 1.5. Looping

- **For Loop**:

  ```javascript
  for (let i = 0; i < 5; i++) {
    console.log(i);
  }
  ```

- **While Loop**:

  ```javascript
  let count = 0;
  while (count < 5) {
    console.log(count);
    count++;
  }
  ```

## 2. Intermediate JavaScript

Setelah memahami dasar-dasar, klean akan melanjutkan ke konsep yang lebih kompleks.

### 2.1. Arrays

- **Mendefinisikan Array**:

  ```javascript
  let fruits = ["apple", "banana", "orange"];
  ```

- **Manipulasi Array**:

  ```javascript
  fruits.push("grape"); // Menambah elemen
  fruits.pop(); // Menghapus elemen terakhir
  ```

- **Looping Melalui Array**:

  ```javascript
  fruits.forEach((fruit) => {
    console.log(fruit);
  });
  ```

### 2.2. Objects

- **Mendefinisikan Objek**:

  ```javascript
  let person = {
    name: "Alice",
    age: 25,
    greet: function () {
      return `Hello, ${this.name}`;
    },
  };
  ```

- **Akses Properti**:

  ```javascript
  console.log(person.name); // Mengakses dengan titik
  console.log(person["age"]); // Mengakses dengan bracket
  ```

### 2.3. DOM Manipulation

- **Mengakses Elemen DOM**:

  ```javascript
  const title = document.getElementById("title");
  const paragraphs = document.querySelectorAll("p");
  ```

- **Mengubah Konten dan Gaya**:

  ```javascript
  title.textContent = "New Title";
  title.style.color = "blue";
  ```

- **Menambahkan Event Listener**:

  ```javascript
  const button = document.querySelector("button");
  button.addEventListener("click", () => {
    alert("Button clicked!");
  });
  ```

## 3. Advanced JavaScript

Di bagian ini, klean akan mempelajari fitur dan konsep lanjutan dalam JavaScript.

### 3.1. Asynchronous JavaScript

- **Promises**:

  ```javascript
  const fetchData = new Promise((resolve, reject) => {
    setTimeout(() => {
      const data = { name: "Alice" };
      resolve(data);
    }, 2000);
  });

  fetchData.then((data) => console.log(data));
  ```

- **Async/Await**:

  ```javascript
  async function fetchData() {
    const response = await fetch("https://api.example.com/data");
    const data = await response.json();
    console.log(data);
  }

  fetchData();
  ```

### 3.2. Modules

- **Menggunakan Module**:

  ```javascript
  // myModule.js
  export const name = "Alice";
  export function greet() {
    return `Hello, ${name}!`;
  }

  // main.js
  import { name, greet } from "./myModule.js";
  console.log(greet());
  ```

### 3.3. Error Handling

- **Try-Catch**:

  ```javascript
  try {
    // kode yang mungkin terjadi error
  } catch (error) {
    console.error("Error occurred:", error);
  }
  ```

### 3.4. Closures

- **Contoh Closures**:

  ```javascript
  function outerFunction() {
    let outerVariable = "I'm outside!";
    return function innerFunction() {
      console.log(outerVariable);
    };
  }

  const inner = outerFunction();
  inner(); // Output: "I'm outside!"
  ```

## 4. Expert JavaScript

Pada level ini, klean akan diberikan topik-topik lanjutan dan praktik JavaScript.

### 4.1. Functional Programming

- **Higher-Order Functions**:

  ```javascript
  const add = (a) => (b) => a + b;
  const add5 = add(5);
  console.log(add5(10)); // Output: 15
  ```

- **Map, Filter, Reduce**:

  ```javascript
  const numbers = [1, 2, 3, 4, 5];
  const doubled = numbers.map((num) => num * 2);
  const evenNumbers = numbers.filter((num) => num % 2 === 0);
  const sum = numbers.reduce((acc, num) => acc + num, 0);
  ```

### 4.2. Prototypal Inheritance

- **Inheritance dengan Prototipe**:

  ```javascript
  function Animal(name) {
    this.name = name;
  }

  Animal.prototype.speak = function () {
    console.log(`${this.name} makes a noise.`);
  };

  function Dog(name) {
    Animal.call(this, name);
  }

  Dog.prototype = Object.create(Animal.prototype);
  Dog.prototype.bark = function () {
    console.log(`${this.name} barks.`);
  };

  const dog = new Dog("Buddy");
  dog.speak(); // Output: "Buddy makes a noise."
  dog.bark(); // Output: "Buddy barks."
  ```

### 4.3. Event Delegation

- **Menggunakan Event Delegation**:

  ```javascript
  document.querySelector("#parent").addEventListener("click", (event) => {
    if (event.target.matches("button")) {
      console.log("Button clicked:", event.target.textContent);
    }
  });
  ```

### 4.4. Design Patterns

- **Module Pattern**:

  ```javascript
  const Module = (function () {
    let privateVariable = "I'm private";

    return {
      getPrivate: function () {
        return privateVariable;
      },
    };
  })();

  console.log(Module.getPrivate()); // Output: "I'm private"
  ```

### 4.5. Best Practices

- **Gunakan `let` dan `const` daripada `var`** untuk mendeklarasikan variabel
- **Tulis kode yang bersih dan terorganisir** dengan mengikuti prinsip KISS
- **Gunakan linting tools** seperti ESLint untuk menjaga konsistensi kode
