---
title: "10 - Dijkstra's Algorithm"
date: 2025-06-11
categories: [Dijikstra, Algoritma, Struktur Data]
tags: [dijkstra, shortest-path, graf, algoritma]
author: Davidzen
layout: post
pin: true
---

## 🔍 Apa Itu Dijkstra's Algorithm?

**Dijkstra's Algorithm** adalah metode untuk mencari **jalur terpendek** antara dua titik dalam **graf berbobot non-negatif**. Algoritma ini bekerja pada graf yang terdiri dari simpul (node) dan sisi (edge) dengan bobot tertentu, dan digunakan untuk menentukan jalur optimal dari simpul awal ke simpul tujuan.

---

## 🛠️ Cara Kerja Dijkstra's Algorithm

1. **Inisialisasi**: Set semua jarak ke setiap simpul sebagai tak terhingga (∞), kecuali simpul awal (0).
2. **Pilih Simpul**: Pilih simpul dengan jarak terpendek yang belum diproses.
3. **Perbarui Jarak**: Update jarak ke semua tetangga dari simpul yang dipilih jika lebih pendek dari sebelumnya.
4. **Tandai Simpul**: Tandai simpul tersebut sebagai telah diproses.
5. **Ulangi**: Lakukan langkah 2-4 sampai semua simpul diproses atau simpul tujuan tercapai.

---

## 💻 Implementasi Dijkstra dalam C++

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <climits>

using namespace std;

typedef pair<int, int> pii; // {jarak, simpul}

void dijkstra(vector<vector<pii>>& graph, int start, vector<int>& dist) {
    priority_queue<pii, vector<pii>, greater<pii>> pq;
    dist[start] = 0;
    pq.push({0, start});

    while (!pq.empty()) {
        int u = pq.top().second;
        int current_dist = pq.top().first;
        pq.pop();

        if (current_dist > dist[u]) continue;

        for (auto& edge : graph[u]) {
            int v = edge.first;
            int weight = edge.second;

            if (dist[u] + weight < dist[v]) {
                dist[v] = dist[u] + weight;
                pq.push({dist[v], v});
            }
        }
    }
}

int main() {
    int n = 6; // Jumlah simpul
    vector<vector<pii>> graph(n);
    vector<int> dist(n, INT_MAX);

    // Contoh graf: A=0, B=1, ..., F=5
    graph[0].push_back({1, 1});  // A -> B (1)
    graph[0].push_back({2, 5});  // A -> C (5)
    graph[1].push_back({2, 2});  // B -> C (2)
    graph[1].push_back({3, 2});  // B -> D (2)
    graph[1].push_back({4, 1});  // B -> E (1)
    graph[3].push_back({5, 1});  // D -> F (1)
    graph[4].push_back({5, 2});  // E -> F (2)

    dijkstra(graph, 0, dist); // Mulai dari A

    cout << "Jarak terpendek dari A ke F: " << dist[5] << endl; // Output: 4
    return 0;
}
```

---

## ✅ Kelebihan Dijkstra's Algorithm

- **Menjamin Jalur Terpendek**: Hasilnya optimal untuk graf dengan bobot non-negatif.
- **Multi-Tujuan**: Sekali jalan, dapat menemukan jarak ke semua simpul lain.
- **Banyak Aplikasi Nyata**: Digunakan dalam navigasi, logistik, dan jaringan komputer.

---

## ⚠️ Kekurangan Dijkstra's Algorithm

- ❌ **Tidak Mendukung Bobot Negatif**: Tidak bisa digunakan jika ada bobot negatif.
- ⚠️ **Kurang Efisien untuk Graf Sparse Besar**: Perlu optimasi seperti min-heap.
- 📉 **Menghitung Semua Jalur**: Meski hanya butuh satu tujuan, ia tetap memproses semua.

---

## 🌐 Aplikasi Dijkstra's Algorithm

- 🚗 **Navigasi Jalan**: Digunakan pada GPS untuk cari rute tercepat.
- 📦 **Pengiriman Barang**: Rute efisien untuk distribusi logistik.
- 🌐 **Jaringan Komputer**: Routing data melalui jalur tercepat dan terpendek.

---

## 🧾 Kesimpulan

Dijkstra's Algorithm merupakan solusi yang kuat untuk masalah jalur terpendek dalam graf berbobot positif. Dengan efisiensi tinggi dan hasil optimal, algoritma ini tetap menjadi pilar penting dalam bidang teori graf dan aplikasi dunia nyata seperti navigasi dan komunikasi data. Namun, penggunaannya harus hati-hati dalam graf dengan bobot negatif dan pada graf yang sangat besar tanpa optimasi yang memadai.

> “Cari bukan hanya yang terdekat, tapi juga yang terbaik.” – Inspirasi dari Dijkstra 😄
