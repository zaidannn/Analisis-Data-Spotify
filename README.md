<p align="center">
  <img src="https://github.com/zaidannn/Analisis-Data-Spotify/blob/main/Images/spotify.png" alt="Logo" width="200">
</p>

<h1 align="center">Analisis Data Spotify</h1>

---
## Anggota Kelompok 

<p align="center">
  <div style="text-align: center;">
    <table border="1" style="margin: auto;">
      <tr>
        <th>Nama Anggota</th>
        <th>NIM</th>
      </tr>
      <tr>
        <td>Muhammad Zaidan Naufal Fikri</td>
        <td>202110370311492</td>
      </tr>
      <tr>
        <td>Hadi Dwi Ardiansyah</td>
        <td>202110370311520</td>
      </tr>
      <tr>
        <td>Muhammad Mazen Fayiz Birizqie</td>
        <td>202110370311513</td>
      </tr>
    </table>
  </div>
</p>


## Deskripsi

<p align="justify">
Data yang digunakan dalam proyek ini bertujuan untuk mengeksplorasi dataset Spotify. Pengumpulan data dilakukan dengan memanfaatkan <strong>Spotify API</strong> melalui paket <em>spotifyr</em>, yang memungkinkan pengambilan metadata dan informasi audio dari berbagai lagu di platform Spotify. Dataset ini merupakan bagian dari proyek <strong>Tidytuesday</strong> yang dirilis pada 21 Januari 2020, dan mencakup sekitar 32.780 lagu. 
</p>
<p align="justify">Dataset dapat diakses di link berikut : https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-01-21/spotify_songs.csv </p>

<p align="justify">
Setiap lagu dalam dataset dilengkapi dengan 23 variabel yang memberikan gambaran menyeluruh tentang karakteristik audio dan informasi pendukung lainnya. Variabel-variabel tersebut mencakup nama lagu (<em>track_name</em>), nama artis (<em>artist_name</em>), ID lagu (<em>track_id</em>), nama album (<em>album_name</em>), dan berbagai fitur audio seperti <em>danceability</em>, <em>energy</em>, <em>valence</em>, <em>tempo</em>, dan <em>loudness</em>. Selain itu, dataset ini juga memuat informasi tentang genre dan tingkat popularitas lagu, memberikan konteks tambahan untuk analisis yang lebih dalam. Dengan kombinasi data ini, proyek bertujuan untuk menggali wawasan baru mengenai pola dan tren musik, mengklasifikasikan lagu berdasarkan karakteristik uniknya, serta memberikan interpretasi yang relevan terhadap industri musik modern.
</p>

### Variabel dan Deskripsi Dataset

| **Variabel**              | **DType**   | **Deskripsi**                                                                                           |
|---------------------------|-------------|---------------------------------------------------------------------------------------------------------|
| `track_id`                | karakter    | ID unik lagu.                                                                                          |
| `track_name`              | karakter    | Nama lagu.                                                                                            |
| `track_artist`            | karakter    | Artis lagu.                                                                                           |
| `track_popularity`        | integer     | Popularitas lagu (0-100), semakin tinggi nilainya, semakin populer lagu tersebut.                      |
| `track_album_id`          | karakter    | ID unik album.                                                                                        |
| `track_album_name`        | karakter    | Nama album lagu.                                                                                      |
| `track_album_release_date`| karakter    | Tanggal rilis album.                                                                                  |
| `playlist_name`           | karakter    | Nama playlist.                                                                                        |
| `playlist_id`             | karakter    | ID playlist.                                                                                          |
| `playlist_genre`          | karakter    | Genre playlist.                                                                                       |
| `playlist_subgenre`       | karakter    | Subgenre playlist.                                                                                    |
| `danceability`            | float       | Mengukur kecocokan lagu untuk menari berdasarkan elemen musik seperti tempo, ritme, dan kekuatan ketukan (0.0 = tidak cocok, 1.0 = sangat cocok). |
| `energy`                  | float       | Menggambarkan intensitas dan aktivitas lagu (nilai tinggi = lagu intens seperti metal, nilai rendah = lagu tenang seperti musik klasik). |
| `key`                     | integer     | Kunci umum lagu (0 = C, 1 = C♯/D♭, 2 = D, dst).                                                       |
| `loudness`                | float       | Tingkat kerasnya lagu dalam desibel (dB), dengan rentang antara -60 hingga 0 dB.                       |
| `mode`                    | integer     | Mode skala lagu (1 = mayor, 0 = minor).                                                               |
| `speechiness`             | float       | Mengukur kehadiran kata-kata yang diucapkan (1.0 = banyak berbicara, seperti talk show atau buku audio).|
| `acousticness`            | float       | Kepercayaan apakah lagu bersifat akustik (0.0 = tidak akustik, 1.0 = sangat akustik).                 |
| `instrumentalness`        | float       | Memprediksi apakah lagu tidak mengandung vokal (nilai >0.5 = lagu instrumental).                      |
| `liveness`                | float       | Mengukur kehadiran audiens dalam rekaman (nilai >0.8 = kemungkinan rekaman langsung).                  |
| `valence`                 | float       | Mengukur sejauh mana lagu menyampaikan perasaan positif (nilai tinggi = ceria, nilai rendah = murung). |
| `tempo`                   | float       | Tempo lagu dalam ketukan per menit (BPM).                                                             |
| `duration_ms`             | integer     | Durasi lagu dalam milidetik.                                                                          |

