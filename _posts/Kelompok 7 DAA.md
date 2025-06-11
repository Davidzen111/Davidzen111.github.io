---
title: "Breadth-First Search (BFS) – Penelusuran Graf Berbasis Antrian"
date: 2025-06-11
categories: [Algoritma, Struktur Data]
tags: [bfs, graph traversal, antrian, algoritma]
layout: post
author: Davidzen
pin: true
---

## 🔍Breadth-First Search (BFS)?

**Breadth-First Search (BFS)** adalah algoritma untuk menelusuri graf atau pohon secara **berlapis (level-order)**, dimulai dari simpul awal dan menjelajahi tetangga-tetangganya terlebih dahulu sebelum berlanjut ke simpul yang lebih jauh.

Ilustrasi sederhananya: seperti mencari ruangan di gedung bertingkat dari lantai 1 ke atas secara menyeluruh. BFS menjelajahi ke seluruh arah mendatar dulu, baru melangkah ke tingkat selanjutnya.

---

## 🧠 Konsep Dasar

- BFS menggunakan **struktur data queue (antrian)**
- **Level-order traversal**: semua simpul di satu level dikunjungi sebelum naik ke level berikutnya
- Menjamin **jalur terpendek ditemukan** pada graf tak berbobot

---

## 🪜 Langkah-langkah BFS

1. Tentukan simpul awal (start node)
2. Masukkan simpul ke dalam antrian (`enqueue`)
3. Selama antrian tidak kosong:
   - Ambil simpul dari depan antrian (`dequeue`)
   - Tandai sebagai dikunjungi
   - Untuk semua tetangga yang belum dikunjungi:
     - Tandai sebagai dikunjungi
     - Masukkan ke antrian

---

## 📊 Contoh Visualisasi

Graf:

```
     S
   /   \
  A     B
 / \   / \
C   D E   F
         / \
        H   G
```

Urutan antrian (QUEUE):  
S → A, B → C, D, E, F → H, G

---

## 💡 Aplikasi Nyata BFS

1. **Labirin & Game (Pac-Man)**  
   Mencari jalan keluar terpendek

2. **Media Sosial (Facebook, LinkedIn)**  
   Menemukan teman dari koneksi level 1, 2, dst

3. **Jaringan Komputer**  
   Memetakan koneksi antar perangkat

4. **Transportasi & Navigasi (Google Maps)**  
   Menemukan rute dengan simpul/berhenti paling sedikit (jika bobot jalur sama)

---

## ✅ Kelebihan

- **Lengkap (complete)**: selalu menemukan solusi jika ada
- **Optimal**: menemukan solusi dengan jalur terpendek (jumlah edge terkecil)
- **Sederhana dan terstruktur**

## ⚠️ Kekurangan

- Membutuhkan memori lebih besar dibanding DFS, terutama untuk graf besar
- Kurang efisien jika solusi berada di kedalaman besar

---

## 🧾 Kesimpulan

- BFS adalah teknik traversal graf **berbasis antrian** yang efektif dan deterministik.
- Cocok digunakan untuk **pencarian jalur terpendek pada graf tak berbobot**.
- BFS banyak digunakan di berbagai bidang seperti **game, pencarian sosial, sistem navigasi**, dan banyak lagi.

---


> BFS adalah langkah awal terbaik untuk menyisir solusi secara menyeluruh sebelum melangkah lebih dalam.
