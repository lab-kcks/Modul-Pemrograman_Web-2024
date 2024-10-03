# Modul 2 - Java Script

## 1. JavaScript Basics

JavaScript adalah bahasa pemrograman yang digunakan untuk menambahkan interaksi dan logika ke halaman web.
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
   <script src="./script.js"></script>
   ```

### 1.2. Sintaks Dasar

- **Variabel**: Menggunakan `let`, dan `const`. (kenapa nggada `var` mas?, karena rekom masa sekarang better `let` dan `const` yeah)

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

### 1.6. Menggunakan Local Storage

**Local Storage** adalah penyimpanan di browser yang memungkinkan klean menyimpan data secara permanen di sisi klien (hingga dihapus secara manual oleh pengguna).

#### 1.6.1. Menyimpan Data ke Local Storage

Untuk menyimpan data ke local storage, gunakan metode `localStorage.setItem()`. Metode ini menerima dua parameter: kunci (key) dan nilai (value).

Contoh menyimpan data:

```javascript
localStorage.setItem("username", "Alice");

const user = {
  name: "Alice",
  age: 25,
};
localStorage.setItem("user", JSON.stringify(user));
```

#### 1.6.2. Mengambil Data dari Local Storage

Untuk mengambil data yang telah disimpan di local storage, gunakan metode `localStorage.getItem()`. Jika datanya adalah string yang di-encode sebagai JSON, gunakan `JSON.parse()` untuk mengubahnya kembali ke objek JavaScript.

Contoh mengambil data:

```javascript
const username = localStorage.getItem("username");
console.log(username); // Output: Alice

const user = JSON.parse(localStorage.getItem("user"));
console.log(user.name); // Output: Alice
```

#### 1.6.3. Menghapus Data dari Local Storage

Gunakan `localStorage.removeItem()` untuk menghapus item tertentu dari local storage.

Contoh menghapus data:

```javascript
localStorage.removeItem("username");
```

Untuk menghapus semua data yang tersimpan di local storage, gunakan `localStorage.clear()`:

```javascript
localStorage.clear();
```

## 2. Intermediate JavaScript

Setelah memahami dasar-dasar, klean akan melanjutkan ke konsep yang lebih kompleks.

### 2.1. Arrays

- **Mendefinisikan Array**:

  ```javascript
  let fruits = [🍏, 🍉, 🍊];
  ```

- **Manipulasi Array**:

  ```javascript
  fruits.push(🍇); // Menambah elemen
  fruits.pop(); // Menghapus elemen terakhir
  ```

- **Menambah dan Menghapus Elemen di Awal Array**:

  ```javascript
  fruits.unshift(🍊); // Menambah elemen di awal array
  fruits.shift(); // Menghapus elemen pertama
  ```

- **Menggabungkan Dua Array**:

  ```javascript
  const moreFruits = [🍏, 🍉,];
  const allFruits = fruits.concat(moreFruits);
  ```

- **Mengakses Elemen dengan `indexOf` dan `includes`**:

  ```javascript
  const index = fruits.indexOf(🍏); // Mengembalikan index dari '🍏'
  const hasApple = fruits.includes(🍏); // Mengecek apakah array memiliki '🍏'
  ```

- **Menggunakan `slice` untuk Mengambil Subset**:

  ```javascript
  const someFruits = fruits.slice(1, 3); // Mengambil elemen dari index 1 hingga sebelum 3
  ```

- **Menggunakan `splice` untuk Menambah/Menghapus Elemen di Posisi Tertentu**:

  ```javascript
  fruits.splice(2, 0, 🍏); // Menambah 🍏 di index 2 tanpa menghapus elemen
  fruits.splice(1, 1); // Menghapus 1 elemen mulai dari index 1
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
  let work = {
    name: "Lorem Ipsum",
    position: "Software Engineer",
    greet: () => {
      return `Hello, ${work.name}`;
    },
  };
  ```

- **Akses Properti**:

  ```javascript
  console.log(person.name); // Mengakses dengan titik
  console.log(person["age"]); // Mengakses dengan bracket
  console.log(work.name); // Mengakses dengan titik
  console.log(work["position"]); // Mengakses dengan bracket
  console.log(work.greet()); // Mengakses dengan bracket
  ```

### 2.3. DOM Manipulation

#### 2.3.1. DOM Document

`document` adalah objek utama yang mewakili seluruh halaman web. Klean bisa mengakses elemen, membuat elemen baru, dan melakukan manipulasi DOM lainnya menggunakan `document`.

Contoh mengakses elemen:

```javascript
const title = document.getElementById("title");
const paragraphs = document.querySelectorAll("p");
```

#### 2.3.2. DOM Elements

Elemen DOM bisa diakses dan dimanipulasi untuk mengubah konten, gaya, atribut, dll.

Contoh mengubah konten dan gaya:

```javascript
title.textContent = "New Title";
title.style.color = "blue";
```

#### 2.3.3. DOM HTML

`innerHTML` digunakan untuk mengubah atau menyisipkan konten HTML dalam elemen. (Awas kena **XSS** puhh)

Contoh:

```javascript
const content = document.getElementById("content");
content.innerHTML =
  "<h1>Judul Baru</h1><p>Paragraf diubah dengan innerHTML.</p>";
