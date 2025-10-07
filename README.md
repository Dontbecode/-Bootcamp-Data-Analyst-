## Ringkasan Pembelajaran NumPy & Eksperimen Performa

Repositori ini berisi notebook `main.ipynb` yang mendemonstrasikan dasar-dasar NumPy untuk analisis data, eksperimen performa antara Python murni vs NumPy, serta pembuatan data acak berdasarkan berbagai distribusi probabilitas.

### Topik yang Dipelajari
- **Pembuatan data besar (simulasi gaji karyawan)**: membuat list berisi jutaan nilai acak dan mengonversinya menjadi array NumPy untuk pemrosesan cepat.
- **Perbandingan performa Python vs NumPy**:
  - Menghitung rata-rata dengan `sum(...)/len(...)` (Python murni) vs `np.mean(...)` (NumPy) menggunakan `%%timeit`.
- **Membuat array**:
  - `np.array` untuk 1D, 2D, 3D.
  - Menentukan `dtype` (contoh: `np.int32`).
- **Generator deret dan array khusus**:
  - `np.arange(start, stop, step)`.
  - `np.zeros(shape, dtype)` dan `np.ones(shape, dtype)`.
- **Mengatur dimensi**:
  - `reshape`, atribut `shape`, serta meratakan array dengan `flatten()`.
- **Indexing & slicing**:
  - Index tunggal, indeks negatif, dan slicing `[start:stop:step]` untuk 1D dan 2D.
- **Modifikasi elemen**:
  - Mengubah nilai elemen dengan indeks dan update sebagian array (`array[1:3] = [...]`).
- **Operasi vektorisasi**:
  - Operasi aritmetika elemen-per-elemen: `+ - * /`.
- **Atribut array penting**:
  - `shape` (dimensi) dan `size` (jumlah elemen).
- **Fungsi statistik**:
  - `mean`, `sum`, `min`, `max`, `median`, `std`, `var`, `percentile`.
- **Distribusi probabilitas**:
  - Normal: `np.random.normal(loc, scale, size)`.
  - Uniform: `np.random.uniform(low, high, size)`.

### Contoh Ringkas

```python
import numpy as np

# 1) Mean Python vs NumPy
numbers = list(range(1_000_000))
arr = np.array(numbers)
py_mean = sum(numbers) / len(numbers)
np_mean = np.mean(arr)

# 2) Array 2D dan reshape
a = np.arange(12)
a2 = a.reshape(3, 4)

# 3) Indexing & slicing
first = a[0]
sub = a[1:5]

# 4) Operasi vektorisasi
b = a * 2

# 5) Statistik
mean_val = np.mean(a)
std_val = np.std(a)

# 6) Distribusi
normal_samples = np.random.normal(loc=7, scale=1, size=5)
uniform_samples = np.random.uniform(low=0, high=10, size=5)
```

### Cara Menjalankan Notebook
1. Pastikan Python 3.9+ terpasang.
2. (Opsional) Buat environment terpisah:
   - Windows PowerShell:
     ```powershell
     python -m venv .venv
     .\.venv\Scripts\Activate.ps1
     ```
3. Instal dependensi minimal:
   ```bash
   pip install numpy jupyter
   ```
4. Jalankan Jupyter dan buka `main.ipynb`:
   ```bash
   jupyter notebook
   ```
   Atau gunakan VS Code + Jupyter extension, lalu jalankan sel-selnya.

### Catatan Performa
- Operasi berbasis NumPy biasanya jauh lebih cepat dibanding Python murni karena vektorisasi dan implementasi C di balik layar.
- Gunakan magic `%%timeit` di notebook untuk mengukur waktu eksekusi secara reliabel.

### Struktur Proyek
- `main.ipynb`: Notebook yang berisi seluruh contoh dan eksperimen.
- `README.md`: Dokumen ringkasan materi dan panduan menjalankan.

### Lisensi
Gunakan bebas untuk pembelajaran pribadi.




### Ringkasan Pembelajaran Hari Ini (2025-10-07)
- **NumPy: Performa & Dasar Array**
  - Simulasi data besar (10.000.000 gaji) dan perbandingan rata-rata: Python murni (~73 ms) vs `np.mean` (~6 ms) menunjukkan percepatan signifikan berkat vektorisasi.
  - Pembuatan array 1D/2D/3D dengan `np.array`, kontrol `dtype` (mis. `np.int32`).
  - Generator dan array khusus: `np.arange`, `np.zeros`, `np.ones`.
  - Pengaturan dimensi: `reshape`, atribut `shape`, meratakan dengan `flatten()`.
  - Indexing & slicing pada 1D/2D, termasuk indeks negatif dan rentang `[start:stop:step]`.
  - Modifikasi elemen dan slice assignment (contoh `array[1:3] = [...]`).
  - Operasi vektorisasi elemen-per-elemen: `+`, `-`, `*`, `/`.
  - Atribut penting: `shape`, `size`.
  - Statistik dasar: `mean`, `sum`, `min`, `max`, `median`, `std`, `var`, `percentile`.
  - Distribusi probabilitas: Normal (`np.random.normal`) dan Uniform (`np.random.uniform`).

- **Pandas: Pengenalan**
  - Versi yang digunakan: 2.3.3.
  - Struktur data utama: `Series` (1D berindeks) dan `DataFrame` (2D seperti tabel).
  - Membuat `DataFrame` dari list/dict; penggunaan `display(...)` untuk tampilan terformat di Jupyter.
  - Membaca data dari berbagai sumber: `read_csv`, `read_excel`, `read_json`, serta contoh `pd.read_excel('data.xlsx')`.

Catatan: Materi hari ini fokus membangun intuisi performa NumPy dan dasar manipulasi struktur data di Pandas sebagai fondasi analisis data.