## Berdasarkan deskripsi dataset, kami penyusun beberapa pernyataan masalah diantaranya :

1. Genre playlist apa yang paling populer?
2. Bagaimana performa popularitas lagu di setiap tahunnya, baik secara umum maupun untuk setiap genre?
3. Genre apa yang paling populer di 5 tahun awal dan 5 tahun terakhir?
4. Bagaimana fitur audio (danceability, tempo, valence, energy) memengaruhi popularitas lagu di berbagai genre?
5. Siapa artis atau album yang paling banyak dimasukkan ke playlist?
6. Bagaimana perilaku pengguna dalam membuat playlist (genre serupa vs. genre campuran)?
7. Bagaimana distribusi popularitas lagu berdasarkan tahun rilis?

## Alur Analisis Data
### 1. Pertama, Kami melakukan gathering data dari dataset yang kami ambil dari 
https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-01-21/spotify_songs.csv
### 2. Setelah data berhasil di load, kami melakukan assessing data pada dataset untuk mendapatkan informasi yang ada dari dataset. Terdapat 5 kesimpulan yang kami dapatkan dari assessing data, diantaranya :
   
### Data Assessing Summary

| **Kategori**       | **Detail**                                                                                 |
|---------------------|-------------------------------------------------------------------------------------------|
| **Tipe Data**       | Terdapat kesalahan tipe data pada kolom `track_album_release_date`.                       |
| **Missing Values**  | Terdapat 5 baris missing values pada kolom `track_name`, `track_artist`, dan `track_album_name`. |
| **Duplikasi Data**  | Tidak terdapat duplikasi data.                                                            |
| **Inaccurate Data** | Pada kolom `track_name`, `track_artist`, dan `track_album_name` terdapat nilai yang berakhiran angka. |
| **Emoticon**        | Terdapat penggunaan emote pada kolom `playlist_name`.                                     |

### 3. Dari hasil assessing data yang kami temukan, selanjutnya kami melakukan cleaning data
### Cleaning data Summary

| **Variabel**               | **Deskripsi**                        | **Tipe Data** | **Keterangan & Distribusi**                                                                                     |
|----------------------------|--------------------------------------|---------------|---------------------------------------------------------------------------------------------------------------|
| `track_name`               | Nama lagu                           | String        | Beberapa nilai missing telah di-drop, hanya menyisakan lagu dengan nama yang valid. Terdapat beberapa nilai berupa angka yang telah diimputasi dan dropout. |
| `track_artist`             | Nama artis                          | String        | Nilai missing telah di-drop. Biasanya terdiri dari nama tunggal atau kolaborasi beberapa artis.                |
| `track_album_name`         | Nama album                          | String        | Beberapa nilai missing telah di-drop. Beberapa nama album hanya berupa angka telah diidentifikasi dan sebagian besar dihapus. |
| `track_album_release_date` | Tanggal rilis album                 | DateTime      | Format yang tidak konsisten telah dibersihkan. Tahun saja diubah menjadi `{tahun}-01-01`, bulan-tahun diubah menjadi `{tahun}-{bulan}-01`. |
| `playlist_name`            | Nama playlist tempat lagu berada    | String        | Terdapat penggunaan emotikon yang perlu dibersihkan untuk menjaga konsistensi data.                           |

### 4. Setelah melakukan cleaning pada data, selanjutnya kami mengeskplorasi dataset untuk mengaanalisis informasi yang terdapat pada dataset. 

