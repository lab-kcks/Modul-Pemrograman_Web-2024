# Modul 3 - Express JS dan MongoD

## TypeScrypt

### Apa itu TypeScript🤔???

TypeScript adalah sebuah bahasa pemrograman yang dikembangkan di atas JavaScript. Dibandingkan dengan JavaScript, TypeScript menyediakan fitur tambahan yang mempermudah pengembangan aplikasi berskala besar. Dengan menggunakan TypeScript, tools pemrograman menjadi lebih baik, membantu dalam meningkatkan produktivitas, dan meminimalkan kesalahan dalam kode.

TypeScript adalah superset dari JavaScript, yang berarti semua kode JavaScript yang valid juga valid di TypeScript. Namun, TypeScript menambahkan syntax tambahan seperti tipe data (type) dan antarmuka (interface) untuk memberikan lebih banyak struktur pada kode.

Proses Transpilasi kode yang ditulis dalam TypeScript tidak dijalankan langsung di browser atau Node.js. Kode ini perlu dikonversi menjadi JavaScript terlebih dahulu melalui proses yang disebut transpiling. Setelah dikonversi, hasilnya adalah kode JavaScript biasa yang dapat dijalankan di:

- **Browser**: Untuk membuat aplikasi web.
- **Node.js atau Deno**: Untuk membuat aplikasi server atau utilitas lain berbasis JavaScript.

### Mengapa Typescript😣???

- **Integrasi IDE**: TypeScript dirancang untuk bekerja lebih baik dengan Code Editor seperti VS Code, sehingga memudahkan dalam penulisan dan perbaikan kode.
- **Error Checking**: Salah satu keuntungan utama TypeScript adalah kemampuannya untuk menangkap kesalahan langsung saat penulisan kode, sehingga bug dapat diperbaiki sebelum program dijalankan.
- **Scalable**: TypeScript sangat berguna dalam proyek berskala besar karena adanya tipe data yang lebih jelas, sehingga memudahkan pengembang dalam memahami dan menjaga kualitas kode.

### Javascript😁 vs Typescript😎

| **Fitur**             | **TypeScript**                                                                  | **JavaScript**                                        |
| --------------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------- |
| **Tipe Data**         | Menyediakan tipe statis                                                         | Bertipe dinamis                                       |
| **Perkakas**          | Dilengkapi dengan IDE dan editor kode                                           | Tools bawaan terbatas                                 |
| **Sintaks**           | Mirip dengan JavaScript, dengan fitur tambahan                                  | Syntax Standar JavaScript standar                     |
| **Kompatibilitas**    | Kompatibel dengan JavaScript                                                    | Tidak dapat menjalankan TypeScript di file JavaScript |
| **Debugging**         | Penulisan kode yang lebih kuat/strict dapat membantu mengidentifikasi kesalahan | Memerlukan lebih banyak debugging dan pengujian       |
| **Tingkat Kesulitan** | Membutuhkan waktu untuk mempelajari fitur tambahan                              | Sintaks JavaScript standar lebih familier             |
| **Tipe Bahasa**       | Object-oriented                                                                 | Prototype-based language                              |

1. Deklarasi Variabel dengan Tipe Data

- **JavaScript**: Tidak menggunakan tipe data statis.
- **TypeScript**: Mendukung tipe data statis dengan anotasi tipe.

```javascript
// JavaScript
let name = "John"; // Tipe data ditentukan saat runtime

// TypeScript
let name: string = "John"; // Tipe data string secara eksplisit
```

2. Fungsi dengan Tipe Parameter dan Return

- JavaScript: Tidak menentukan tipe data pada parameter dan nilai yang dikembalikan.
- TypeScript: Memungkinkan penentuan tipe data untuk parameter dan nilai kembalian.

```javascript
// JavaScript
function add(a, b) {
	return a + b;
}

// TypeScript
function add(a: number, b: number): number {
	return a + b;
}
```

3. Interface

- JavaScript: Tidak memiliki konsep interface.
- TypeScript: Menyediakan interface untuk mendefinisikan bentuk objek secara eksplisit.

```javascript
// TypeScript
interface Person {
	name: string;
	age: number;
}

let person: Person = {
	name: "Alice",
	age: 25,
};
```

4. Class dan Properti

