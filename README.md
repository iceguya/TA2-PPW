Berikut **README.md versi lengkap, rapi, dan informatif** yang bisa langsung kamu pakai di GitHub. Sudah ditata agar terlihat profesional dan tetap mudah dipahami, lengkap dengan penjelasan workflow Git, struktur commit, dan alur branching.

---

````md
# 🗂️ TA2 Portfolio Project – Git Workflow Documentation

Dokumentasi ini menjelaskan proses penggunaan **Git & GitHub** dalam pengembangan project portfolio, mulai dari inisialisasi repository, workflow commit bertahap, penggunaan branch untuk eksperimen, hingga merge dan push ke remote repository.  

Tujuan:  
✅ Repo rapi dan terstruktur  
✅ Perubahan tercatat per fitur  
✅ Eksperimen styling aman di branch terpisah  
✅ Dokumentasi mudah dipahami oleh dosen/teman kontributor  

---

## 📌 1. Inisialisasi Git untuk Project Portfolio

Langkah pertama adalah menyiapkan _repository_ Git lokal dan menyetel identitas developer.

```bash
git config --global user.name "iceguya"
git config --global user.email "kunhide568@gmail.com"

git init
ls -la
git status
````

📍 **Penjelasan Singkat**

| Perintah              | Fungsi                                           |
| --------------------- | ------------------------------------------------ |
| `git config --global` | Daftarkan identitas agar muncul di setiap commit |
| `git init`            | Membuat repository Git di folder project         |
| `ls -la`              | Melihat struktur file termasuk `.git/`           |
| `git status`          | Mengecek file mana yang belum dilacak Git        |

---

## 📌 2. Commit Bertahap untuk Setiap Section

Setiap perubahan dilakukan bertahap agar riwayat commit jelas dan mudah ditelusuri.

```bash
git add index.html
git commit -m "Init : add index.html"

git add style.css
git commit -m "Add Style.css"

git add .
git commit -m "Add assets folder & images"
```

📍 **Kelebihan commit bertahap**

* Mempermudah rollback jika ada error
* Membuat history Git lebih rapi & bermakna
* Ideal untuk penilaian tugas yang butuh pembuktian progress

📍 **Melihat history:**

```bash
git log --oneline
```

Contoh output:

```
15451d3 (HEAD -> main) Add Style.css
f252c3b Init : add index.html
```

---

## 📌 3. Membuat Branch untuk Eksperimen Styling Baru

Branch digunakan untuk melakukan eksperimen tanpa mengganggu tampilan utama di `main`.

```bash
git checkout -b new-ui
```

Lalu edit CSS → test design → commit:

```bash
git add .
git commit -m "New UI styling update"
```

Jika ingin menyimpan di GitHub:

```bash
git push origin new-ui
```

📍 *Manfaat branch di Git*

| Kondisi                                         | Solusi                     |
| ----------------------------------------------- | -------------------------- |
| Mau coba redesign tanpa merusak yang sudah jadi | Pakai branch terpisah      |
| Mau kerja paralel dengan teman                  | Branching memisahkan scope |
| Mau buat pull request                           | Branch wajib ada           |

---

## 📌 4. Merge Branch Setelah Styling Selesai

Jika hasil eksperimen sudah OK, gabungkan kembali ke `main`.

```bash
git checkout main
git merge new-ui
```

Output merge yang muncul:

```
Fast-forward
 2 files changed, 294 insertions(+), 1 deletion(-)
```

📍 Fast-forward = merge otomatis tanpa konflik

Jika branch sudah tidak dibutuhkan:

```bash
git branch -d new-ui
```

✅ Repo tetap bersih
✅ Riwayat tetap terstruktur

---

## 📌 5. Push ke GitHub & Menambahkan Dokumentasi

Set remote repo:

```bash
git remote add origin https://github.com/iceguya/TA2-PPW.git
git push origin main
```

Push branch fitur:

```bash
git push origin new-ui
```

Buat file dokumentasi:

```
README.md → (berisi penjelasan repo, cara setup, workflow, dll)
```

📌 Setelah dipush, GitHub akan otomatis menampilkan link pull request jika ada branch baru:

```
remote: Create a pull request for 'new-ui' on GitHub by visiting:
remote: https://github.com/iceguya/TA2-PPW/pull/new/new-ui
```

---

## 📁 Struktur Repository

```
TA2-PPW/
├─ images/
│  ├─ preview.jpg
│  └─ assets.jpg
├─ index.html
├─ style.css
└─ README.md
```

---

## 🔁 Alur Workflow Git Secara Visual

```
(main) ──●──●───────────────●───────────────▶ push
             \ 
              \── (new-ui) ●──●──●── merge ─▶
```

---


## 📎 Next Improvement (Opsional)

* Tambahkan GitHub Pages untuk preview website
* Tambahkan `.gitignore` (jika nanti ada node_modules atau build assets)
* Gunakan commit convention seperti `feat:`, `fix:`, `docs:`, `refactor:`

---

✍️ *Maintained by* **@iceguya**
📌 *Project untuk Praktikum Pemrograman Web – Semester 5*
