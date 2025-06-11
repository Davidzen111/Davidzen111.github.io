---
title: "03 - Huffman Coding"
date: 2025-06-11
categories: [Algoritma, Kompresi, Huffman Coding]
tags: [huffman coding, kompresi, algoritma]
pin: true
author: Davidzen
---

## 📚 Huffman Coding

**Huffman Coding** ditemukan oleh **David A. Huffman pada tahun 1952** sebagai metode untuk mengompresi data tanpa kehilangan informasi (lossless). Ini dilakukan dengan memberikan kode biner yang lebih pendek pada simbol yang sering muncul dalam suatu pesan/data.

---

**Huffman Coding** adalah algoritma kompresi data lossless yang efisien dan banyak digunakan dalam format ZIP, JPEG, MP3, dan lainnya. Algoritma ini bekerja dengan membuat kode biner berdasarkan frekuensi karakter dalam data. Semakin sering suatu karakter muncul, semakin pendek kode binernya. Hasilnya, ukuran data menjadi jauh lebih kecil tanpa kehilangan informasi apa pun.

---

## 💡 Konsep Dasar

- Berdasarkan **frekuensi karakter** dalam data.
- Karakter dengan **frekuensi tinggi → kode pendek**
- Karakter dengan **frekuensi rendah → kode panjang**
- Data direpresentasikan dalam **struktur pohon biner**

---

## 🧩 Langkah-langkah Huffman Coding

1. Hitung frekuensi setiap karakter.
2. Buat node (simpul) untuk setiap karakter.
3. Gabungkan dua node dengan frekuensi terendah.
4. Ulangi hingga menjadi satu **pohon Huffman**.
5. Tetapkan kode biner berdasarkan traversal pohon (0 = kiri, 1 = kanan).

---

## 🧪 Contoh Kasus

Contoh: `"ABBCCCDDDD"`  
Frekuensi karakter:
- A = 1
- B = 2
- C = 3
- D = 4

Contoh hasil kode Huffman:  
- D = `0`  
- C = `10`  
- B = `110`  
- A = `111`  

➡️ Hasil kompresi lebih pendek dari representasi ASCII biasa.

---

## 🔬 Simulasi Huffman Coding

**Pesan:** `BCCABBDDAECCBBAEDDCC`  
- Total huruf: 20  
- ASCII (8 bit per karakter): 160 bit  
- Huffman Code: **45 bit**

➡️ Terjadi penghematan ukuran data yang signifikan (dari 160 → 45 bit).

---

## 🧠 Pseudocode dan Kompleksitas

- Kompleksitas waktu: `O(n log n)`  
- `n` = jumlah karakter unik  
- Struktur data: **heap** (priority queue)  
- Implementasi melibatkan **traversal pohon biner** untuk menentukan kode

---

## ✅ Kelebihan

- ✅ Tidak ada data yang hilang (lossless)
- ✅ Efisien untuk data dengan distribusi tidak merata
- ✅ Banyak digunakan dalam kompresi file (ZIP, JPEG, dll)

## ❌ Kekurangan

- ❌ Tidak optimal untuk data dengan distribusi karakter merata
- ❌ Memerlukan tabel kode untuk proses dekompresi

---

## 💻 Implementasi C++ Huffman Coding

Berikut contoh implementasi sederhana algoritma **Huffman Coding** dalam bahasa C++:

```cpp
#include <iostream>
#include <queue>
#include <unordered_map>
#include <vector>
using namespace std;

// Node Huffman
struct Node {
    char ch;
    int freq;
    Node *left, *right;

    Node(char c, int f) : ch(c), freq(f), left(nullptr), right(nullptr) {}
};

// Perbandingan untuk priority_queue (min-heap)
struct Compare {
    bool operator()(Node* a, Node* b) {
        return a->freq > b->freq;
    }
};

// Traversal pohon untuk menghasilkan kode Huffman
void buildCodes(Node* root, string str, unordered_map<char, string>& huffmanCode) {
    if (!root) return;

    if (!root->left && !root->right) {
        huffmanCode[root->ch] = str;
    }

    buildCodes(root->left, str + "0", huffmanCode);
    buildCodes(root->right, str + "1", huffmanCode);
}

// Fungsi utama untuk membangun Huffman Tree
void huffmanEncoding(const string& text) {
    unordered_map<char, int> freq;
    for (char ch : text) freq[ch]++;

    priority_queue<Node*, vector<Node*>, Compare> pq;
    for (auto pair : freq) {
        pq.push(new Node(pair.first, pair.second));
    }

    while (pq.size() > 1) {
        Node* left = pq.top(); pq.pop();
        Node* right = pq.top(); pq.pop();

        Node* merged = new Node('\0', left->freq + right->freq);
        merged->left = left;
        merged->right = right;

        pq.push(merged);
    }

    Node* root = pq.top();
    unordered_map<char, string> huffmanCode;
    buildCodes(root, "", huffmanCode);

    cout << "Huffman Codes:\n";
    for (auto pair : huffmanCode) {
        cout << pair.first << " = " << pair.second << '\n';
    }

    // Encoding hasil
    string encodedStr;
    for (char ch : text) {
        encodedStr += huffmanCode[ch];
    }

    cout << "\nEncoded message:\n" << encodedStr << '\n';
}

int main() {
    string text = "BCCABBDDAECCBBAEDDCC";
    huffmanEncoding(text);
    return 0;
}

---

> Huffman Coding tetap menjadi metode yang efisien dan andal dalam kompresi data modern.
