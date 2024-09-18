# Modul 1 - HTML dan CSS

### 🦴  HTML

#### 1. Heading & Paragraph

Heading adalah sebuah format text pada HTML yang dapat berfungsi sebagai **judul** atau **subjudul**. Heading terdiri dari 6 tipe dari `<h1>` hingga `<h6>` di mana `<h1>` merupakan heading paling besar dan `<h6>` adalah heading paling kecil. Besar kecilnya heading menentukan seberapa penting informasi dari text tersebut.
```html
<h1>Ini adalah Heading 1</h1> 
<h2>Ini adalah Heading 2</h2> 
<h3>Ini adalah Heading 3</h3> 
<h4>Ini adalah Heading 4</h4> 
<h5>Ini adalah Heading 5</h5> 
<h6>Ini adalah Heading 6</h6>
```
![heading](foto/HTML/heading.png)

Paragraph adalah sebuah format text pada HTML yang dapat berfungsi sebagai **isi** atau **content**. Paragraph ditulis dengan menggunakan tag `<p>`.
```html
<p>Ini adalah paragraf pertama. Paragraf digunakan untuk menulis teks dalam bentuk blok yang rapi di HTML.</p> 
<p>Ini adalah paragraf kedua. Setiap paragraf baru dimulai dengan tag yang terpisah.</p>
```
![paragraph](foto/HTML/paragraph.png)

#### 2. Formatting

Text dalam HTML dapat diatur tampilannya dengan menggunakan beberapa tag formatting berikut:
- **Bold** `<b>` untuk **menebalkan** suatu text.
- **Italic** `<i>` untuk membuat suatu text menjadi **miring**.
- **Underline** `<u>` untuk memberikan **garis bawah** pada suatu text.
- **Strikethrough** `<s>` untuk memberikan **coretan** pada suatu text.
- **Superscript** `<sup>` untuk membuat suatu teks menjadi **di atas**. Biasanya digunakan untuk penulisan eksponen atau footnote.
- **Subscript** `<sub>` untuk membuat suatu teks menjadi **di bawah**. Biasanya digunakan untuk penulisan indeks atau formula kimia.
- **Mark** `<mark>` untuk memberikan **highlight** pada suatu text.
- **Small** `<small>` untuk **mengecilkan** suatu text.
```html
<p>Teks ini menggunakan <b>bold (tebal)</b>.</p>
<p>Teks ini menggunakan <i>italic (miring)</i>.</p>
<p>Teks ini menggunakan <u>underline (garis bawah)</u>.</p>
<p>Teks ini menggunakan <s>strikethrough (coretan)</s>.</p>
<p>Teks ini menggunakan <sup>superscript</sup>.</p>
<p>Teks ini menggunakan<sub>subscript</sub>.</p>
<p>Teks ini menggunakan <mark>highlight</mark>.</p>
<p>Teks ini menggunakan <small>small (teks kecil)</small>.</p>
```
![formatting](foto/HTML/formatting.png)

#### 3. Anchor

Anchor `<a>` adalah sebuah element HTML yang dapat digunakan untuk **memberikan tautan/link** menuju email, file, hingga halaman website lain. Element ini dapat membungkus element-element lain seperti heading, paragraph, image, dsb.
```html
<a href="https://www.w3schools.com/html/">Belajar HTML lewat sini</a>
```
![anchor](foto/HTML/anchor.png)

#### 4. Image

Jika ingin menambahkan gambar pada web HTML, dapat menggunakan element `<img>`. Tag ini memiliki dua atribut penting yaitu `src` dan `alt`. Atribut `src` digunakan untuk **menentukan sumber lokasi atau URL dari gambar** yang ingin ditampilkan dan `alt` yang digunakan untuk **memberikan keterangan alternatif** jika gambar tidak dapat ditampilkan. Selain itu, terdapat atribut `height` dan `width` yang berfungsi untuk mengatur **panjang** dan **lebar** dari gambar yang ditampilkan.
```html
<img src="nogambar.jpg" alt="Ini adalah fungsi 'alt'"/>
<img src="https://picsum.photos/300/200" alt="Gambar random" width="300" height="200" />
```
![image](foto/HTML/img.png)

