Tentu, berikut adalah README untuk kode visualisasi algoritma Dijkstra yang Anda berikan.

# Visualisasi Algoritma Pathfinding Dijkstra

## 🗺️ Gambaran Umum

Proyek ini adalah sebuah program interaktif berbasis Python menggunakan pustaka **Pygame** untuk memvisualisasikan cara kerja **algoritma Dijkstra**. Pengguna dapat secara visual memahami bagaimana algoritma ini menemukan jalur terpendek antara dua titik pada grid, menghindari rintangan (barrier).

## 🎮 Cara Menggunakan

1.  **Instalasi**: Pastikan Anda telah menginstal pustaka **Pygame**. Jika belum, jalankan perintah berikut di terminal Anda:

    ```bash
    pip install pygame
    ```

2.  **Menjalankan Program**: Jalankan skrip Python:

    ```bash
    python nama_file_anda.py
    ```

3.  **Interaksi**:

      - **Klik Kiri**:
          - **Pertama kali**: Klik pada grid untuk menetapkan **titik awal (Start)** (berwarna **kuning**).
          - **Kedua kali**: Klik di tempat lain untuk menetapkan **titik akhir (End)** (berwarna **ungu**).
          - **Selanjutnya**: Klik untuk membuat **dinding/rintangan (Barrier)** (berwarna **hitam**).
      - **Klik Kanan**: Menghapus titik awal, akhir, atau rintangan yang telah Anda buat, mengembalikannya ke kondisi kosong (berwarna **putih**).
      - **Tombol Spasi**: Setelah Anda menetapkan titik awal dan akhir, tekan tombol **spasi** untuk memulai visualisasi algoritma Dijkstra.
      - **Tombol 'C'**: Menekan tombol **'C'** akan mereset seluruh grid, memungkinkan Anda untuk membuat skenario baru.

## 🎨 Palet Warna

Program ini menggunakan skema warna untuk membantu visualisasi:

  - 🟥 **Merah**: Node yang sudah dipertimbangkan (sudah dikunjungi) oleh algoritma.
  - 🟩 **Hijau**: Node yang berada dalam antrian untuk dikunjungi, tetapi belum diproses.
  - 🟦 **Biru**: Node yang merupakan bagian dari jalur terpendek yang ditemukan.
  - 🟨 **Kuning**: Titik awal.
  - 🟫 **Hitam**: Rintangan yang tidak bisa dilewati.
  - ⬜ **Putih**: Area kosong yang dapat dilewati.
  - 🟪 **Ungu**: Titik akhir.
  - **Abu-abu**: Garis-garis yang membentuk grid.

## ⚙️ Cara Kerja Kode

  - **`Node` Class**: Merepresentasikan setiap kotak pada grid. Objek `Node` menyimpan posisi baris/kolom, warna, dan daftar tetangga (neighbors) yang dapat dikunjungi.
  - **`dijkstra` Function**: Implementasi inti dari algoritma Dijkstra.
      - Menggunakan **Priority Queue** (`PriorityQueue` dari pustaka `queue`) untuk selalu memilih node yang memiliki jarak terpendek dari titik awal.
      - Secara iteratif memproses node, memperbarui jarak ke tetangga, dan mewarnai node untuk memvisualisasikan statusnya (hijau untuk "open", merah untuk "closed").
      - Jika titik akhir ditemukan, fungsi `reconstruct_path` dipanggil untuk menandai jalur terpendek dengan warna biru.
  - **`main` Function**: Mengelola loop utama program, menangani input pengguna (klik mouse dan keyboard), serta memperbarui visualisasi pada layar.
