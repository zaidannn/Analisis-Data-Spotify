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

### Fitur
- Analisis statistik data Spotify
- Visualisasi data tren musik
- Interpretasi wawasan bisnis berdasarkan data

### Alur Analisis Data
1. Pertama, Kami melakukan gathering data dari dataset yang kami ambil dari https://github.com/rfordatascience/tidytuesday/blob/main/data/2020/2020-01-21/spotify_songs.csv
2. Setelah data berhasil load, kami melakukan assessing data pada dataset untuk mendapatkan wawasan dari dataset. Terdapat 5 kesimpulan yang kami dapatkan dari assessing data, diantaranya :
   - Tipe Data --> Terdapat kesalahan tipe data pada kolom track_album_release_date
   - Missing Values --> Terdapat 5 baris missing values dimana 5 missing value

### Teknologi yang Digunakan
- Python
- Pandas
- Matplotlib
- Seaborn

### Cara Menjalankan
1. Clone repositori ini:
   ```bash
   git clone https://github.com/zaidannn/Analisis-Data-Spotify.git