- JavaScript: Tidak menggunakan tipe pada properti dan tidak mendukung akses modifier secara langsung.
- TypeScript: Mendukung tipe pada properti dan akses modifier seperti public, private, dan protected.

```typescript
// JavaScript
class Animal {
	constructor(name) {
		this.name = name;
	}
}

let dog = new Animal("Dog");

// TypeScript
class Animal {
	private name: string;

	constructor(name: string) {
		this.name = name;
	}

	public getName(): string {
		return this.name;
	}
}

let dog: Animal = new Animal("Dog");
```

1. Type Assertions

- JavaScript: Tidak mendukung asersi tipe.
- TypeScript: Mendukung asersi tipe untuk menyatakan bahwa suatu nilai adalah tipe tertentu.

```typescript
// TypeScript
let value: any = "Hello World";
let lengthOfString: number = (value as string).length; // Asersi bahwa value adalah string
```

6. Optional Parameters

- JavaScript: Tidak memiliki fitur parameter opsional secara eksplisit.
- TypeScript: Mendukung parameter opsional dengan tanda ?.

```typescript
// TypeScript
function greet(name: string, age?: number): string {
	return age ? `Hello ${name}, age ${age}` : `Hello ${name}`;
}
```

7. Generics

- JavaScript: Tidak mendukung generics.
- TypeScript: Mendukung penggunaan generics untuk fungsi atau class yang fleksibel dengan berbagai tipe.

```typescript
// TypeScript
function identity<T>(arg: T): T {
	return arg;
}

let output = identity<string>("Hello"); // Menggunakan generics dengan tipe string
```

## Mongo Client🤖

### Konfigurasi Mongo Client di ExpressJS😶‍🌫️

Untuk membuat sebuah koneksi dari ExpressJS ke MongoDB, harus dibuat sebuah file environment `.env`. Di dalamnya dapat diisi dengan variabel yang berfungsi untuk melakukan define koneksi database maupun port. Berikut contoh file `.env` dengan menggunakan MongoDB Atlas.

```.env
ATLAS_URI=mongodb+srv://<username>:<password>@sandbox.jadwj.mongodb.net/myFirstDatabase?retryWrites=
PORT=5050
```

Untuk melakukan import dari `.env`, buat sebuah file baru `loadEnvironment.mjs` untuk load dari `.env` yang sudah dibuat sebelumnya. Berikut isinya.

```javascript
import dotenv from "dotenv";
dotenv.config();
```

Kemudian di bagian `index.mjs` dapat ditambahkan import dari `loadEnvironment.mjs`.

```javascript
// Load environment variables
import "./loadEnvironment.mjs";
```

Selanjutnya, buat `server/db/conn.mjs` dan ganti kontennya dengan kode berikut. Kode ini akan membuat objek basis data global yang dapat digunakan kembali oleh komponen server lainnya.

```javascript
import { MongoClient } from "mongodb";
const connectionString = process.env.ATLAS_URI || "";
const client = new MongoClient(connectionString);
let conn;
try {
	conn = await client.connect();
} catch (e) {
	console.error(e);
}
let db = conn.db("sample_training");
export default db;
```

Kode ini menggunakan string koneksi yang disediakan dalam file .env dan membuat klien baru. Setelah klien di-define, kode ini akan mencoba membuat koneksi baru ke database. Database kemudian diekspor jika koneksi berhasil. Hal ini memberikan sebuah interface yang seragam yang dapat digunakan kembali di semua modul yang akan dibuat selanjutnya.

### Membuat CRUD API dengan ExpressJS dan MongoClient🤠

Dalam contoh ini, akan digunakan contoh yang disediakan dari https://github.com/mongodb-developer/mongodb-express-rest-api-example. Folder structure servernya adalah sebagai berikut.

```
server
    ├── .env
    ├── db
    │   └── conn.mjs
    ├── index.mjs
    ├── loadEnvironment.mjs
    └── routes
        └── posts.mjs
```

- `.env`: File konfigurasi yang menyimpan detail string koneksi MongoDB.
- `db/conn.mjs`: Mengekspos koneksi global ke basis database.
- `index.mjs`: Titik masuk utama untuk server Express.
- `loadEnvironment.mjs`: Memuat variabel environment (.env).
- `routes/posts.mjs`: Mengekspos endpoint REST API dan menjalankan logika bisnisnya.

