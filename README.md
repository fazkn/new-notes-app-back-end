# Notes App Back-End

## Deskripsi

Notes App Back-End adalah aplikasi RESTful API sederhana yang dibangun menggunakan **Hapi Framework**.  
Aplikasi ini digunakan untuk mengelola catatan (notes) dengan fitur **menambah, menampilkan, mengubah, dan menghapus catatan**.

Proyek ini dibuat sebagai **latihan pembelajaran** untuk memahami:

- Konsep **Hapi Plugin**
- Pemisahan **handler** dan **service**
- Pengelolaan struktur proyek back-end yang rapi dan terukur

Data catatan pada aplikasi ini masih disimpan **di dalam memori (in-memory)** menggunakan array.

---

## Fitur

- Menambahkan catatan
- Menampilkan seluruh catatan
- Menampilkan detail catatan berdasarkan ID
- Mengubah catatan
- Menghapus catatan

---

## Teknologi yang Digunakan

- **Node.js**
- **Hapi Framework**
- **nanoid** (untuk generate ID unik)

---

### Penjelasan Struktur

- **server.js**  
  Bertugas membuat, mengonfigurasi, dan menjalankan HTTP server menggunakan Hapi serta mendaftarkan plugin.

- **api/notes**  
  Merupakan Hapi Plugin untuk fitur notes.

  - `routes.js`: mendefinisikan endpoint API
  - `handler.js`: menangani request dan response
  - `index.js`: mendaftarkan route sebagai plugin

- **services/inMemory/NotesService.js**  
  Menangani logika bisnis (CRUD) catatan dan menyimpan data di memori.

---

## Data Validation

Aplikasi ini menerapkan **validasi data** menggunakan **Joi** untuk memastikan data yang dikirim oleh client sesuai dengan skema yang telah ditentukan.

Validasi dilakukan pada:

- Payload request saat menambahkan catatan
- Payload request saat memperbarui catatan

Dengan menggunakan Joi, aplikasi dapat:

- Mencegah data tidak valid masuk ke sistem
- Memberikan response error yang lebih jelas dan terstruktur kepada client
- Menjaga konsistensi data pada Notes API

Validasi ini diintegrasikan ke dalam **plugin Notes** sehingga tetap selaras dengan konsep modularisasi pada Hapi Framework.
