# E-Pendidikan Islam (SR)

Laman bahan pembelajaran Pendidikan Islam Sekolah Rendah, Tahun 1 hingga 6.

- **Pengguna (guru & murid):** buka laman web, lihat sahaja.
- **Admin (ustazah):** kemas kini bahan dalam Google Sheet. Laman web dikemas kini sendiri.

---

## 1. Sediakan Google Sheet (pangkalan data)

1. Buat Google Sheet baharu.
2. Namakan tab pertama **`Bahan`** (huruf B besar).
3. **File › Import › Upload** `Bahan.csv` › pilih *Replace current sheet*.
4. (Pilihan) Import `Kunci_Halaman.csv` sebagai tab baharu *Insert new sheet* — senarai semua kod halaman untuk rujukan.
5. Klik **Share** › *General access* › **Anyone with the link** › **Viewer**.
   Jangan beri akses *Editor* kepada orang lain — hanya admin boleh ubah.
6. Salin ID dari URL Sheet:
   `https://docs.google.com/spreadsheets/d/`**`INI_ID_ANDA`**`/edit`

### Lajur tab `Bahan`

| halaman | tajuk | keterangan | pautan | jenis |
|---|---|---|---|---|
| dskp | DSKP Pendidikan Islam Tahun 1 | Dokumen Standard... | https://drive.google.com/... | PDF |
| t2-soalan-jawi | Latihan Suku Kata | 10 soalan | https://drive.google.com/... | PDF |
| t3-games | Bingo Rukun Islam | Boleh print | https://... | Games |

- **halaman** — kod halaman (lihat tab `Kunci_Halaman`). Contoh: `t1-nota-quran`, `t4-hasil`.
- **tajuk** — wajib. Baris tanpa tajuk diabaikan.
- **jenis** — label kecil di sebelah kanan (PDF, Video, Canva, Games...). Boleh kosong.

Pastikan fail Google Drive yang dipautkan juga dikongsi *Anyone with the link › Viewer*.

## 2. Sambungkan laman web ke Sheet

Buka `index.html`, cari baris ini dan tampal ID:

```js
const SHEET_ID  = "INI_ID_ANDA";
const SHEET_TAB = "Bahan";
```

Tukar juga nama laman, guru dan sekolah dalam `const SITE = { ... }`.

## 3. Terbitkan di GitHub Pages (percuma)

1. Log masuk github.com › **New repository** › nama contoh `pendidikan-islam` › **Public** › Create.
2. **Add file › Upload files** › muat naik `index.html` dan `README.md` › Commit.
3. **Settings › Pages** › *Source*: **Deploy from a branch** › Branch: `main` / `(root)` › Save.
4. Selepas 1–2 minit, laman anda di:
   `https://NAMA-PENGGUNA.github.io/pendidikan-islam/`

## 4. Menambah bahan (kerja harian admin)

1. Muat naik fail ke Google Drive › kongsi *Anyone with the link*.
2. Tambah satu baris dalam tab `Bahan`.
3. Muat semula laman web. Siap — tiada perlu sentuh GitHub.

## Nota keselamatan

- Repositori GitHub awam bermaksud kod laman boleh dilihat sesiapa. ID Sheet juga kelihatan, tetapi dengan akses *Viewer* orang hanya boleh **baca**, tidak boleh ubah.
- Jangan letak maklumat peribadi murid (nama penuh, IC, gambar tanpa izin) dalam Sheet atau Drive awam.
