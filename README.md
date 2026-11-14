# Orkestra

Orkestra adalah aplikasi desktop untuk menjalankan satu tim agent [Claude Code](https://claude.com/claude-code) dari satu jendela. Satu agent menjadi orchestrator: ia menerima permintaanmu, membagi pekerjaan ke agent lain, dan meneruskan pertanyaan mereka kepadamu. Tiap agent adalah sesi `claude` interaktif biasa, dengan terminalnya sendiri yang bisa kamu lihat dan ketik langsung.

Aplikasinya ringan: dibuat dengan Rust dan Tauri, installer sekitar 5 MB.

Repo ini hanya berisi installer di halaman [Releases](https://github.com/ElyaNur/Orkestrator/releases). Kode sumbernya tidak dipublikasikan.

## Yang bisa dilakukan

- **Tim agent.** Beberapa agent berjalan berdampingan, masing-masing dengan peran, warna, dan terminalnya sendiri. Agent yang lama diam ditidurkan dan dilanjutkan lagi saat dibutuhkan.
- **Pertanyaan di satu tempat.** Saat agent butuh keputusanmu, muncul lencana "perlu kamu". Pertanyaannya dijawab dari satu pop up, tanpa mencari terminal mana yang sedang menunggu.
- **Pekerjaan.** Tiap pekerjaan punya label, branch, dan worktree git sendiri, dan bergerak di papan dari todo sampai selesai. Agent hanya mengubah berkas di worktree pekerjaannya.
- **Memori tim.** Catatan yang bertahan antar sesi, supaya agent tidak mengulang pertanyaan yang sama.
- **Papan peraturan.** Aturan kerja yang berlaku untuk semua agent dalam satu tim.
- **Brankas.** Kredensial per tim, disimpan terpisah dari percakapan.
- **Riwayat.** Semua pertanyaan dan jawaban lama bisa dicari lagi.
- **Pemakaian.** Token per agent dan per pekerjaan, serta limit 5 jam dan mingguan langgananmu.
- **Pembaruan otomatis.** Aplikasi memberi tahu saat ada versi baru. Pembaruan hanya dipasang sesudah kamu mengekliknya.

## Yang dibutuhkan

- Windows 10 atau 11 (64-bit). Linux didukung, tetapi belum ada paketnya di sini.
- Claude Code sudah terpasang dan sudah masuk dengan akunmu. Orkestra menjalankan `claude` milikmu; ia tidak membawa model atau akun sendiri.
- Git, untuk fitur pekerjaan.

## Memasang

1. Buka [Releases](https://github.com/ElyaNur/Orkestrator/releases) dan unduh `Orkestra_<versi>_x64-setup.exe` dari rilis terbaru.
2. Jalankan installer itu. Windows bisa menampilkan peringatan SmartScreen karena installer belum punya sertifikat penanda tangan kode; pilih "More info" lalu "Run anyway" kalau kamu mengunduhnya dari halaman ini.
3. Buka Orkestra, buat orchestrator pertamamu, dan tambahkan folder proyek.

## Pembaruan

Orkestra mengecek versi baru saat dibuka dan tiap 6 jam. Kalau ada, muncul lencana di baris bawah; klik untuk melihat catatan rilis dan memasangnya. Tiap pembaruan ditandatangani, dan aplikasi menolak berkas yang tanda tangannya tidak cocok.

Di Linux aplikasi hanya memberi tahu ada versi baru; pemasangannya dengan tangan.

## Catatan

- Agent berjalan dengan izin penuh di folder proyek yang kamu berikan. Beri hanya folder yang memang boleh mereka ubah.
- Data aplikasi disimpan di komputermu sendiri. Percakapan dengan model berjalan lewat Claude Code seperti biasa.
