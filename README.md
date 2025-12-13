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
