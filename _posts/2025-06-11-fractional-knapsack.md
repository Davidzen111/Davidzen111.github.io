---
title: "Fractional Knapsack - Optimisasi Greedy untuk Solusi Cepat"
date: 2025-06-11
categories: [Algoritma, Optimisasi, Fractional Knapsack]
tags: [fractional knapsack, greedy, algoritma, struktur data]
pin: true
author: Davidzen
layout: post
---

## Fractional Knapsack

**Fractional Knapsack** adalah salah satu variasi dari Knapsack Problem yang memungkinkan pengambilan sebagian barang. Berbeda dengan 0/1 Knapsack yang hanya mengizinkan barang diambil seluruhnya atau tidak sama sekali, versi fraksional ini bisa diselesaikan dengan pendekatan **greedy** yang efisien. Dengan menghitung rasio nilai per berat (_value/weight_), kita dapat memilih barang terbaik secara lokal untuk mencapai solusi global yang optimal.

---

## 🎒 Apa itu Fractional Knapsack?

Fractional Knapsack adalah masalah optimisasi di mana kita ingin **memaksimalkan nilai barang** yang dimasukkan ke dalam tas (knapsack) dengan kapasitas terbatas, **dengan izin mengambil sebagian dari barang**.

---

## 🔍 Karakteristik

- Setiap item memiliki nilai (_value_) dan berat (_weight_).
- Kapasitas tas terbatas.
- Barang **boleh diambil sebagian** (misalnya 0.5 bagian).
- Cocok diselesaikan menggunakan **Greedy Algorithm**.

---

## ⚙️ Strategi Penyelesaian

1. Hitung rasio **value/weight** untuk tiap item.
2. Urutkan item berdasarkan rasio tersebut secara menurun.
3. Ambil sebanyak mungkin item dari yang paling tinggi rasio-nya hingga tas penuh.
4. Jika kapasitas sisa tidak cukup, ambil **sebagian** dari item terakhir.

---

## ⏱️ Kompleksitas Waktu

- `O(n log n)` untuk pengurutan berdasarkan rasio
- `O(n)` untuk pengisian tas

---

## 🛠️ Aplikasi Fractional Knapsack

- Penjadwalan tugas dengan sumber daya terbatas  
- Investasi dana ke beberapa proyek  
- Pengalokasian bandwidth jaringan  
- Optimisasi logistik dan transportasi

---

## 🧠 Tentang Algoritma Greedy

**Greedy Algorithm** membuat keputusan terbaik secara lokal (saat ini) dengan harapan keputusan tersebut akan membawa ke solusi optimal global.

**Ciri-cirinya:**
- Tidak mempertimbangkan efek jangka panjang.
- Sangat cepat dan sederhana.
- Efektif hanya untuk beberapa jenis masalah, termasuk Fractional Knapsack.

---

## ✅ Kesimpulan

Fractional Knapsack menawarkan solusi cepat dan optimal untuk masalah alokasi dengan kapasitas terbatas. Dengan memanfaatkan **algoritma greedy**, kita dapat memilih barang berdasarkan **rasio nilai/berat** dan mendapatkan hasil terbaik tanpa perlu mengeksplorasi semua kemungkinan kombinasi.

---

> Fractional Knapsack membuktikan bahwa strategi sederhana pun bisa menghasilkan solusi optimal dalam dunia algoritma.
