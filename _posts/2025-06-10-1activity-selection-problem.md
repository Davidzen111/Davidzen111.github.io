---
title: "01 - Activity Selection Problem"
date: 2025-06-10 09:00:00 +0700
categories: [Algoritma, Greedy]
tags: [C++, Activity Selection, Greedy Algorithm]
author: Davidzen
pin: true
layout: post
---

## 🧠 Activity Selection Problem

**Activity Selection Problem** adalah masalah optimasi klasik dalam ilmu komputer. Tujuannya adalah memilih sebanyak mungkin aktivitas yang tidak saling tumpang tindih, berdasarkan waktu mulai dan selesai.

### 🎯 Tujuan

Memilih jumlah **maksimal aktivitas** yang bisa dilakukan oleh satu orang (atau sumber daya) **tanpa konflik waktu** antara aktivitas-aktivitas tersebut.

---

## 🚀 Solusi: Algoritma Greedy

Masalah ini dapat diselesaikan dengan **algoritma greedy** karena keputusan lokal yang optimal menghasilkan solusi global yang optimal.

### Langkah-langkah:

1. **Urutkan aktivitas berdasarkan waktu selesai (finish time).**  
2. **Pilih aktivitas pertama** (yang selesai paling awal).  
3. **Iterasi aktivitas berikutnya**:  
   Pilih jika waktu mulai ≥ waktu selesai aktivitas terakhir yang dipilih.

---

## 💻 Pseudocode

```text
ACTIVITY-SELECTOR(s, f, n)
    A = {a1}         // Aktivitas pertama dipilih
    j = 1
    for i = 2 to n
        if s[i] >= f[j]
            A = A ∪ {ai}
            j = i
    return A
```

---

## 💻 Implementasi C++ (Kode Nyata)

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

struct Activity {
    int start, finish;
};

bool compare(Activity a1, Activity a2) {
    return a1.finish < a2.finish;
}

void activitySelection(vector<Activity>& activities) {
    sort(activities.begin(), activities.end(), compare);

    cout << "Aktivitas yang dipilih:\n";
    int lastFinish = activities[0].finish;
    cout << "(" << activities[0].start << ", " << activities[0].finish << ")\n";

    for (int i = 1; i < activities.size(); i++) {
        if (activities[i].start >= lastFinish) {
            cout << "(" << activities[i].start << ", " << activities[i].finish << ")\n";
            lastFinish = activities[i].finish;
        }
    }
}

int main() {
    vector<Activity> activities = {
        {1, 3}, {2, 5}, {4, 6}, {6, 7}, {5, 8}, {8, 9}
    };

    activitySelection(activities);

    return 0;
}
```

---

## ⏱️ Kompleksitas

- **Waktu:** `O(n log n)` (karena proses pengurutan)
- **Ruang:** `O(n)` (untuk menyimpan input dan hasil)

---

## 📦 Aplikasi Nyata

- Penjadwalan kelas dan ruang pertemuan  
- Penjadwalan CPU dalam sistem operasi  
- Penjadwalan pengiriman logistik  
- Pengalokasian bandwidth di jaringan  

---

## ✅ Kelebihan

- Solusi optimal untuk masalah dasar  
- Mudah diimplementasikan dan sangat efisien  
- Cocok sebagai pengantar algoritma greedy  

---

## ⚠️ Keterbatasan

- Tidak cocok untuk kasus yang lebih kompleks dengan:
  - Prioritas antar aktivitas  
  - Biaya atau keuntungan variatif  
  - Batasan lokasi atau sumber daya lain  

---

## 🧾 Kesimpulan

Activity Selection Problem adalah contoh ideal dari masalah yang bisa diselesaikan secara efisien dengan algoritma greedy. Cocok untuk pemula yang ingin memahami **penjadwalan optimal berbasis keputusan lokal**. Untuk kasus yang lebih kompleks, pendekatan seperti **pemrograman dinamis** atau **heuristik** mungkin lebih tepat.
