# Latihan Kontribusi GitHub

Selamat datang di repo `latihan-kontribusi`! Repo ini dibuat khusus bagi teman-teman yang sedang belajar menggunakan GitHub dan ingin mencoba **berkontribusi** (membuat Pull Request) ke sebuah proyek.

---

## Tujuan

Tujuan dari repo ini sangat sederhana: memberikan tempat latihan yang aman dan mudah bagi siapa saja yang ingin mencoba proses _fork_, _clone_, membuat _branch_, mengedit file, dan membuat _Pull Request_.

---

## Cara Berkontribusi

Ikuti langkah-langkah di bawah ini untuk menambahkan data profil kamu ke file `kontribusi.md`:

### 1. Fork Repositori Ini

**Fork** repositori ini ke akun GitHub kamu. Caranya:

- Klik tombol **"Fork"** di pojok kanan atas halaman ini.

### 2. Clone Repositori Hasil Fork

Setelah kamu berhasil melakukan _fork_, sekarang **clone** repositori tersebut ke komputer lokal kamu.

- Buka terminal (atau Git Bash/Command Prompt).
- Ganti `<username-github-kamu>` dengan username GitHub kamu.
- Jalankan perintah berikut:

  ```bash
  git clone https://github.com/<username-github-kamu>/latihan-kontribusi.git
  ```

### 3. Buat Branch Baru

Masuk ke dalam direktori proyek dan buat **branch** baru. Nama branch disarankan sesuai dengan nama kamu agar mudah dikenali.

- Masuk ke direktori proyek:

  ```bash
  cd latihan-kontribusi
  ```

- Buat branch baru (ganti `add-nama_anda` dengan nama kamu, contoh: `add-budi`):
  ```bash
  git switch -c add-nama_anda
  ```

### 4. Edit File `kontribusi.md`

Buka file `kontribusi.md` menggunakan editor teks favorit kamu (VS Code, Sublime Text, Notepad++, dll.).

- Tambahkan baris baru di dalam tabel dengan format:

  ```markdown
  | Nama Anda | [Link GitHub Anda](https://github.com/username_anda) |
  ```

  **Contoh:**

  ```markdown
  | Budi Santoso | [BudiSantoso](https://github.com/BudiSantoso) |
  ```

- Pastikan format tabel tetap rapi.

### 5. Tambahkan dan Commit Perubahan

Setelah selesai mengedit, simpan perubahan, lalu tambahkan dan _commit_ perubahan tersebut.

- Tambahkan perubahan ke _staging area_:
  ```bash
  git add kontribusi.md
  ```
- Lakukan _commit_ (ganti `Tambahkan [Nama Anda]` dengan nama kamu):
  ```bash
  git commit -m "Tambahkan [Nama Anda]"
  ```

### 6. Push Perubahan ke Repositori Fork Kamu

Kirim perubahan dari komputer lokal ke repositori hasil _fork_ kamu di GitHub.

- Ganti `add-nama_anda` dengan nama branch yang kamu buat sebelumnya:

  ```bash
  git push origin add-nama_anda
  ```

### 7. Buat Pull Request (PR)

Sekarang, saatnya membuat **Pull Request (PR)**!

- Buka halaman repositori kamu di GitHub (hasil _fork_).
- Kamu akan melihat sebuah notifikasi "Compare & pull request" atau "This branch is 1 commit ahead of main branch". Klik tombol **"Compare & pull request"**.
- Isi judul PR dengan jelas, contoh: `Add: [Nama Anda]`.
- Tambahkan deskripsi singkat jika perlu.
- Klik tombol **"Create pull request"**.

### **Penting: Cara Menyelesaikan Konflik (Jika Terjadi)**

Terkadang, ketika kamu membuat Pull Request, mungkin terjadi "konflik" jika ada perubahan di file `kontribusi.md` yang sama dari orang lain sebelum Pull Request kamu digabungkan. Jangan khawatir, ini adalah bagian normal dari kolaborasi di Git!

