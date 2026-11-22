# Undangan Digital Nida & Sidik

Undangan pernikahan statis (HTML + CSS + JS), monokrom hitam-putih dengan ornamen wayang kulit
(gunungan, sulur ukel, pita tumpal) dan latar batik kawung. Data diambil dari undangan kertas.

## Isi folder

```
index.html     -> isi undangan (nama, orang tua, alamat, jam acara, daftar turut mengundang)
style.css      -> tampilan
script.js      -> KONFIGURASI di bagian atas (hitung mundur, link Maps, rekening gift, musik)
assets/        -> foto dan musik
.nojekyll      -> agar GitHub Pages menyajikan file apa adanya
```

## Yang perlu dilengkapi

1. **Rekening gift**: buka `script.js`, isi `nomor` dan `atasNama` pada BRI dan Mandiri di bagian `gift`.
   Selama nomor kosong, kartu menampilkan "Nomor rekening menyusul". Tombol "Salin Nomor" muncul otomatis.
2. **Link Google Maps**: sudah terisi dari QR di undangan kertas. Coba buka sekali untuk memastikan lokasinya benar.
3. **Musik** (opsional): taruh `musik.mp3` di folder `assets/`. Tanpa file ini, tombol musik otomatis hilang.
4. **Foto galeri** (opsional): taruh `galeri-1.jpg` sampai `galeri-4.jpg` di `assets/` (rasio 3:4, sekitar 200-300 KB).
   Selama belum ada, bagian galeri tidak tampil.

Foto mempelai ada di `assets/foto-sidik.png` dan `assets/foto-nida.png` (PNG transparan).
Untuk menggantinya, simpan PNG transparan dengan nama yang sama lalu timpa file-nya.

## Animasi

- Bagian mempelai pria: foto masuk dari kiri, teks dari kanan.
- Bagian mempelai wanita: foto masuk dari kanan, teks dari kiri.
- Warna bagian gelap dan terang bergantian otomatis, jadi menambah atau menghapus bagian aman.

## Mengubah data

Nama, orang tua, alamat, jam akad/resepsi, dan daftar "Turut Mengundang" diedit langsung di `index.html`.
Waktu hitung mundur ada di `script.js` (`tanggalHitungMundur`).

## Nama tamu otomatis

Tambahkan `?to=Nama Tamu` di akhir link, contoh:

```
https://USERNAME.github.io/undangan-nida-sidik/?to=Budi%20Santoso
```

Spasi ditulis `%20`. Kirim link berbeda untuk tiap tamu agar nama mereka tampil di cover.

## Publikasi lewat GitHub (agar tamu bisa membuka)

Repository ini sudah berisi satu commit awal, jadi tinggal dihubungkan ke GitHub.

1. Di GitHub, buat repository baru bernama `undangan-nida-sidik`, pilih **Public**, dan **jangan**
   centang "Add a README" atau opsi lain yang membuat file awal.
2. Di folder proyek ini, jalankan:
   ```bash
   git remote add origin https://github.com/USERNAME/undangan-nida-sidik.git
   git push -u origin main
   ```
   (ganti `USERNAME` dengan nama akun GitHub Anda). Dengan VS Code bisa juga lewat menu
   **Source Control > Publish to GitHub**.
3. Buka **Settings > Pages**. Pada *Build and deployment*, pilih **Deploy from a branch**,
   branch **main**, folder **/ (root)**, lalu **Save**.
4. Tunggu 1-2 menit. Undangan aktif di `https://USERNAME.github.io/undangan-nida-sidik/`.

Setelah itu, setiap perubahan cukup:

```bash
git add .
git commit -m "Perbarui undangan"
git push
```

Catatan:
- Repository harus Public agar GitHub Pages gratis bisa dibuka tamu. Siapa pun yang memiliki link
  bisa membuka undangan, dan isi file juga terlihat di repository. Karena itu jangan menaruh data
  yang tidak ingin dilihat umum.
- Halaman sudah diberi `noindex`, jadi tidak muncul di hasil pencarian Google. Hanya tamu yang
  menerima link yang akan menemukannya.

## Catatan lain

- Musik diputar saat tombol **Buka Undangan** ditekan, karena browser memblokir musik otomatis.
- Font memakai Google Fonts, jadi perangkat tamu perlu terhubung internet agar huruf tampil sesuai.
