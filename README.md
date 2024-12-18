<p align="center">
  <img src="https://github.com/zaidannn/Analisis-Data-Spotify/blob/main/Images/spotify.png" alt="Logo" width="200">
</p>

<h1 align="center">Analisis Data Spotify</h1>

---
### Anggota Kelompok 

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
        <td>202110370311492</td>
      </tr>
      <tr>
        <td>Muhammad Mazen Fayiz Birizqie</td>
        <td>202110370311492</td>
      </tr>
    </table>
  </div>
</p>


### Deskripsi

<p align="justify">
Data yang digunakan dalam proyek ini bertujuan untuk mengeksplorasi dan mengklasifikasikan lagu berdasarkan fitur audio yang disediakan oleh Spotify. Pengumpulan data dilakukan dengan memanfaatkan <strong>Spotify API</strong> melalui paket <em>spotifyr</em>, yang memungkinkan pengambilan metadata dan informasi audio dari berbagai lagu di platform Spotify. Dataset ini merupakan bagian dari proyek <strong>Tidytuesday</strong> yang dirilis pada 21 Januari 2020, dan mencakup sekitar 16.000 lagu. 
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


### Fitur
- Analisis statistik data Spotify
- Visualisasi data tren musik
- Interpretasi wawasan bisnis berdasarkan data

### Alur Analisis Data
## 1. Pertama, Kami melakukan gathering data dari dataset yang kami ambil dari https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-01-21/spotify_songs.csv
## 2. Setelah data berhasil load, kami melakukan assessing data pada dataset untuk mendapatkan wawasan dari dataset. Terdapat 5 kesimpulan yang kami dapatkan dari assessing data, diantaranya :
   
### Data Assessing Summary

| **Kategori**       | **Detail**                                                                                 |
|---------------------|-------------------------------------------------------------------------------------------|
| **Tipe Data**       | Terdapat kesalahan tipe data pada kolom `track_album_release_date`.                       |
| **Missing Values**  | Terdapat 5 baris missing values pada kolom `track_name`, `track_artist`, dan `track_album_name`. |
| **Duplikasi Data**  | Tidak terdapat duplikasi data.                                                            |
| **Inaccurate Data** | Pada kolom `track_name`, `track_artist`, dan `track_album_name` terdapat nilai yang berakhiran angka. |
| **Emoticon**        | Terdapat penggunaan emote pada kolom `playlist_name`.                                     |

## 3. Dari hasil assessing data yang kami temukan, selanjutnya kami melakukan cleaning data
### Cleaning data Summary

| **Variabel**               | **Deskripsi**                        | **Tipe Data** | **Keterangan & Distribusi**                                                                                     |
|----------------------------|--------------------------------------|---------------|---------------------------------------------------------------------------------------------------------------|
| `track_name`               | Nama lagu                           | String        | Beberapa nilai missing telah di-drop, hanya menyisakan lagu dengan nama yang valid. Terdapat beberapa nilai berupa angka yang telah diimputasi dan dropout. |
| `track_artist`             | Nama artis                          | String        | Nilai missing telah di-drop. Biasanya terdiri dari nama tunggal atau kolaborasi beberapa artis.                |
| `track_album_name`         | Nama album                          | String        | Beberapa nilai missing telah di-drop. Beberapa nama album hanya berupa angka telah diidentifikasi dan sebagian besar dihapus. |
| `track_album_release_date` | Tanggal rilis album                 | DateTime      | Format yang tidak konsisten telah dibersihkan. Tahun saja diubah menjadi `{tahun}-01-01`, bulan-tahun diubah menjadi `{tahun}-{bulan}-01`. |
| `playlist_name`            | Nama playlist tempat lagu berada    | String        | Terdapat penggunaan emotikon yang perlu dibersihkan untuk menjaga konsistensi data.                           |


### Teknologi yang Digunakan
- Python
- Pandas
- Matplotlib
- Seaborn

### Cara Menjalankan
1. Clone repositori ini:
   ```bash
   git clone https://github.com/zaidannn/Analisis-Data-Spotify.git
