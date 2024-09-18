# Modul 1 - HTML dan CSS
### 🎨 **CSS**

#### **1. Cara Menyisipkan CSS**

Ada tiga cara untuk menyisipkan CSS ke dalam dokumen HTML:

- **Inline CSS**: CSS diterapkan langsung ke elemen HTML menggunakan atribut `style`.
  
  ```html
  <p style="color: red;">Ini adalah paragraf berwarna merah.</p>
  ```

- **Internal CSS**: CSS diletakkan di dalam tag `<style>` pada bagian `<head>` dokumen HTML.
  
  ```html
  <head>
    <style>
      p {
        color: blue;
      }
    </style>
  </head>
  ```

- **Eksternal CSS**: CSS disimpan dalam file terpisah dan dihubungkan ke HTML menggunakan tag `<link>`.
  
  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <link rel="stylesheet" href="mystyle.css">
  </head>
  <body>

  <h1>Pemweb seru gasi</h1>
  <p>seru banget kak</p>

  </body>
  </html>

  ```

---

#### **2. Selektor (Menghubungkan Class & Id)**

Selektor CSS digunakan untuk menargetkan elemen HTML tertentu buat dikasih *style*. Dua selektor utama adalah **class** dan **id**.

- **Class Selector**: Menargetkan elemen dengan kelas tertentu.
  
  ```html
  <div class="kotak">Kotak 1</div>
  <div class="kotak">Kotak 2</div>
  
  /* CSS */
  .kotak {
    background-color: lightblue;
    padding: 10px;
  }
  ```

- **ID Selector**: Menargetkan elemen unik dengan ID tertentu.
  
  ```html
  <div id="kotakID">Kotak Utama</div>
  
  /* CSS */
  #kotakID {
    background-color: green;
    padding: 20px;
  }
  ```

---

#### **3. Box Model (Margin, Padding, Border, Konten)**

**Box model** dalam CSS terdiri dari **konten**, **padding**, **border**, dan **margin**. Memahami model ini penting untuk tata letak halaman.

- **Konten**: Isi dari elemen (teks, gambar, dll.).
- **Padding**: Ruang antara konten dan border.
- **Border**: Garis yang mengelilingi padding dan konten.
- **Margin**: Ruang di luar border, antara elemen lain.

Contoh:
```html
<div class="kotak">Pemweb</div>

<style>
  .kotak {
    width: 200px;
    padding: 10px;
    border: 2px solid black;
    margin: 20px;
  }
</style>
```
![contoh box model](foto/box.png)

---

#### **4. Tinggi & Lebar (Height & Width)**

Kalian bisa menetapkan tinggi dan lebar elemen menggunakan properti `height` dan `width`.

Contoh:
```html
<div class="kotak">kotak ini ada tinggi sama lebar</div>

<style>
  .kotak {
    width: 300px;
    height: 150px;
    background-color: lightcoral;
  }
</style>
```
![contoh penggunaan height and width](foto/tinggilebar.png)
---

#### **5. Warna (Color)**

Properti `color` mengubah warna teks, sedangkan `background-color` mengubah warna latar belakang.

Contoh:
```html
<p class="teks-berwarna">woh berwarna cik</p>

<style>
  .teks-berwarna {
    color: #3498db; /* Warna teks */
    background-color: #f1c40f; /* Warna latar belakang */
  }
</style>
```
![warna background dan font](foto/warna.png)
---

#### **6. Teks & Font**

kalian bisa menata teks menggunakan properti seperti `font-size`, `font-family`, `text-align`, `line-height`, dan lainnya.

Contoh:
```html
<p class="text">Pemweb seru ya ges ya</p>

<style>
  .teks-styling {
    font-size: 20px;
    font-family: 'Arial', sans-serif;
    text-align: center;
    line-height: 1.5;
  }
