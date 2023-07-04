
# UAS Pengolahan Citra

Pertama, impor beberapa library yang dibutuhkan:

cv2: OpenCV, library komputer vision yang digunakan untuk pemrosesan citra.

numpy as np: Library untuk operasi numerik yang mempermudah manipulasi data dalam bentuk array.

matplotlib.pyplot as plt: Library untuk visualisasi data dalam bentuk grafik atau gambar.

Fungsi detect_lane_markings(image) adalah fungsi utama 
untuk mendeteksi garis marka jalan pada citra input. 

Langkah-langkah dalam fungsi ini adalah sebagai berikut:
a. Konversi citra ke dalam ruang warna Grayscale menggunakan cv2.cvtColor() untuk mempermudah pemrosesan lebih lanjut.

b. Terapkan filter blur pada citra Grayscale menggunakan cv2.GaussianBlur() untuk mengurangi noise dan memperhalus citra.

c. Deteksi tepi pada citra menggunakan metode Canny dengan cv2.Canny(), yang akan menghasilkan citra biner dengan tepi yang terdeteksi lebih tajam.

d. Lakukan transformasi Hough untuk mendeteksi garis-garis pada citra biner menggunakan cv2.HoughLinesP(). Hasil dari deteksi ini akan berupa array yang berisi koordinat titik-titik garis yang terdeteksi.

e. Gambar garis-garis pada citra asli dengan fungsi draw_lines().

Fungsi draw_lines(image, lines, color, thickness) digunakan untuk menggambar garis-garis pada citra. Fungsi ini akan menerima citra, array lines yang berisi koordinat titik-titik garis yang telah terdeteksi, serta parameter color dan thickness yang menentukan warna dan ketebalan garis yang akan digambar.

Setelah mendefinisikan fungsi-fungsi di atas, dilakukan pembacaan citra input dengan cv2.imread() yang kemudian akan diubah ukurannya menjadi lebih kecil untuk meningkatkan performa dengan cv2.resize().

Selanjutnya, fungsi detect_lane_markings() dipanggil untuk mendeteksi garis marka jalan pada citra input.

Terakhir, hasil citra asli dan citra dengan garis marka jalan ditampilkan menggunakan matplotlib.pyplot. Citra asli ditampilkan di sebelah kiri dengan judul "Original Image", sedangkan citra dengan garis marka jalan ditampilkan di sebelah kanan dengan judul "Detected Lane Markings".

