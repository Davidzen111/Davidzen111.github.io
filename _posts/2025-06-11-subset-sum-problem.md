---
title: "Subset Sum Problem – Optimasi Kombinasi dengan DP dan Backtracking"
date: 2025-06-11
categories: [Algoritma, Dynamic Programming]
tags: [subset sum, dp, backtracking, algoritma, np-complete]
layout: post
author: Davidzen
pin: true
---

## 📌Subset Sum Problem

**Subset Sum Problem (SSP)** adalah masalah klasik dalam ilmu komputer yang tergolong **NP-Complete**. Diberikan sebuah himpunan bilangan bulat dan sebuah nilai target, tugasnya adalah menentukan apakah ada subset dari himpunan tersebut yang jumlah elemennya sama dengan target.

Masalah ini memiliki banyak **variasi**, bisa diselesaikan dengan pendekatan **rekursif** atau **dynamic programming (DP)**, dan sangat relevan dalam aplikasi nyata seperti **kriptografi**, **keuangan**, **bioinformatika**, dan **AI**.

---

## 🧩 Definisi Formal

> Diberikan himpunan bilangan bulat `S = {s₁, s₂, ..., sₙ}` dan sebuah angka `target`, apakah ada subset dari `S` yang totalnya sama dengan `target`?

Contoh:
- `Set = {3, 34, 4, 12, 5, 2}, Target = 9` → ✅ Ya, subset `{4, 5}`
- `Set = {3, 34, 4, 12, 5, 2}, Target = 25` → ❌ Tidak ada subset yang valid

---

## 🔄 Pendekatan Penyelesaian

### 1. Rekursif (Brute Force)
- Coba semua kombinasi subset
- Kompleksitas waktu: `O(2ⁿ)`
- Kurang efisien untuk input besar

### 2. Dynamic Programming (DP)
- **Memoization (Top-Down)** dan **Tabulation (Bottom-Up)**
- Gunakan tabel `dp[n][sum]` untuk menyimpan hasil submasalah
- Kompleksitas waktu: `O(n × sum)`
- **Space Optimization**: Gunakan dua array 1D untuk mengurangi ruang menjadi `O(sum)`

---

## 🧪 Variasi Subset Sum

- **Bounded**: Setiap elemen hanya bisa digunakan sekali  
- **Unbounded**: Elemen bisa dipakai berkali-kali  
- **Exact k Elements**: Subset harus terdiri dari tepat `k` elemen  
- **Partition Problem**: Bagi set menjadi dua subset dengan jumlah yang sama  
- **Multi-target**: Subset harus memenuhi lebih dari satu syarat (misal harga dan berat)  
- **Approximate**: Tidak ada subset pas, cari yang mendekati target  

---

## 📦 Aplikasi di Dunia Nyata

- 🔐 **Kriptografi**: Sistem kunci publik berbasis ransel  
- 💰 **Investasi dan Anggaran**: Memilih kombinasi aset sesuai target  
- 🧬 **Bioinformatika**: Kombinasi ekspresi gen atau DNA  
- 📦 **Logistik & E-Commerce**: Pemilihan item dengan batasan biaya/berat  
- 🧠 **Kecerdasan Buatan**: Optimalisasi pilihan subset dalam pemodelan  

---

## ✅ Kesimpulan

Subset Sum Problem adalah permasalahan penting yang bukan hanya relevan secara teoritis dalam dunia algoritma dan optimasi, tetapi juga memiliki **aplikasi luas di berbagai bidang**. Dengan banyaknya variasi dan pendekatan penyelesaian, SSP menjadi alat penting dalam desain solusi berbasis kombinasi dan batasan.

---


> “Subset Sum bukan hanya soal angka – tapi tentang bagaimana kita memilih dengan bijak dalam batas yang tersedia.”