</style>
```
![contoh font](foto/font.png)

#### **11. Flex**

Flexbox adalah metode tata letak CSS yang memudahkan distribusi ruang dan penjajaran elemen dalam kontainer dengan cara yang lebih efisien dibandingkan metode tata letak tradisional. Flexbox dirancang untuk mengatasi masalah tata letak yang kompleks dengan cara yang lebih mudah, memungkinkan elemen dalam kontainer untuk menyesuaikan diri secara otomatis berdasarkan ruang yang tersedia.

Konsep Utama Flexbox:

1) Kontainer Flex (Flex Container): Elemen yang diatur menggunakan Flexbox dengan `display: flex;` atau `display: inline-flex;`. Semua anak elemen dari kontainer ini akan menjadi item flex.

2) Item Flex (Flex Items): Elemen di dalam kontainer flex yang secara otomatis menyesuaikan ukuran dan posisinya berdasarkan properti Flexbox yang diterapkan pada kontainer.

3) Sumbu Utama (Main Axis): Arah utama di mana item flex ditempatkan dalam kontainer. Arah ini bisa horizontal (default) atau vertikal, tergantung pada nilai flex-direction.

4) Sumbu Silang (Cross Axis): Arah yang tegak lurus terhadap sumbu utama. Ini digunakan untuk mengatur penempatan item flex di sepanjang sumbu yang berbeda dari sumbu utama.

5) Properti Kontainer Flex:
    - `flex-direction`: Mengatur arah sumbu utama (misalnya, baris horizontal atau kolom vertikal).

    - `flex-wrap`: Menentukan apakah item flex harus dibungkus ke baris atau kolom berikutnya jika ruang tidak cukup.

    - `justify-content`: Mengatur distribusi ruang sepanjang sumbu utama (misalnya, penempatan di tengah, spasi antara, atau spasi di sekeliling).

    - `align-items`: Menentukan bagaimana item flex diatur di sepanjang sumbu silang (misalnya, pusatkan, atau perataan di awal atau akhir).

    - `align-content`: Mengatur ruang di antara baris flex saat kontainer memiliki banyak baris (misalnya, spasi antara, atau meratakan di pusat).

6) Properti Item Flex:
    - `flex-grow`: Mengatur seberapa banyak item flex akan tumbuh relatif terhadap item lainnya jika ada ruang ekstra.

    - `flex-shrink`: Mengatur seberapa banyak item flex akan menyusut relatif terhadap item lainnya jika ruang terbatas.

    - `flex-basis`: Menentukan ukuran awal item flex sebelum `flex-grow` atau `flex-shrink` diterapkan.



Contoh:
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

```css
<style>
    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f0f0f0;
    }

    .item {
      background-color: lightcoral;
      color: white;
      padding: 20px;
      margin: 10px;
      border-radius: 5px;
    }
</style>
```

#### **12. Grid**

CSS Grid Layout adalah sistem tata letak dua dimensi yang memungkinkan untuk membuat desain yang kompleks dan responsif dengan mudah. Grid Layout membagi area halaman menjadi baris dan kolom, sehingga bisa menempatkan elemen di dalam grid dengan cara yang lebih fleksibel dibandingkan metode lain.

Konsep Utama Grid Layout:

1) Kontainer Grid (Grid Container): Elemen yang diatur menggunakan Grid Layout dengan `display: grid;` atau `display: inline-grid;`. Elemen anak dari kontainer ini akan menjadi item grid.

2) Item Grid (Grid Items): Elemen di dalam kontainer grid yang akan diatur dalam baris dan kolom berdasarkan aturan grid.

3) Baris dan Kolom (Grid Rows and Columns): Grid Layout membagi kontainer menjadi baris dan kolom. Dapat mengatur ukuran baris dan kolom serta mengatur penempatan item di dalam grid.

4) Properti Kontainer Grid:
    - `grid-template-rows`: Menentukan ukuran baris grid. Menggunakan satuan seperti px, %, atau fr (fractional unit).

    - `grid-template-columns`: Menentukan ukuran kolom grid

    - `grid-template-areas`: Mengatur area grid dengan mendefinisikan nama area untuk memudahkan penempatan item grid

    - `grid-gap`: Menentukan jarak antara baris dan kolom grid

5) Properti Item Grid:
    - `grid-column`: Menentukan berapa banyak kolom item grid akan mencakup

    - `grid-row`: Menentukan berapa banyak baris item grid akan mencakup.

    - `grid-area`: Mengatur posisi item grid berdasarkan nama area atau posisi grid.

Contoh:

```html
  <div class="grid-container">
    <div class="header">Header</div>
    <div class="sidebar">Sidebar</div>
    <div class="main">Main Content</div>
    <div class="footer">Footer</div>
  </div>