### Ringkasan Dataset

| **Atribut**               | **Deskripsi**                                                                              |
|---------------------------|--------------------------------------------------------------------------------------------|
| **Total Lagu**            | 32.780                                                                                     |
| **Rentang Popularitas**   | 0 - 100                                                                                    |
| **Rata-rata Popularitas** | 42,48                                                                                      |
| **Standar Deviasi Popularitas** | 24,98                                                                                |
| **Rentang Durasi Lagu**   | 0,07 menit (terpendek) - 8,63 menit (terpanjang)                                           |
| **Rata-rata Durasi Lagu** | 3,76 menit                                                                                 |

Dataset ini menunjukkan variasi yang signifikan dalam popularitas dan durasi lagu, sehingga menawarkan beragam karakteristik musik untuk dianalisis.

### Pertama, kami coba lihat genre playlist yang paling populer
genre playlist yang paling populer adalah genre edm dan Genre EDM relatif lebih baru dibandingkan dengan genre lainnya, meskipun edm paling populer, lagu-lagu dalam genre pop dan latin memiliki popularitas yang lebih tinggi. Genre R&B dan Rock memiliki sejarah yang panjang, dengan album-album yang dirilis sejak tahun 1957.

### Selanjutnya, 🤔 bagaimana dengan performa popularitas lagu disetiap tahunnya❓
berdasarkan hasil analisis, tren popularitas lagu per tahun, terlihat adanya fluktuasi. Meskipun tidak ada penurunan tren yang signifikan secara konsisten, terdapat periode-periode tertentu di mana rata-rata popularitas mengalami penurunan.

### 🤔 Bagaimana dengan performa popularitas lagu disetiap tahunnya untuk setiap genre❓
Dan dari tahun ke tahun grafik menunjukan pola yang semakin lama rata-rata popularitasnya memadat direntang 60-30, hal ini menunjukan bahwa dari tahun ke tahun tren musik akan semakin beragam dan kompetitif. Popularitas lagu tidak lagi didominasi oleh satu atau dua genre saja, tetapi tersebar lebih merata di berbagai genre. Meskipun genre tertentu mungkin masih mendominasi secara keseluruhan, perbedaan popularitas antar genre cenderung berkurang seiring waktu, yang menunjukkan pasar musik yang lebih beragam.

### 🤔Genre manakah yang paling populer di 5 tahun awal dan 5 tahun terakhir❓
genre paling populer di 5 tahun awal r&b dan di 5 tahun terakhir terdapat r&b dan pop, genre rap dan pop muncul di 5 tahun terakhir dan tidak ada di 5 tahun awal. Hal ini menandakan tentang pergeseran tren musik dari waktu ke waktu. Serta penurunan popularitas pada genre rock, dimana genre rock lebih populer di 5 tahun awal dibanding 5 tahun terakhir.

### 🤔 Bagaimana fitur audio (dancebility, tempo, valensi, energi) memengaruhi popularitas lagu (track_popularity) dalam berbagai playlist_genre❓
1. Musik EDM cenderung memiliki energi tinggi dan tempo cepat, tetapi popularitasnya lebih rendah dibandingkan genre lain seperti latin atau pop.
2. Genre Latin memiliki tingkat danceability dan valence yang tinggi, mencerminkan karakteristik musik yang ceria dan energik. Popularitasnya cukup tinggi.
3. Musik pop memiliki popularitas tertinggi karena sifatnya yang fleksibel dan mudah diterima oleh berbagai kalangan pendengar.
4. R&B memiliki tempo lebih lambat dengan energy sedang, cocok untuk pendengar yang mencari musik yang lebih emosional dan santai.
5. Genre rap memiliki danceability tertinggi, yang menunjukkan kuatnya elemen ritme dalam genre ini, meskipun popularitasnya tidak setinggi pop atau latin.
6. Rock memiliki energi tinggi tetapi danceability rendah, menunjukkan fokusnya pada intensitas musik daripada aspek tarian.

### 🤔 Siapa artis atau album yang paling banyak dimasukkan ke playlist❓
## Artis Teratas

| **Peringkat** | **Artis**                  |
|---------------|----------------------------|
| 1             | Martin Garrix             |
| 2             | Queen                     |
| 3             | The Chainsmokers          |
| 4             | David Guetta              |
| 5             | Don Omar                  |
| 6             | Drake                     | 
| 7             | Dimitri Vegas & Like Mike | 
| 8             | Calvin Harris             |                          
| 9             | Hardwell                  | 
| 10            | Kygo                      | 