Jika Pull Request kamu menunjukkan status "This branch has conflicts that must be resolved", ikuti langkah-langkah berikut untuk memperbaikinya:

1. **Ambil Perubahan Terbaru dari Repositori Utama:**

   - Pastikan kamu berada di direktori proyek lokal kamu.
   - Pertama, pastikan kamu berada di _branch_ `main` lokal kamu:

     ```bash
     git switch main
     ```

   - Tambahkan _upstream remote_ (jika belum pernah):

     ```bash
     git remote add upstream https://github.com/nama-github-anda/latihan-kontribusi.git
     ```

     _(Ganti `nama-github-anda` dengan username GitHub kamu jika sebelumnya sudah pernah menambahkan `upstream` ke repositori `latihan-kontribusi` milikku. Jika belum, tambahkan `https://github.com/namasaya/latihan-kontribusi.git` dengan nama username GitHub saya. Pastikan `upstream` mengarah ke repositori asli (`latihan-kontribusi` milikku), bukan `fork` milikmu)._

   - _Fetch_ perubahan terbaru dari repositori utama (`upstream`) ke _branch_ `main` lokal kamu:
     ```bash
     git fetch upstream
     ```
   - Sekarang, pindah ke _branch_ PR kamu (contoh: `add-nama_anda`):

     ```bash
     git switch add-nama_anda
     ```

   - Gabungkan perubahan dari `main` _branch_ repositori utama (`upstream/main`) ke _branch_ PR kamu:

     ```bash
     git merge upstream/main
     ```

     _Atau jika kamu lebih nyaman dengan `rebase` (untuk sejarah commit yang lebih bersih):_

     ```bash
     git rebase upstream/main
     ```

2. **Selesaikan Konflik Secara Manual:**

   - Git akan memberitahu file mana saja yang mengalami konflik (biasanya `kontribusi.md`).
   - Buka file tersebut di editor teks kamu. Kamu akan melihat penanda konflik seperti `<<<<<<<`, `=======`, dan `>>>>>>>`.
   - Contoh tampilan konflik:

     ```markdown
     | Nama Budi | [Budi](https://github.com/budi) |
     <<<<<<< HEAD
     | Nama Bambang | [Bambang](https://github.com/bambang) |
     =======
     | Nama Prima | [Prima](https://github.com/prima) |

     > > > > > > > add-prima
     ```

   - Hapus penanda konflik dan edit bagian yang berkonflik agar sesuai dengan yang kamu inginkan (gabungkan kedua perubahan dengan benar). Pastikan format tabel tetap utuh dan rapi.
   - Setelah selesai mengedit, simpan file tersebut.

3. **Tambahkan dan Commit Perubahan yang Sudah Diperbaiki:**

   ```bash
   git add kontribusi.md
   git commit -m "Resolve conflict in kontribusi.md"
   ```

4. **Push Perubahan ke Repositori Fork Kamu:**

   - Sekali lagi, _push_ perubahan yang sudah diperbaiki ke repositori _fork_ kamu.

     ```bash
     git push origin add-nama_anda
     ```

     _Jika kamu menggunakan `rebase` di langkah 1, mungkin kamu perlu melakukan `git push --force-with-lease origin add-nama_anda` (gunakan `--force-with-lease` untuk keamanan, jangan hanya `--force`)._

Setelah langkah ini, GitHub akan mendeteksi bahwa konflik sudah diselesaikan, dan Pull Request kamu akan siap untuk di-review ulang.

---

Selamat! Kamu sudah berhasil membuat Pull Request pertamamu. Saya akan me-review PR kamu dan segera menggabungkannya ke branch utama jika sudah sesuai.

---

Jika ada pertanyaan atau kesulitan, jangan ragu untuk membuka `Issue` baru di repositori ini.

Selamat berlatih!

---
