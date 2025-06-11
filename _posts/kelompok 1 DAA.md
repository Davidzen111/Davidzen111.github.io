---
title: "01-Activity Selection Problem"
date: 2025-06-10 09:00:00 +0700
categories: 
tags: [c++, Activity Selection]
layout: post
---

## 🧠 Activity Selection Problem

**Activity Selection Problem** adalah masalah optimasi klasik dalam ilmu komputer yang bertujuan memilih sebanyak mungkin aktivitas yang tidak saling tumpang tindih berdasarkan waktu mulai dan selesai.

### 💡 Tujuan:
Memilih jumlah maksimal aktivitas yang bisa dilakukan oleh satu orang atau satu sumber daya, tanpa ada dua aktivitas yang tumpang tindih waktunya.

---

### 🚀 Solusi: Algoritma Greedy

Masalah ini dapat diselesaikan secara efisien menggunakan **algoritma greedy**. Strateginya:

1. **Urutkan aktivitas berdasarkan waktu selesai (finish time).**
2. **Pilih aktivitas pertama (selesai paling awal).**
3. **Pilih aktivitas selanjutnya jika waktu mulai ≥ waktu selesai aktivitas sebelumnya.**

---

### 🧾 Pseudocode:
```text
ACTIVITY-SELECTOR(s, f, n)
    A = {a1}      // Pilih aktivitas pertama
    j = 1
    for i = 2 to n
        if s[i] >= f[j]
            A = A ∪ {ai}
            j = i
    return A

### ⏱️ Kompleksitas:
Waktu: O(n log n) → karena proses pengurutan.

Ruang: O(n) → untuk menyimpan input dan hasil.

---

### 📦 Aplikasi Nyata:
Penjadwalan kelas, laboratorium, dan ruang meeting

Penjadwalan proses CPU

Jadwal pengiriman logistik

Alokasi bandwidth di jaringan

### ✅ Kelebihan:
Solusi sederhana dan optimal untuk kasus dasar

Efisien dan mudah diimplementasikan

---

### ⚠️ Keterbatasan:
Tidak cocok untuk masalah dengan banyak batasan tambahan seperti prioritas, biaya, atau lokasi.

### Kesimpulan:
Activity Selection Problem menyajikan cara cerdas untuk menyusun jadwal tanpa konflik waktu. Algoritma greedy menjadi solusi optimal dengan efisiensi tinggi. Untuk masalah yang lebih kompleks, dapat dipertimbangkan pendekatan lain seperti pemrograman dinamis atau algoritma heuristik.