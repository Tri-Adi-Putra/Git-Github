# Daily Git & GitHub Workflow Guide in VS Code

This document outlines the standard operating procedure (SOP) for keeping your GitHub repository up to date whenever you modify code, fix bugs, or add new files to your project within VS Code.

---

## Core Workflow: Stage ➡️ Commit ➡️ Push

You can update your code using either the **Visual Interface (GUI)** inside VS Code or via **Terminal Commands**. Choose whichever method best suits your development workflow.

### Method 1: Using VS Code Visual Interface / GUI (Recommended)

This method is highly efficient as it eliminates the need to type any terminal commands.

#### Step 1: Open the Source Control Panel
* Press `Ctrl + Shift + G` on your keyboard, or click the **Source Control (Tree Branch)** icon on the left sidebar of VS Code.
* Under the **Changes** section, you will see a compiled list of all recently modified or newly created files.

#### Step 2: Stage & Commit Changes
1. **Stage Changes (`+`):** Click the plus (`+`) icon next to the *Changes* label to stage all files at once, or click `+` next to a specific file. Staged items will move up to the *Staged Changes* section.
2. **Commit:** Type a meaningful summary of your adjustments into the **Message** text field (e.g., `"add authentication module"` or `"fix bug in get user"`). Once done, click the **Commit** (Checkmark) button.
* *At this point, your new development checkpoint is securely saved into your local Git database.*

#### Step 3: Push to GitHub (Sync Changes)
* Click the blue **Sync Changes** button that appears in the Source Control panel, or click the circular arrow icon located at the bottom-left corner of VS Code.
* VS Code will automatically execute a *Push* action to upload your local commits to GitHub.

---

### Method 2: Using the VS Code Terminal

If you prefer the speed of executing commands directly within the integrated terminal (`Ctrl + ~`), run these 3 sequential commands:

```bash
# 1. Stage all local modifications and untracked files
git add .

# 2. Record the staged snapshot to the local history with a message
git commit -m "Enter your commit message here"

# 3. Upload the newly recorded commits to your remote GitHub repository
git push origin main
```

---

### 💡 Pro-Tip Before Writing New Code
Before writing any fresh code at the start of your session, make it a habit to always **Pull** first. This ensures your local environment stays synchronized with any changes made directly on the GitHub web interface.
* **Via GUI:** Click the **three dots (...)** icon at the top of the Source Control panel ➡️ Select **Pull**.
* **Via Terminal:** Run the `git pull origin main` command.


Versi IND

# Panduan Alur Kerja Harian Git & GitHub di VS Code

Dokumen ini menjelaskan prosedur standar operasi (SOP) untuk memperbarui repositori GitHub setiap kali Anda melakukan perubahan kode, memperbaiki *bug*, atau menambahkan berkas baru ke dalam projek di VS Code.

---

## Alur Kerja Utama: Stage ➡️ Commit ➡️ Push

Anda memiliki dua pilihan metode untuk memperbarui kode: menggunakan **Tampilan Visual (GUI)** di VS Code atau menggunakan **Perintah Terminal**. Silakan pilih metode yang paling nyaman dengan alur kerja Anda.

### Metode 1: Menggunakan Tampilan Visual / GUI VS Code (Direkomendasikan)

Metode ini sangat praktis karena Anda tidak perlu mengetik perintah terminal sama sekali.

#### Langkah 1: Buka Panel Source Control
* Tekan kombinasi tombol `Ctrl + Shift + G` pada keyboard Anda, atau klik ikon **Cabang Pohon** di bilah menu sebelah kiri VS Code.
* Di bawah kolom **Changes**, Anda akan melihat daftar seluruh berkas yang baru saja diubah atau ditambahkan.

#### Langkah 2: Lakukan Stage & Commit
1. **Stage Changes (`+`):** Klik ikon tanda tambah (`+`) di samping tulisan *Changes* untuk mengantrekan semua berkas sekaligus, atau klik `+` di samping berkas spesifik. Berkas yang dipilih akan berpindah ke kolom *Staged Changes*.
2. **Commit:** Tuliskan pesan deskriptif mengenai perubahan Anda pada kolom teks **Message** (contoh: `"menambahkan modul autentikasi"` atau `"memperbaiki bug pada get user"`). After that, klik tombol **Commit** (ikon centang).
* *Sampai tahap ini, riwayat perubahan baru Anda sudah aman tersimpan di database Git lokal (komputer).*

#### Langkah 3: Kirim ke GitHub (Sync Changes)
* Klik tombol **Sync Changes** (tombol biru yang muncul di panel panel Source Control, atau ikon panah berputar di pojok kiri bawah VS Code).
* VS Code akan otomatis melakukan proses *Push* untuk mengirim kode baru Anda ke GitHub.

---

### Metode 2: Menggunakan Terminal VS Code

Jika Anda lebih menyukai kecepatan mengetik di terminal bawaan (`Ctrl + ~`), jalankan 3 baris perintah berikut secara berurutan:

```bash
# 1. Masukkan semua perubahan ke dalam antrean Git
git add .

# 2. Simpan perubahan ke Git lokal dengan pesan dokumentasi
git commit -m "Tulis pesan perubahan kodingan Anda di sini"

# 3. Unggah seluruh perubahan terbaru dari lokal ke repositori GitHub
git push origin main
```

---

### 💡 Tips Tambahan Sebelum Mulai Ngoding
Sebelum Anda mulai menulis kode baru di hari berikutnya, biasakan untuk selalu melakukan **Pull** terlebih dahulu. Hal ini berguna untuk mengambil pembaruan terakhir jika Anda sempat melakukan modifikasi langsung lewat website GitHub.
* **Via GUI:** Klik ikon **titik tiga (...)** di panel Source Control ➡️ Pilih **Pull**.
* **Via Terminal:** Jalankan perintah `git pull origin main`.
