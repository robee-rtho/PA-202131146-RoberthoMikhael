
# UAS Pengolahan Citra

Deteksi marka jalan merupakan salah satu tugas dalam pengolahan citra yang bertujuan untuk mengidentifikasi marka jalan yang ada pada gambar atau video jalan. Metode deteksi marka jalan bertujuan untuk memisahkan marka jalan dari latar belakang atau elemen lain dalam citra dengan menggunakan teknik-teknik pengolahan citra.

Berikut ini adalah beberapa teknik pengolahan citra yang umum digunakan dalam deteksi marka jalan:

1. Peningkatan Kontras:
   - Peningkatan kontras dapat digunakan untuk memperjelas marka jalan dalam gambar.
   - Teknik-teknik yang umum digunakan meliputi penyesuaian histogram, transformasi linier, atau metode peningkatan kontras adaptif.

2. Filter Spasial:
   - Filter spasial dapat digunakan untuk menghilangkan noise dan meningkatkan kualitas citra sebelum proses deteksi marka jalan.
   - Filter seperti filter median, filter Gaussian, atau filter bilateral dapat digunakan untuk menghaluskan citra dan mengurangi efek noise.

3. Segmentasi:
   - Segmentasi merupakan proses memisahkan marka jalan dari latar belakang citra.
   - Teknik-teknik segmentasi yang umum digunakan meliputi thresholding, clustering, atau segmentasi berbasis tepi (edge-based segmentation).

4. Transformasi Hough:
   - Transformasi Hough adalah metode yang populer untuk deteksi garis dalam citra.
   - Transformasi Hough dapat digunakan untuk mendeteksi garis marka jalan dalam citra dengan menemukan parameter garis yang paling sesuai.

5. Analisis Kontur:
   - Analisis kontur melibatkan identifikasi dan analisis bentuk geometris marka jalan.
   - Fitur-fitur seperti panjang, sudut, atau properti morfologis kontur dapat digunakan untuk mengklasifikasikan marka jalan.

6. Klasifikasi:
   - Klasifikasi merupakan tahap akhir dalam deteksi marka jalan yang melibatkan penggunaan model klasifikasi untuk membedakan marka jalan dan non-marka jalan.
   - Metode klasifikasi yang umum digunakan meliputi klasifikasi berbasis aturan, klasifikasi berbasis fitur, atau klasifikasi berbasis pembelajaran mesin seperti SVM (Support Vector Machines) atau jaringan saraf tiruan.

Selain teknik-teknik di atas, terdapat juga pendekatan lanjutan dalam deteksi marka jalan, seperti penggunaan jaringan saraf konvolusi (CNN) untuk mendeteksi marka jalan secara end-to-end atau pendekatan berbasis pemodelan 3D.

Pengolahan citra dalam deteksi marka jalan memainkan peran penting dalam mengidentifikasi marka jalan dan memisahkannya dari latar belakang atau elemen lain dalam citra. Dengan menggunakan teknik-teknik pengolahan citra yang tepat, deteksi marka jalan dapat diimplementasikan secara efektif untuk berbagai aplikasi seperti sistem pengemudi otomatis, sistem bantuan pengemudi, atau pemantauan lalu lintas.

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

