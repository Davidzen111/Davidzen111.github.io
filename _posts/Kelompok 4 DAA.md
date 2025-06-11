---
title: "N-Queens Problem – Studi Backtracking dan CSP"
date: 2025-06-11
categories: [N-Queens Problem, Algoritma, Kecerdasan Buatan]
tags: [n-queens, backtracking, CSP]
pin: true
author: Davidzen
layout: post
---

## ♟️ Apa Itu N-Queens Problem?

Masalah ini mengharuskan kita menempatkan `N` ratu di papan catur `N x N`:
- Tidak ada dua ratu yang boleh berada pada **baris, kolom, atau diagonal yang sama**.
- Contoh paling terkenal: **8-Queens Problem**.

---

**N-Queens Problem** adalah permasalahan klasik dalam komputasi di mana kita harus menempatkan `N` ratu pada papan catur ukuran `N x N` sehingga tidak ada dua ratu yang saling menyerang (baik secara horizontal, vertikal, maupun diagonal). Masalah ini ideal sebagai studi kasus untuk **algoritma backtracking**, **constraint satisfaction problem (CSP)**, dan **analisis kompleksitas**. N-Queens juga memiliki analogi dalam dunia nyata seperti penjadwalan, penempatan modul elektronik, dan pengalokasian sumber daya eksklusif.

---



## 🎯 Tujuan & Relevansi

- ✅ Menemukan semua konfigurasi valid penempatan ratu.
- ✅ Meningkatkan pemahaman teknik pencarian (backtracking, DFS, heuristik, dsb).
- ✅ Studi penting dalam **CSP (Constraint Satisfaction Problem)**.
- ✅ Digunakan dalam pembelajaran **AI, optimasi, dan algoritma pencarian**.

---

## ⚙️ Kenapa Relevan?

1. **Belajar Backtracking**:  
   Mahasiswa belajar menyusun solusi bertahap dan mundur jika menemui jalan buntu.

2. **Analisis Kompleksitas**:  
   Menunjukkan perbandingan brute-force vs backtracking yang lebih efisien.

3. **Perkenalan ke CSP**:  
   Cocok untuk mengenalkan teknik seperti **forward checking** dan **backjumping**.

---

## 🔁 Algoritma Backtracking (Langkah-langkah)

1. **Decision Choice**: Pilih kolom untuk menempatkan ratu di baris berikutnya.  
2. **Constraint Check**: Apakah posisi aman? Jika ya, lanjut; jika tidak, coba opsi lain.  
3. **Recursive Exploration**: Lanjutkan proses secara rekursif.  
4. **Backtrack**: Jika tidak ada opsi yang valid, kembali ke langkah sebelumnya.  
5. **Base Case**: Jika semua ratu sudah ditempatkan, solusi ditemukan.

---

## 🌍 Aplikasi Dunia Nyata

Masalah N-Queens dapat dimodelkan dalam skenario seperti:
- **Penjadwalan tugas tanpa konflik**
- **Penempatan karyawan di ruang kerja**
- **Pengaturan modul dalam rangkaian elektronik**
- **Pengalokasian sumber daya eksklusif**

---

> Masalah N-Queens bukan sekadar teka-teki catur – ia adalah alat penting untuk belajar logika, algoritma, dan strategi pemecahan masalah dalam komputasi.
