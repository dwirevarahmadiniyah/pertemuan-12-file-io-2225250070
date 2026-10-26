# Pertemuan 12 - File I/O dan Error Handling

**Nama:** Dwi Reva Rahmadiniyah  
**NIM:** 2225250070 
**Kelas:** 3E

## Tujuan

Membaca, memvalidasi, mengolah, dan menulis data file menggunakan Python. Program dibuat untuk menghitung rekap nilai dari file teks serta menangani kesalahan yang mungkin terjadi selama proses pengolahan data.

## Format File Input

File input disimpan di `data/nilai.txt` dengan format `NIM,nilai`.

Contoh isi file:

```text
A001,85
A002,78
A003,92
A004,abc
A005,74
A006,88
```

Baris `A004,abc` digunakan untuk menguji penanganan data nilai yang tidak valid.

## Cara Menjalankan

1. Buka folder proyek di VS Code.
2. Pastikan file `data/nilai.txt` sudah tersedia.
3. Buka Terminal di VS Code.
4. Jalankan perintah berikut:

```bash
python tugas/rekap_nilai_file.py
```

Program akan membaca data nilai, memvalidasi setiap baris, menghitung statistik nilai, dan menyimpan hasilnya ke `data/hasil_rekap.txt`.

## Error yang Ditangani

- **FileNotFoundError:** Menangani kondisi ketika file input tidak ditemukan dengan menampilkan pesan kesalahan.
- **ValueError:** Menangani data yang tidak sesuai format atau nilai yang tidak dapat dikonversi menjadi angka. Baris yang tidak valid dilewati agar data lainnya tetap dapat diproses.

## Test Case

| No. | Kondisi | Hasil yang Diharapkan | Hasil Aktual | Status |
|---|---|---|---|---|
| 1 | Semua data valid | Semua data diproses dan rekap berhasil dibuat. | Belum diuji | Belum diuji |
| 2 | File `nilai.txt` tidak ditemukan | Pesan file tidak ditemukan ditampilkan dan program tidak crash. | Belum diuji | Belum diuji |
| 3 | Nilai berisi teks, misalnya `A004,abc` | Baris tidak valid dilewati dan data lain tetap diproses. | Belum diuji | Belum diuji |
| 4 | Terdapat baris kosong | Baris kosong dilewati. | Belum diuji | Belum diuji |
| 5 | Nilai sama dengan 60 | Nilai dihitung sebagai lulus. | Belum diuji | Belum diuji |

*Catatan: Kolom hasil aktual dan status diisi setelah setiap pengujian dilakukan.*

## Refleksi

Dalam pengerjaan tugas ini, saya menemukan kesalahan ketika program membaca data nilai yang berisi teks `abc`. Kesalahan tersebut terjadi karena teks tidak dapat dikonversi menjadi angka menggunakan fungsi `float()`. Untuk mengatasinya, saya menggunakan `try-except` dengan `ValueError`, sehingga baris yang tidak valid dapat dilewati dan data lainnya tetap diproses. Saya juga menggunakan `FileNotFoundError` untuk menangani kondisi ketika file input tidak ditemukan. Dari latihan ini, saya memahami pentingnya validasi data dan penanganan error dalam program Python.