#### 5. Tabel

HTML memiliki element tersendiri untuk membuat tabel. Tag yang diperlukan untuk membuat tabel adalah sebagai berikut:

- **Table** `<table>` setiap membuat tabel baru harus dibungkus dengan tag `<table>`.
- **Table Row** `<tr>` setiap ingin membuat **row/baris** baru harus dibungkus dengan tag `<tr>`.
- **Table Header** `<th>` umumnya digunakan **header/judul** dari kolom tabel. Tag `<th>` akan membuat isi dari barisnya menjadi di **tengah (centered)** dan **tebal**.
- **Table Data** `<td>` umumnya digunakan untuk membuat **content/isi** dari tabel.
```html
<table>  
	<tr>  
		<th>Nama</th>  
		<th>Umur/th>  
		<th>Pekerjaan</th>  
	</tr>  
	<tr>  
		<td>Irfan</td>  
		<td>25</td>  
		<td>Tidak Bekerja</td>  
	</tr>  
	<tr>  
		<td>Hendro</td>  
		<td>26</td>  
		<td>Full Stack Developer</td>  
	</tr>  
</table>
```
![tabel](foto/HTML/table.png)

#### 6. List

HTML memiliki element tersendiri untuk membuat list. List dalam HTML terbagi menjadi 2 yaitu:

1. **Ordered List**
Ordered List memberikan list yang **memiliki urutan**. Umumnya digunakan untuk memberikan list yang perlu dirunut seperti langkah-langkah. Untuk membuat ordered list harus membungkus tag `<li>` di dalam `<ol>`.
```html
<ol>
	<li>Langkah pertama</li>
	<li>Langkah Kedua</li>
	<li>Langkah ketiga</li>
</ol>
```
![ol](foto/HTML/ol.png)

2. Unordered List
Unordered List memberikan list yang **tidak memiliki urutan**. Umumnya digunakan untuk memberikan list yang tidak perlu dirunut. Untuk membuat unordered list harus membungkus tag `<li>` di dalam `<ul>`.
```html
<ul>
	<li>Item 1</li>
	<li>Item 2</li>
	<li>Item 3</li>
</ul>
```
![ul](foto/HTML/ul.png)

#### 7. Forms

Forms HTML adalah sebuah format untuk melakukan **user input**. Hasil user input tersebut umumnya digunakan untuk diproses ke server atau database. Pembuatan form HTML umumnya menggunakan pembungkus `<form>`. Di dalamnya akan terdapat beberapa element lain yang berfungsi sebagai user inputnya. Element-element tersebut adalah sebagai berikut:

- `<input>` adalah sebuah element untuk meminta input user. Jenis input yang dimasukkan dapat berupa apapun dengan menambahkan atribut `type` di dalamnya. Terdapat banyak sekali opsi `type` pada input, contoh: `radio`, `text`, `time`, `date`, `number`, `password`, dsb.
- `<label>` berfungsi untuk menambahkan `<label>` pada element forms lain. Untuk menghubungkan `<label>` dan element forms lain, harus dihubungkan dengan menggunakan `id` yang sama pada kedua element.
- `<select>` berfungsi untuk memberikan pilihan berupa dropdown. Untuk memberikan option/pilihan dropdown-nya, dapat menggunakan tag `<option>`.
- `<textarea>` adalah element untuk meminta input user berupa text multi-line.
- `<button>` berfungsi untuk menambahkan element berupa button/tombol. `<button>` memiliki beberapa `type` juga seperti `button`, `submit`, atau `reset`.
- `<fieldset>` digunakan untuk membungkus dan mengelompokkan suatu data form yang berelasi. Untuk memberikan keterangan pada `<fieldset>`, dapat menggunakan element `<legend>`.
```html
<form  action="/submit"  method="POST">
	<fieldset>
		<legend>Informasi Pribadi</legend>

		<label  for="name">Nama Lengkap:</label>
		<input  type="text"  id="name"  name="name"  placeholder="Masukkan nama lengkap"  required>

		<br>
		<label  for="email">Email:</label>
		<input  type="email"  id="email"  name="email"  placeholder="Masukkan email"  required>

		<br>
		<label  for="password">Password:</label>
		<input  type="password"  id="password"  name="password"  placeholder="Masukkan password"  required>

		<br>
	<button  type="submit">Kirim</button>
</fieldset>

</form>
```
![forms](foto/HTML/forms.png)

