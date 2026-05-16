# Git Case Study: Resolving Remote Errors & Fixing Broken Git Submodules in Microservices Architecture

This document provides a comprehensive step-by-step troubleshooting guide based on a real-world scenario. It covers configuring Git in a local Golang Microservices project, handling remote URL conflicts, and fixing inaccessible folder issues on GitHub.

---

## Chronology of Issues & Solutions (Case Study)

### Issue 1: `error: remote origin already exists` and `Repository not found`
When attempting to link the local project to a newly created GitHub repository using the `git remote add origin` command, the terminal rejected it because the name *origin* was already registered to an old, incorrect repository URL (`Microservice-Golang-1-Online-Soccer-Field-Booking.git`). Consequently, executing `git push` resulted in a fatal error stating the repository was not found.

#### Actual Solution:
Use the `set-url` command to forcefully update the *remote origin* address to the new valid repository without wiping out the existing local Git history.

```bash
# 1. Update the remote URL to the correct repository
git remote set-url origin https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git

# 2. Set the default local branch to main and push to GitHub
git branch -M main
git push -u origin main
```

**Terminal Verification Output:**
```bash
git remote -v
origin  https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git (fetch)
origin  https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git (push)
```

---

### Issue 2: Folder `user-service` is Greyed Out & Inaccessible on GitHub
After a successful push, the `user-service` microservice folder appeared as an empty, greyed-out icon with an arrow overlay on GitHub, making its contents unreadable. This happened because a hidden `.git` folder accidentally existed inside the sub-folder `user-service`, causing the root Git to mistake it for a *Git Submodule* (tracked as *mode 160000*).

#### Actual Solution:
Untrack the corrupted index cache, delete the redundant internal git metadata from that specific service folder, and re-index the entire directory.

```bash
# 1. Remove the tracked submodule cache of 'user-service' from the root Git index
git rm --cached "user-service"

# 2. Permanently delete the nested hidden .git folder inside the user-service directory
rm -rf "user-service/.git"

# 3. Re-add all files from the service directory back to the root Git index
git add .

# 4. Create a fix commit
git commit -m "Fix: memperbaiki folder user-service yang tidak bisa diklik"

# 5. Push the finalized changes back to GitHub
git push origin main
```

**Index Update Verification (Terminal Output):**
The root Git successfully converted the object status from a submodule reference (`delete mode 160000`) into regular files (`create mode 100644`) for the entire `user-service` layout:
```text
 delete mode 160000 user-service
 create mode 100644 user-service/.env.example
 create mode 100644 user-service/.gitignore
 create mode 100644 user-service/go.mod
 create mode 100644 user-service/main.go
 ...
```

---

## Daily Standard Operating Procedure (SOP Post-Linking)

Once the foundational terminal configuration is successfully settled, daily file management can be handled entirely via the graphical user interface (GUI) inside VS Code's **Source Control** panel (`Ctrl + Shift + G`) following this lifecycle:

1. **Stage Changes:** Click the `+` icon next to the modified or newly created Go files to stage them.
2. **Commit:** Type a clear, concise summary of your code changes into the *Message* bar and click the checkmark button (Commit).
3. **Sync Changes:** Click the sync button to seamlessly push local development adjustments to GitHub and pull any remote updates.

---

### 💡 VS Code Productivity Tip
* You can instantly preview how this `.md` document renders beautifully before pushing it to GitHub by pressing `Ctrl + Shift + V` within VS Code.



Versi Bahasa Indonesia :

Mantap! Semua riwayat terminal dari ThinkPad X250 Anda menunjukkan bahwa Anda telah berhasil menyelesaikan dua masalah besar yang sangat krusial bagi developer backend/microservices: mengatasi konflik URL repositori remote (`git remote set-url`) dan memperbaiki masalah *submodule* folder (`user-service`) yang tersangkut.

Ini adalah bahan artikel/konten portofolio IT yang sangat bagus karena murni berdasarkan *case study* (studi kasus) nyata yang sering membingungkan banyak developer baru.

Berikut adalah draf utuh isi file `.md` dari baris pertama sampai terakhir. Cukup klik tombol **Copy** satu kali di pojok kanan atas kotak kode di bawah ini, lalu buat file baru bernama `GIT_TROUBLESHOOT_GUIDE.md` (atau nama lain) di VS Code Anda dan langsung *paste*.