```

#### 2.3.4. DOM Forms

Untuk mengakses dan memanipulasi elemen form seperti `input`, `textarea`, dll., klean bisa menggunakan properti `value`.

Contoh menangani form:

```javascript
const form = document.getElementById("myForm");
form.addEventListener("submit", (event) => {
  event.preventDefault();
  const inputValue = document.getElementById("inputField").value;
  alert(`Input value: ${inputValue}`);
});
```

#### 2.3.5. DOM CSS

Untuk mengubah gaya elemen, klean bisa menggunakan properti `style`.

Contoh:

```javascript
title.style.fontSize = "24px";
title.style.backgroundColor = "yellow";
```

#### 2.3.6. DOM Animations

Klean bisa menambahkan animasi menggunakan CSS atau JavaScript. Dengan JavaScript, properti `style` bisa digunakan untuk mengubah transformasi dan transisi.

Contoh:

```javascript
const box = document.getElementById("box");
box.style.transition = "transform 0.5s";
box.style.transform = "rotate(45deg)";
```

#### 2.3.7. DOM Events

Event adalah tindakan yang dilakukan oleh pengguna atau browser seperti klik, scroll, dan input. Klean bisa menggunakan event seperti `click`, `input`, atau `submit`.

Contoh event `click` yang digunakan di HTML nantinya:

```javascript
function changeText(id) {
  id.innerHTML = "Huft!";
}
```

#### 2.3.8. DOM Event Listener

`addEventListener` digunakan untuk menambahkan event listener ke elemen DOM.

Contoh menangani klik tombol:

```javascript
button.addEventListener("click", () => {
  console.log("Button was clicked!");
});
```

#### 2.3.9. DOM Nodes

Semua elemen di DOM adalah node, dan klean bisa memanipulasinya dengan metode seperti `appendChild`, `removeChild`, atau `replaceChild`.

Contoh menghapus elemen:

```javascript
const parentElement = document.getElementById("parent");
const childElement = document.getElementById("child");
parentElement.removeChild(childElement);
```

#### 2.3.10. DOM Collections & Node List

**HTMLCollection** dan **NodeList** adalah koleksi elemen DOM. Klean bisa melakukan iterasi di atas koleksi tersebut seperti pada array, meskipun tidak sepenuhnya sama.

Contoh dengan `NodeList`:

```javascript
const paragraphs = document.querySelectorAll("p");
paragraphs.forEach((p) => {
  p.style.color = "green";
});
```

Contoh dengan `HTMLCollection`:

```javascript
const divs = document.getElementsByTagName("div");
for (let i = 0; i < divs.length; i++) {
  divs[i].style.backgroundColor = "yellow";
}
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

- **Callback**:

  ```javascript
  function fetchData(callback) {
    setTimeout(() => {
      const data = {
        name: "Alice",
        age: 24,
        posistion: "Software Engineer",
      };
      callback(data);
    }, 2000);
  }

  function handleData(data) {
    console.log(data);
  }

  fetchData(handleData);
  ```

Fungsi `fetchData` menerima fungsi callback (`handleData`) sebagai argumen, yang kemudian dipanggil setelah `setTimeout` selesai dan `data` siap digunakan.

### 3.2. Error Handling

- **Try-Catch**:

  ```javascript
  try {
    // kode yang mungkin terjadi error
  } catch (error) {
    console.error("Error occurred:", error);
  }
  ```

### 3.3. Closures

- **Contoh Closures**:

  ```javascript
  function pesanKamuKeDia() {
    const chatKamu = "Kamu dah tidur belum";
    return function pesanYangDiaSukai() {
      const chatYangDiaSukai = "Haii, sudah makan belum?";
      console.log({ chatYangDiaBaca: chatYangDiaSukai });
    };
  }

  const hasil = pesanKamuKeDia();
  hasil(); // Output: "Haii, sudah makan belum?"
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

### 4.2. Event Delegation

- **Menggunakan Event Delegation**:

  ```javascript
  document.querySelector("#parent").addEventListener("click", (event) => {
    if (event.target.matches("button")) {
      console.log("Button clicked:", event.target.textContent);
    }
  });
  ```

### 4.3. Best Practices

- **Gunakan `let` dan `const` daripada `var`** untuk mendeklarasikan variabel
- **Tulis kode yang bersih dan terorganisir** dengan mengikuti prinsip KISS
- **Gunakan linting tools** seperti ESLint untuk menjaga konsistensi kode