#### 8. Div

Div `<div>` adalah sebuah element **blok** yang umumnya digunakan sebagai sebuah **container** atau **memisahkan antar section** pada suatu halaman website. `<div>` digunakan untuk membungkus dan mengelompokkan beberapa element lain untuk menciptakan suatu section tersendiri.
```html
<div> 
	<h2>Judul Artikel pertama</h2> 
	<p>Ini adalah paragraf pertama dari artikel pertama.</p> 
</div>

<div> 
	<h2>Judul Artikel kedua</h2> 
	<p>Ini adalah paragraf pertama dari artikel kedua.</p> 
</div>
```
![div](foto/HTML/div.png)

#### 9. Span

Span `<span>` adalah sebuah element **inline** yang umumnya digunakan untuk **membungkus bagian kecil** dari teks atau elemen lainnya agar bisa diberikan gaya atau manipulasi tertentu. Perbedannya dengan `<div>` adalah `<span>` tidak mengambil baris baru.
```html
<p>Teks ini memiliki <span style="color: red;">warna merah</span> hanya di bagian tertentu.</p>
```
![span](foto/HTML/span.png)

#### 10. Class

`class` adalah atribut yang digunakan untuk **menetapkan satu atau lebih kelas** pada element HTML. Elemen HTML bisa memiliki lebih dari satu `class`. Ini memungkinkan untuk melakukan pengelompokkan element-element yang berbeda di halaman menjadi satu atau lebih kelompok yang sama, sehingga element-element tersebut bisa memiliki gaya atau perilaku yang sama. `class` biasanya digunakan untuk menerapkan gaya yang sama atau manipulasi JavaScript pada beberapa element yang berbeda.
```html
<div class="box"></div>
<div class="box special"></div>
<p class="text">Ini adalah paragraf dengan kelas 'text'.</p>
```
![class](foto/HTML/class.png)

#### 11. Id 

`id` adalah atribut yang digunakan untuk memberikan **identitas unik** pada elemen HTML. Setiap elemen di halaman harus memiliki `id` yang unik, artinya tidak boleh ada `id` yang sama untuk beberapa elemen yang berbeda. Atribut `id` biasanya digunakan ketika Anda ingin menargetkan satu elemen tertentu untuk diberikan gaya atau manipulasi JavaScript.
```html
<div id="header">Ini adalah header</div> 
<p id="intro">Ini adalah paragraf pertama yang memiliki id 'intro'.</p>
```
![id](foto/HTML/id.png)

#### Perbedaan Class dan Id 
| Perbedaan      | `class`                                                                                                              | `id`                                                            |
| -------------- | -------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Kegunaan**   | Digunakan untuk mengelompokkan beberapa elemen yang berbeda sehingga dapat diberikan gaya atau manipulasi yang sama. | Digunakan untuk memberikan identitas unik pada elemen tertentu. |
| **Penggunaan** | Dapat digunakan pada beberapa elemen yang berbeda.                                                                   | Hanya dapat digunakan sekali per halaman.                       |
| **Jumlah**     | Satu elemen bisa memiliki lebih dari satu kelas.                                                                     | Setiap elemen hanya bisa memiliki satu id unik.                 |
| **JavaScript** | Dapat digunakan untuk menargetkan beberapa elemen sekaligus.                                                         | Biasanya digunakan untuk menargetkan satu elemen saja.          |

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