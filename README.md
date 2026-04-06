# AI-Video-Generator-n8n
Workflow n8n otomatis untuk pembuatan video AI (Image-to-Video) secara asinkron dengan integrasi Google Drive. Dibangun untuk efisiensi produksi konten pemasaran digital.

# 🎬 AI Video Generator Automation with n8n

Proyek ini adalah alur kerja (workflow) otomatisasi menggunakan n8n untuk mengubah gambar statis menjadi video pendek secara cerdas melalui integrasi API AI. Sistem ini menangani proses pembuatan video secara asinkron, mulai dari pengisian formulir hingga penyimpanan otomatis ke Google Drive.

## 🚀 Fitur Utama
- **Interface Formulir**: Input prompt dan URL gambar melalui antarmuka web.
- **Pemrosesan Asinkron**: Mekanisme jeda (Wait) dan perulangan (Looping) untuk memantau status render video secara otomatis.
- **Ekstraksi Data**: Menggunakan JavaScript untuk mengambil URL video dari respons JSON yang kompleks.
- **Penyimpanan Cloud**: Mengunduh hasil akhir dan mengunggahnya langsung ke Google Drive.

## 🛠️ Arsitektur Workflow
Alur kerja ini terdiri dari beberapa tahapan utama:
1. **Submit Text Prompt**: Menerima input data dari pengguna.
2. **Mengirim Request**: Melakukan permintaan POST ke API Video AI.
3. **Menunggu (Wait)**: Jeda 20 detik agar server memiliki waktu untuk memproses video.
4. **Cek Status**: Memeriksa apakah video sudah selesai dibuat.
5. **Kondisi (IF)**: Jika sukses, lanjut ke tahap download; jika belum, kembali menunggu.
6. **Ekstrak URL**: Mengambil link download video menggunakan Code Node.
7. **Download & Simpan**: Mengunduh file video dan mengunggahnya ke Google Drive.

## 🔧 Cara Penggunaan
1. **Import Workflow**: Unduh file .json dari repositori ini dan import ke n8n kamu.
2. **Setup Kredensial**: Hubungkan akun Google Drive kamu pada node yang bersangkutan.
3. **Input URL**: Saat menjalankan form, gunakan format link Direct Download untuk gambar agar sistem bisa memprosesnya:
   `https://drive.google.com/uc?export=download&id=ID_FILE_KAMU`
4. **Jalankan**: Klik execute dan isi prompt yang diinginkan.

## 📝 Catatan Teknis
- Pastikan file gambar di Google Drive sudah diatur aksesnya menjadi "Anyone with the link".
- Gunakan API Key yang valid agar request tidak ditolak oleh server.

---
Proyek ini dibuat untuk memenuhi Tugas 3 pada Modul Implementasi AI untuk Pemasaran.