1. Handling HTTP request
   Pada contoh ini, segala route dari server akan menuju file `server/routes/posts.mjs`. Kemudian semua modul dari request yang data dari enpoint `/posts` akan dilakukan berdasarkan pemenaggilan code berikut pada `index.mjs`.

```javascript
// Load the /posts routes
app.use("/posts", posts);
```

2. Read route
   Fungsi ini mengembalikan daftar 50 artikel pada koleksi posts melalui permintaan **GET** di route `/posts`.

```javascript
// Get 50 posts
router.get("/", async (req, res) => {
	let collection = await db.collection("posts");
	let results = await collection.find({}).limit(50).toArray();
	res.send(results).status(200);
});
```

- Menetapkan collection untuk mengakses koleksi posts.
- Menggunakan `find()` untuk mencari dokumen dan `limit()` untuk membatasi hasil.
- Mengirim hasil ke klien dengan `res.send()` dan menambahkan kode status `200`.

3. Read Route (Advance)
   Fungsi ini mengembalikan tiga artikel terbaru menggunakan pipeline agregasi.

```javascript
// Get new posts
router.get("/latest", async (req, res) => {
	let collection = await db.collection("posts");
	let results = await collection
		.aggregate([
			{ $project: { author: 1, title: 1, tags: 1, date: 1 } },
			{ $sort: { date: -1 } },
			{ $limit: 3 },
		])
		.toArray();
	res.send(results).status(200);
});
```

Pipeline agregasi digunakan untuk memproyeksikan fields yang diperlukan, mengurutkan berdasarkan tanggal, dan membatasi hasil ke tiga artikel terbaru.

4. Read Single Result
   Mengembalikan artikel berdasarkan parameter `id` dengan menggunakan route dinamis.

```javascript
// Get by id
router.get("/:id", async (req, res) => {
	let collection = await db.collection("posts");
	let query = { _id: ObjectId(req.params.id) };
	let result = await collection.findOne(query);
	if (!result) res.send("Not found").status(404);
	else res.send(result).status(200);
});
```

- Mengambil `id` sebagai parameter dari URL, mengonversinya menjadi `ObjectId`, dan mencari dokumen yang sesuai.
- Jika tidak ditemukan, mengirim status `404`.

5. Create
   Menambahkan artikel baru ke koleksi `posts` melalui metode **POST**.

```javascript
// Create new post
router.post("/", async (req, res) => {
	let collection = await db.collection("posts");
	let newDocument = req.body;
	newDocument.date = new Date();
	let result = await collection.insertOne(newDocument);
	res.send(result).status(204);
});
```

Mengambil body dari request, menambahkan tanggal sebagai timestamp, dan menyimpannya dalam koleksi menggunakan `insertOne()`.

6. Update
   Menambahkan komentar baru pada artikel dengan metode PATCH.

```javascript
// Add new comment
router.patch("/comment/:id", async (req, res) => {
	const query = { _id: ObjectId(req.params.id) };
	const updates = {
		$push: { comments: req.body },
	};
	let collection = await db.collection("posts");
	let result = await collection.updateOne(query, updates);
	res.send(result).status(200);
});
```

`updateOne()` menggunakan operator `$push` untuk menambahkan komentar ke array comments.

7. Delete
   Menghapus artikel dari koleksi `posts`.

```javascript
// Delete post by id
router.delete("/:id", async (req, res) => {
	const query = { _id: ObjectId(req.params.id) };
	const collection = db.collection("posts");
	let result = await collection.deleteOne(query);
	res.send(result).status(200);
});
```

Menggunakan `deleteOne()` dengan `id` untuk menghapus dokumen yang sesuai.

8. Testing API
   Pengujian API dapat dilakukan menggunakan Postman atau perintah curl. Contoh pengambilan artikel terbaru:

```bash
curl localhost:5050/posts/latest
```

Pastikan port sudah sesuai dengan port yang sudah di-define di environment.
<br>

- Berikut link download Postman untuk melakukan testing API (sangat disarankan dan sangat membantu).
  https://www.postman.com/downloads/

- Untuk dokumentasi yang lebih jelas bisa langsung menuju ke website resmi MongoDB berikut.
  https://www.mongodb.com/resources/languages/express-mongodb-rest-api-tutorial