```

```css
  <style>
    .grid-container {
      display: grid;
      grid-template-rows: 100px auto 100px;
      grid-template-columns: 1fr 3fr;
      grid-gap: 10px;
    }

    .header {
      grid-column: 1 / 3;
      background-color: lightblue;
      padding: 20px;
    }

    .sidebar {
      background-color: lightcoral;
      padding: 20px;
    }

    .main {
      background-color: lightgreen;
      padding: 20px;
    }

    .footer {
      grid-column: 1 / 3;
      background-color: lightgoldenrodyellow;
      padding: 20px;
    }
  </style>
```

#### **13. Responsive**

Responsive Layout adalah pendekatan desain web yang memastikan tampilan dan fungsionalitas halaman web tetap baik di berbagai ukuran layar, mulai dari desktop besar hingga perangkat mobile kecil. Dengan responsive layout, desain halaman web dapat menyesuaikan diri dengan lebar viewport perangkat yang berbeda.

Konsep utama responsive layout:

  1) **Media Queries**: Media queries adalah fitur CSS untuk menerapkan gaya khusus berdasarkan ukuran layar perangkat. Media queries digunakan untuk menentukan aturan CSS yang hanya diterapkan jika kondisi tertentu terpenuhi.

  Contoh penggunaan media queries:
  ```css
  /* Style default */
  body {
  font-size: 16px;
  }

  /* Style dengan lebar max 600px */
  @media (max-width: 600px) {
    body {
      font-size: 14px;
    }
  }
  ```

  2) **Unit Responsif**: Menggunakan unit ukuran responsif seperti em, rem, %, dan vh/vw (viewport height/width) memungkinkan elemen untuk menyesuaikan ukuran dan posisi mereka sesuai dengan ukuran viewport

  Contoh penggunaan unit responsif:
  ```css
  .container {
  width: 80%;
  padding: 2rem;
  }
  ```

  3) **Responsive Grid & Flexbox** :  Menggunakan Grid Layout dan Flexbox dapat mempermudah penciptaan tata letak responsif dengan fleksibilitas tinggi. Dengan metode ini, arah baris/kolom dapat diubah, elemen dapat disembunyikan atau ditampilkan, dan ukuran item grid/flex dapat disesuaikan berdasarkan ukuran layar.

  Contoh responsive flexbox:
  ```css
  .container {
  display: flex;
  flex-wrap: wrap;
  }

  .item {
  flex: 1 1 200px; /* Item akan tumbuh dan menyusut dengan ukuran minimum 200px */
  }

  ```

  Contoh responsive gridbox: 
  ```css
  .grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  }

  /* Style untuk device dengan lebar layar max 768px */
  @media (max-width: 768px) {
    .grid-container {
    grid-template-columns: repeat(2, 1fr);
    }
  }

  /* Style untuk device dengan lebar layar max 480px */
  @media (max-width: 480px) {
    .grid-container {
      grid-template-columns: 1fr;
    }
  }
  ```

  5) **Responsive Image**: Menggunakan gambar responsif yang dapat menyesuaikan ukuran dan resolusi mereka sesuai dengan perangkat yang digunakan. Dapat menggunakan atribut `srcset` dan `sizes` pada elemen `<img>`

  Contoh penggunaan `srcset` dan `sizes`:
  ```css
  <img src="image-600.jpg" 
     srcset="image-400.jpg 400w, image-600.jpg 600w, image-800.jpg 800w"
     sizes="(max-width: 600px) 100vw, 50vw" 
     alt="Contoh gambar responsif">
  ```

Contoh responsive layout:
```html
  <div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
  </div>
```
```css
  <style>
    .container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .item {
      background-color: lightcoral;
      padding: 20px;
    }

    @media (max-width: 768px) {
      .container {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (max-width: 480px) {
      .container {
        grid-template-columns: 1fr;
      }
    }
  </style>
```