## Album Teratas

| **Peringkat** | **Album**                    | 
|---------------|------------------------------|
| 1             | Greatest Hits               | 
| 2             | Ultimate Freestyle Mega Mix | 
| 3             | Gold                        | 
| 4             | Malibu                      | 
| 5             | Rock & Rios (Remastered)    | 
| 6             | X 100PRE                    | 
| 7             | Appetite For Destruction    |
| 8             | Forever                     |
| 9             | Views                       | 
| 10            | Hollywood's Bleeding        | 

Tabel ini memberikan gambaran tentang artis dan album dengan jumlah penampilan tertinggi dalam dataset.

### 🤔 Bagaimana perilaku pengguna terhadap playlist yang mereka buat? apakah pengguna cenderung membuat playlist dengan genre yang serupa, atau apakah mereka mencampurkan berbagai genre❓
pada hasil data dan visualisasi pada file ipynb disimpulkan bahwa playlist cenderung lebih banyak berisi genre serupa yakni dengan jumlah 441, dan untuk yang playlist berisi genre campuran hanya berjumlah 5

### 🤔 Bagaimana distribusi popularitas lagu berdasarkan tahun rilis❓
1. Tren Positif Popularitas Lagu. Lagu dengan keluaran tahun 2010 ke atas cenderung populernya meningkat seiring dengan waktu, dan paling mendominasi pada periode 2015-2020
2. Lagu Lama Kurang Mendapat Perhatian. Lagu Lama Kurang Mendapatkan popularitasnya terutama pada lagu keluaran sebelum tahun 2010 yang memiliki kontribusi yang lebih kecil terhadap popularitas dibandingkan lagu-lagu yang lebih baru.

## Kesimpulan 
### Wawasan Menarik
- Genre EDM paling populer dalam hal jumlah playlist, namun popularitas lagu-lagunya lebih rendah dibanding genre lain seperti Pop dan Latin.
- Popularitas lagu cenderung menurun seiring waktu, menunjukkan persaingan yang semakin ketat di industri musik.
- Genre Pop dan R&B tetap populer di awal dan akhir periode pengamatan, sedangkan genre Rap dan Latin semakin populer di tahun-tahun terakhir.
- Fitur audio seperti danceability, energy, dan valence memiliki pengaruh yang berbeda terhadap popularitas lagu di berbagai genre.
- Martin Garrix dan Queen adalah artis yang paling banyak muncul di playlist, sedangkan Greatest Hits dan Ultimate Freestyle Mega Mix adalah album yang paling banyak muncul.
- Pengguna cenderung membuat playlist dengan genre yang serupa daripada mencampur berbagai genre.
- Lagu yang dirilis setelah tahun 2010 cenderung lebih populer dibandingkan lagu-lagu yang lebih lama.

### Implikasi bagi Konsumen
- Genre Pop tetap menjadi pilihan populer bagi konsumen yang mencari musik yang mudah didengarkan.
- Genre Latin semakin diminati, dan konsumen mungkin ingin mengeksplorasi genre ini lebih jauh.
- Fitur audio dapat menjadi pertimbangan bagi konsumen dalam memilih lagu, tergantung preferensi mereka.
- Artis dan album yang sering muncul di playlist dapat menjadi indikator popularitas dan kualitas bagi konsumen.
- Konsumen dapat membuat playlist dengan genre serupa sesuai preferensi mereka.
  
### Keterbatasan dan Pengembangan
- Dataset terbatas pada lagu-lagu di Spotify, dan tidak mewakili seluruh industri musik.
- Analisis tidak mempertimbangkan faktor-faktor lain yang dapat memengaruhi popularitas lagu, seperti pemasaran dan promosi.
- Analisis dapat dikembangkan dengan menggunakan dataset yang lebih besar dan mencakup data dari platform musik lain.
- Pemodelan prediktif dapat digunakan untuk memprediksi popularitas lagu di masa depan.
- 
### Teknologi yang Digunakan
- Python
- Pandas
- Matplotlib
- Seaborn

## Visualisasi Data
Dapat diakses pada file [Tugas_Akhir_v2.ipynb](https://github.com/zaidannn/Analisis-Data-Spotify/blob/main/Code/Tugas_Akhir_v2.ipynb)
