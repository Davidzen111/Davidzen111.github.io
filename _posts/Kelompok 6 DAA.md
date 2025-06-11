---
title: "Rat in a Maze – Pemecahan Jalur dengan Backtracking"
date: 2025-06-11
categories: [Algoritma, Backtracking, Rat in a Maze]
tags: [rat in a maze, backtracking, pemrograman, pathfinding]
layout: post
author: Davidzen
pin: true
---

## 🐭 Rat in a Maze Problem

**Rat in a Maze** adalah masalah algoritmik klasik yang melibatkan pencarian **semua jalur dari titik awal ke titik akhir** dalam sebuah labirin berbentuk matriks/grid. Masalah ini sering digunakan untuk memperkenalkan konsep **backtracking**, di mana solusi dicoba langkah demi langkah, dan mundur jika menemui jalan buntu.

## 🎯 Tujuan

Menemukan **semua kemungkinan jalur** dari koordinat awal `(0, 0)` ke tujuan `(N-1, N-1)` dalam sebuah matriks `N x N`, di mana:
- `1` menandakan sel yang bisa dilewati (jalan)
- `0` menandakan sel yang tidak bisa dilewati (tembok)

## 🔁 Prinsip Kerja

1. Mulai dari `(0, 0)`, tikus mencoba bergerak ke 4 arah: **D (Down), R (Right), L (Left), U (Up)**
2. Hanya sel dengan nilai `1` dan belum dikunjungi yang bisa diakses
3. Jika jalan buntu, **backtrack** ke posisi sebelumnya dan coba arah lain
4. Ulangi hingga mencapai `(N-1, N-1)`

## 📌 Contoh Jalur

Matriks:

```
1 0 0 0
1 1 0 1
1 1 0 0
0 1 1 1
```

Jalur valid contoh: `DRDDRR` dan `DDRDRR`  
Dimulai dari `(0, 0)` → tujuan `(3, 3)`

## 🧠 Algoritma Backtracking

- Cek apakah langkah valid
- Tandai posisi sebagai bagian dari jalur
- Lanjutkan ke langkah berikutnya
- Jika tidak bisa lanjut, **batalkan (undo)** dan coba arah lain
- Jika sampai tujuan, simpan solusi

## ✅ Kelebihan

- Sederhana dan mudah diimplementasikan
- Dapat menemukan **semua solusi**
- Fleksibel dan tidak memerlukan struktur data kompleks

## ⚠️ Kekurangan

- Kurang efisien untuk labirin besar
- Risiko **stack overflow** jika rekursi terlalu dalam
- Dapat mengulang jalur yang sama jika tidak dikendalikan

## 📦 Aplikasi Nyata

- Simulasi robot navigasi dalam peta
- Pencarian jalur di GPS dan sistem transportasi
- Pemetaan jalur dalam **game development**
- Visualisasi pemecahan masalah dalam AI


> Rat in a Maze bukan hanya masalah jalur — tetapi latihan logika, eksplorasi, dan strategi sistematis dalam menyelesaikan masalah berbasis constraint.
