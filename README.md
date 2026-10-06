# EDWIN Jeans — Performance Reports

Repo hosting laporan performa affiliate Edwin Jeans, dijalankan DIZCO.

## Isi

```
index.html              hub landing, TIDAK dikunci
september/monthly.html  laporan bulanan September 2026, dienkripsi staticrypt
.nojekyll               biar GitHub Pages serve statis tanpa Jekyll
```

## Setup sekali di awal

1. Bikin repo `edwinreport` di org `dizco-agency`, **Public**.
2. Upload semua isi folder ini ke root repo (termasuk file `.nojekyll` yang namanya diawali titik).
3. Settings → Pages → Source: **Deploy from a branch**, Branch: **main**, folder: **/ (root)**. Save.
4. Tunggu ±1 menit. Live di: `https://dizco-agency.github.io/edwinreport`

## Password laporan

```
DizcoxEdwin123!
```

Kirim ke klien terpisah dari linknya, jangan satu pesan.

## Salt staticrypt Edwin

```
5238a97c0f3fe2d8d017fd8cb39b91e7
```

Laporan Edwin berikutnya **wajib** dienkripsi pakai salt yang sama, biar fitur "ingat saya" jalan lintas file:

```
npx staticrypt@3 <file>.html -p 'DizcoxEdwin123!' --salt 5238a97c0f3fe2d8d017fd8cb39b91e7 -d out
```

## Nambah laporan baru

Taruh file hasil enkripsi di `<folder-bulan>/<nama>.html`, lalu daftarkan di array `MONTHS` dalam `index.html`. Index-nya auto-detect: file yang ada otomatis jadi tombol aktif, yang belum ada tampil "Segera".
