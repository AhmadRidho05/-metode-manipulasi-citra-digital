Brightness Adjustment – Pengolahan Citra Digital

Proyek ini berisi program sederhana untuk melakukan penyesuaian brightness (kecerahan) pada sebuah gambar menggunakan Python dan OpenCV. Metode ini digunakan untuk membuat gambar terlihat lebih terang atau lebih gelap sesuai kebutuhan.

1. Kebutuhan Program

Sebelum menjalankan kode, pastikan beberapa library berikut sudah terinstall:

pip install opencv-python
pip install matplotlib

2. Cara Menjalankan

Download atau clone repository.

Letakkan gambar yang ingin diproses di folder yang sama dengan file kode.

Ubah nama file gambar di bagian:

img = cv2.imread('image.jpg')


Jalankan notebook .ipynb atau file .py seperti biasa.

3. Penjelasan Singkat

Program ini bekerja dengan langkah-langkah berikut:

Membaca gambar dari file.

Mengubah format warna dari BGR ke RGB (supaya warna tampil normal di matplotlib).

Menambahkan nilai brightness melalui parameter beta.

Menampilkan perbandingan antara gambar asli dan gambar yang sudah diubah brightness-nya.

Untuk mengatur tingkat kecerahan, cukup ubah nilai berikut:

brightness_value = 50


Nilai positif akan mencerahkan gambar, sedangkan nilai negatif akan membuat gambar lebih gelap.

4. Kode Program
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Load gambar
img = cv2.imread('image.jpg')

if img is None:
    print("Gambar tidak ditemukan! Pastikan file ada di folder yang sama.")
else:
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    brightness_value = 50
    bright_img = cv2.convertScaleAbs(img_rgb, alpha=1, beta=brightness_value)

    plt.figure(figsize=(10, 5))

    plt.subplot(1, 2, 1)
    plt.title("Original")
    plt.imshow(img_rgb)
    plt.axis("off")

    plt.subplot(1, 2, 2)
    plt.title("Brightness Adjusted")
    plt.imshow(bright_img)
    plt.axis("off")

    plt.show()

5. Catatan

Proyek ini dibuat untuk memenuhi tugas mata kuliah Pengolahan Citra Digital. Silakan modifikasi sesuai kebutuhan.
