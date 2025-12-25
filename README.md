🚀 Twitter Data Crawler & Downloader for Google Colab
Selamat datang di Twitter Data Crawler! Proyek ini menyediakan dua skrip Jupyter Notebook yang dirancang untuk berjalan di Google Colab. Skrip ini memungkinkan Anda untuk melakukan crawling (scraping) data dari Twitter berdasarkan kata kunci dan rentang tanggal, kemudian mengemas semua hasilnya ke dalam satu file .zip untuk diunduh.

✨ Fitur Utama
Pencarian Fleksibel: Lakukan pencarian tweet berdasarkan kata kunci yang kompleks.

Filter Tanggal: Tentukan rentang tanggal (mulai dan selesai) untuk crawling data.

Limit Harian: Atur batas jumlah tweet yang ingin diambil per harinya.

Otomatisasi: Skrip akan berjalan secara otomatis untuk setiap tanggal dalam rentang yang ditentukan.

Pengemasan Mudah: Semua hasil crawling yang berupa file CSV akan dikumpulkan dan dikompres menjadi satu file .zip yang siap diunduh.

Ramah Google Colab: Dirancang khusus untuk berjalan dengan lancar di lingkungan Google Colab.

🔧 Cara Penggunaan
Ikuti dua langkah utama di bawah ini untuk menjalankan keseluruhan proses.

Langkah 1: Crawling Data Tweet
Pada langkah ini, kita akan mengonfigurasi dan menjalankan skrip untuk mengambil data dari Twitter.

Buka file Crawling_data_Google_Colab.ipynb di Google Colab.

Konfigurasi Parameter. Edit sel kode pertama untuk menyesuaikan parameter berikut sesuai kebutuhan Anda:

# 1. Masukkan auth token Twitter API Anda
# Anda bisa mendapatkannya dari cookies browser setelah login ke Twitter.
twitter_auth = 'ganti_dengan_auth_token_anda'

# 2. Tentukan Keyword pencarian
# Contoh: "(vaksin OR vaksinasi) (corona OR covid19)"
keyword = "prabowo OR anies OR ganjar" 

# 3. Atur variabel tanggal mulai dan akhir, serta limit harian
# Format tanggal: 'YYYY-MM-DD'
start_date = '2024-01-01'
end_date = '2024-01-07'
Limit_day = 100 # Jumlah maksimal tweet yang diambil per hari

Jalankan Skrip. Jalankan semua sel di notebook tersebut (Runtime > Run all). Skrip akan mulai proses crawling hari per hari dan menyimpan hasilnya dalam file CSV di dalam folder tweets-data.

Tunggu hingga proses selesai. Anda akan melihat folder baru bernama tweets-data di panel file sebelah kiri.

Langkah 2: Mengemas dan Mengunduh Hasil
Setelah proses crawling selesai dan folder tweets-data sudah terisi file CSV, jalankan skrip kedua untuk mengunduh semuanya.

Buka file Download_semua_hasil_crawling_menjadi_zip.ipynb di Google Colab.

Konfigurasi Nama File. Anda bisa menyesuaikan nama folder dan nama file .zip yang akan dihasilkan. Pastikan folder_to_zip sesuai dengan nama folder hasil crawling dari Langkah 1.

# Nama folder yang ingin di-zip
folder_to_zip = 'tweets-data' # Sesuaikan jika Anda mengubah nama folder

# Nama file zip yang akan dihasilkan
zip_filename = 'hasil_crawling_pemilu_2024.zip' 

Jalankan Skrip. Jalankan semua sel di notebook (Runtime > Run all). Skrip akan mengompres folder tweets-data menjadi satu file .zip dan secara otomatis memulai proses pengunduhan ke komputer Anda.

📂 Struktur Hasil
Setelah menjalankan skrip pertama, Anda akan mendapatkan struktur folder sebagai berikut di lingkungan Colab Anda:

/
|- tweets-data/
|  |- 2024_data_harian_2024-01-01.csv
|  |- 2024_data_harian_2024-01-02.csv
|  |- 2024_data_harian_2024-01-03.csv
|  |- ...dan seterusnya
|- ... file lainnya

Setelah menjalankan skrip kedua, Anda akan mengunduh satu file, misalnya hasil_crawling_pemilu_2024.zip, yang berisi semua file CSV tersebut.

🛠️ Teknologi yang Digunakan
Python

Google Colab

tweet-harvest: Alat untuk melakukan crawling data dari Twitter.

Pandas: Untuk pemrosesan data (meskipun tidak secara eksplisit digunakan untuk manipulasi di skrip ini).

