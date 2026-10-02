# Oil Sounding Tank Calculator + Shared Online History

Aplikasi ini mempertahankan kalkulasi ST 1–ST 4, tabel density, tombol Simpan Kalkulasi ke History, filter tanggal, dan export CSV.

## History bersama antar komputer
Versi ini sudah disiapkan untuk **Supabase**. Jika `supabase-config.js` diisi dengan URL project dan anon/public key yang benar, History disimpan ke database online sehingga orang A dan orang B yang membuka URL GitHub Pages yang sama akan melihat history yang sama.

Jika konfigurasi belum diisi, aplikasi otomatis memakai `localStorage` sebagai fallback sehingga tetap bisa dicoba secara lokal.

## Setup Supabase
1. Buat project di Supabase.
2. Buka **SQL Editor**.
3. Jalankan seluruh isi `supabase-schema.sql`.
4. Buka **Project Settings > API**. Salin **Project URL** dan **anon/public key**.
5. Masukkan keduanya ke `supabase-config.js`:

```js
window.SUPABASE_CONFIG = {
  url: "https://xxxxx.supabase.co",
  anonKey: "eyJ..."
};
```

Jangan pernah memasukkan `service_role` key ke GitHub/frontend.

## Catatan keamanan
SQL di atas memakai website publik tanpa login, sehingga siapa pun yang dapat membuka website dapat membaca, menambah, dan menghapus history. Untuk penggunaan pabrik yang lebih aman, tahap berikutnya sebaiknya memakai **Supabase Auth/login operator** dan policy RLS berdasarkan user/operator.

## Data Excel
```text
data/
├── ST 1.xlsx
├── ST 2.xlsx
├── ST 3.xlsx
├── ST 4.xlsx
└── density.xlsx
```

## Menjalankan
Gunakan VSCode + Live Server untuk pengujian lokal atau GitHub Pages untuk deployment.