```markdown
# Studi Kasus Git: Solusi Error Remote & Memperbaiki Git Submodule Pasca Inisialisasi Microservices

Dokumen ini mendokumentasikan langkah-langkah nyata (Troubleshooting) dalam mengonfigurasi Git pada struktur projek Microservices Golang lokal hingga berhasil diunggah ke GitHub, lengkap dengan penyelesaian kendala teknis yang umum terjadi.

---

## Kronologi Masalah & Solusi (Case Study)

### Masalah 1: `error: remote origin already exists` dan `Repository not found`
Saat mencoba menautkan projek lokal ke repositori GitHub baru menggunakan perintah `git remote add origin`, terminal menolak karena nama *origin* sudah terdaftar ke URL repositori lama yang salah (`Microservice-Golang-1-Online-Soccer-Field-Booking.git`). Akibatnya, proses `git push` menghasilkan pesan fatal karena repositori tujuan tidak ditemukan.

#### Solusi Aktual:
Gunakan perintah `set-url` untuk memperbarui alamat *remote origin* secara paksa menuju repositori baru yang valid tanpa harus menghapus konfigurasi Git yang sudah ada.

```bash
# 1. Mengubah alamat URL remote ke repositori yang benar
git remote set-url origin [https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git](https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git)

# 2. Set branch utama ke main dan push ke GitHub
git branch -M main
git push -u origin main
```

**Verifikasi Hasil Terminal:**
```bash
git remote -v
origin  [https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git](https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git) (fetch)
origin  [https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git](https://github.com/Tri-Adi-Putra/Tri-Adi-Putra-Microservice-Golang-Online-Soccer-Field-Booking.git) (push)
```

---

### Masalah 2: Folder `user-service` Berwarna Abu-abu & Tidak Bisa Diklik di GitHub
Setelah berhasil melakukan *push*, folder salah satu layanan microservice (`user-service`) tampak kosong dan tidak dapat diakses di GitHub. Hal ini disebabkan karena di dalam sub-folder `user-service` secara tidak sengaja tersimpan folder rahasia `.git` bawaan (dianggap sebagai *Git Submodule* atau *mode 160000* oleh Git utama).

#### Solusi Aktual:
Melakukan *untrack* (menghapus cache pelacakan lama), menghapus berkas metadata git internal pada layanan tersebut, lalu melakukan *indexing* ulang.

```bash
# 1. Hapus cache pelacakan submodule 'user-service' dari index Git utama
git rm --cached "user-service"

# 2. Hapus direktori .git rahasia yang merusak di dalam folder user-service
rm -rf "user-service/.git"

# 3. Masukkan kembali seluruh file service ke index lokal
git add .

# 4. Buat commit perbaikan
git commit -m "Fix: memperbaiki folder user-service yang tidak bisa diklik"

# 5. Push perubahan final ke GitHub
git push origin main
```

**Hasil Pembaruan Index (Terminal Output):**
Berhasil mengubah status objek Git dari submodule (`delete mode 160000`) menjadi berkas reguler (`create mode 100644`) untuk seluruh ekosistem di dalam `user-service`:
```text
 delete mode 160000 user-service
 create mode 100644 user-service/.env.example
 create mode 100644 user-service/.gitignore
 create mode 100644 user-service/go.mod
 create mode 100644 user-service/main.go
 ...
```

---

## Ringkasan Alur Kerja Harian (SOP Pasca Penautan)

Setelah konfigurasi dasar di atas selesai, manajemen file kodingan selanjutnya dapat dilakukan sepenuhnya secara visual melalui menu **Source Control** di VS Code (`Ctrl + Shift + G`) dengan siklus:

1. **Stage Changes:** Klik ikon `+` pada berkas/fitur baru yang telah diubah lokalnya.
2. **Commit:** Tulis pesan perubahan fungsional yang jelas pada kolom *Message* lalu centang/commit.
3. **Sync Changes:** Klik sinkronisasi untuk otomatis melakukan pembaharuan data harian antara laptop dan GitHub.

```
