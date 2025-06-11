---
title: "06 - Rat in a Maze"
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

---

## 💻 Implementasi C++ – Rat in a Maze

```cpp
#include <iostream>
#include <vector>
#include <string>

using namespace std;

bool isSafe(int x, int y, vector<vector<int>>& maze, vector<vector<bool>>& visited, int n) {
    return (x >= 0 && x < n && y >= 0 && y < n &&
            maze[x][y] == 1 && !visited[x][y]);
}

void solve(int x, int y, vector<vector<int>>& maze, int n, vector<string>& paths,
           string path, vector<vector<bool>>& visited) {
    // Basis: sampai tujuan
    if (x == n - 1 && y == n - 1) {
        paths.push_back(path);
        return;
    }

    visited[x][y] = true;

    int dx[] = {+1,  0,  0, -1};      // D, R, L, U
    int dy[] = { 0, +1, -1,  0};
    char move[] = {'D','R','L','U'};

    for (int i = 0; i < 4; ++i) {
        int newX = x + dx[i];
        int newY = y + dy[i];

        if (isSafe(newX, newY, maze, visited, n)) {
            solve(newX, newY, maze, n, paths, path + move[i], visited);
        }
    }

    visited[x][y] = false; // Backtrack
}

vector<string> findPaths(vector<vector<int>>& maze, int n) {
    vector<string> paths;
    vector<vector<bool>> visited(n, vector<bool>(n, false));

    if (maze[0][0] == 1) {
        solve(0, 0, maze, n, paths, "", visited);
    }

    return paths;
}

int main() {
    vector<vector<int>> maze = {
        {1, 0, 0, 0},
        {1, 1, 0, 1},
        {1, 1, 0, 0},
        {0, 1, 1, 1}
    };
    int n = maze.size();

    vector<string> result = findPaths(maze, n);

    if (result.empty()) {
        cout << "Tidak ada jalur yang ditemukan.\n";
    } else {
        cout << "Jalur yang ditemukan:\n";
        for (const string& path : result) {
            cout << path << endl;
        }
    }

    return 0;
}

---

> Rat in a Maze bukan hanya masalah jalur — tetapi latihan logika, eksplorasi, dan strategi sistematis dalam menyelesaikan masalah berbasis constraint.
