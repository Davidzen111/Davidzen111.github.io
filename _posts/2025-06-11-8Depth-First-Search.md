---
title: "08 - Depth First Search"
date: 2025-06-11
categories: [DFS, Algoritma, Struktur Data]
tags: [depth-first-search, dfs, graf, tree]
pin: true
author: Davidzen
layout: post
---

## 🔍 Apa Itu Depth First Search?

Depth First Search (DFS) adalah algoritma pencarian atau traversing dalam struktur data graf atau pohon. DFS akan menjelajahi simpul (node) sedalam mungkin sebelum kembali (backtrack) dan menjelajahi cabang lainnya.

---

## 🛠️ Cara Kerja DFS

- Dimulai dari simpul awal (root atau node tertentu).
- Kunjungi simpul tersebut dan tandai sebagai telah dikunjungi.
- Rekursif ke salah satu simpul tetangganya yang belum dikunjungi.
- Jika tidak ada simpul tetangga yang belum dikunjungi, algoritma akan backtrack ke simpul sebelumnya.
- Proses diulang hingga semua simpul dikunjungi.

---

## ⚙️ Implementasi DFS

DFS dapat diimplementasikan dengan dua cara:
- **Rekursif**: Menggunakan pemanggilan fungsi secara berulang.
- **Menggunakan Stack**: Simulasikan backtracking manual menggunakan struktur stack.

### 📌 Contoh Implementasi DFS dalam C++

```cpp
#include <iostream>
#include <vector>
using namespace std;

const int MAX = 100;
vector<int> adj[MAX];  // daftar ketetanggaan
bool visited[MAX];     // penanda simpul yang sudah dikunjungi

void dfs(int node) {
    visited[node] = true;
    cout << node << " ";

    for (int neighbor : adj[node]) {
        if (!visited[neighbor]) {
            dfs(neighbor);
        }
    }
}

int main() {
    int jumlahSimpul, jumlahEdge;
    cout << "Masukkan jumlah simpul dan edge: ";
    cin >> jumlahSimpul >> jumlahEdge;

    cout << "Masukkan pasangan simpul (u v):\n";
    for (int i = 0; i < jumlahEdge; i++) {
        int u, v;
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u); // jika graf tidak berarah
    }

    int mulaiDari;
    cout << "Mulai DFS dari simpul: ";
    cin >> mulaiDari;

    cout << "Hasil DFS traversal: ";
    dfs(mulaiDari);
    cout << endl;

    return 0;
}

---

## ✅ Kelebihan DFS

- Memiliki penggunaan memori yang lebih rendah dibandingkan BFS.
- Cocok untuk menemukan solusi yang dalam pada struktur graf.

---

## ⚠️ Kekurangan DFS

- Bisa masuk ke jalur yang sangat dalam dan salah (dead end).
- Tidak menjamin menemukan jalur terpendek.
- Risiko infinite loop jika graf memiliki siklus dan tidak ditangani dengan benar.

---

## 🌐 Aplikasi DFS

- Pencarian solusi dalam puzzle (misalnya labirin).
- Deteksi siklus dalam graf.
- Topological sorting.
- Komponen terhubung dalam graf tak berarah.

---

> DFS adalah algoritma fundamental yang membentuk dasar pemahaman traversal graf dan digunakan luas dalam berbagai aplikasi ilmu komputer, dari AI hingga pemrosesan jaringan.
