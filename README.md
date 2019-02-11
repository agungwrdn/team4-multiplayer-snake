# team4-multiplayer-snake
#Starting Point
- Download Intaller Here https://nodejs.org/en/download/
- Download Git Here https://git-scm.com/downloads

#How To Get
- git clone https://github.com/agungwrdn/team4-multiplayer-snake.git

#Installing
#Windows
- open nedejs terminal
- git clone https://github.com/agungwrdn/team4-multiplayer-snake.git
- cd ./team4-multiplayer-snake.git
- npm install

#MAC
- open terminal
- cd ./team4-multiplayer-snake.git
- npm install

#how to run
- npm start
- open in browser http://127.0.0.1:3000

#Documentation Code
-|public
-|     |asset
-|         |css
-|            |style.css
-|         |js
-|            |client.js
-|     |index.html
-|server
-|    |server.js
-|    |setting.js
-|    |snake.js
-|app.js

- folder public berisikan source yang bisa dikonsumsi oleh public atau client
  - client.js berfungsi sebagai perantara interaksi response dari server menuju ke tampilan user.
- folder server berisikan source core untuk server lebih tepatnya sebagai proses yang disimpan di server untuk menggerakan object dan memberika perintah dari input yang diterima di arahkan ke bagian user 
- app.js sebagai tempat pendeklarasian server dan sebagain runner nodejs tersendiri

#Function yang ada 
- client.js
  - initGame() // sebagai inisialisasi apa saja yang akan digunakan
  - buttonInput() // sebagai input username, checking kondisi username dan check user limit dan menghapus beberapa tampilan jika username berhasil di masukkan
  - addPlayerScore() // sebagai menambah score list di table score
  - updateScoreboard() // untuk mengupdate score board yang ada di list score yang telah di buat
  - renderBoard() // menampilkan tampilan di bagian board seperti area, ularnya, makananya 
- server.js
  - initServer() // sebagai inisialisai koneksi socketio dan deklarasi class snake
  - variable connection // berisikan fungsi untuk menerima response dari emiter socket io berdasarkan nama
  - gameEvent() // sebagai melemparkan event yang diterima ke sisi client side
- setting.js
  - berisikan boardSize yang dimunculkan dan warna untuk snake/karakter user
- snake.js
  - constructor() //adalah spesial method untuk pembuatan dan penginisialisasian objek yang dibuat dengan kelas
  - addPlayer() // untuk melakukan set warna pada ularnya, menginisialisai data player, menentukan lokasi muncul saat pertama kali 
  - killPlayer() // dimana mereset kondisi user ke kondi awal permainan, dan respawn user
  - removePlayer() // menghilangkan data user dari socketio disaat kondisi socketio terputus atau browser tertutup
  - createBoard() // 
  - setListener() // menerima kejadian kejadian yang ada
  - movePlayer() // mengatur gerak dari snake dan mengecek kondisi snake dalam kondisi kepala menyentuh badan atau tidak jika iya dia akan masuk killPlayer()
  - spawnFood() // memunculkan makanan dengan kondisinya
  - keyStroke() // menerima kondisi arah yang di request dari client ke server dan outpunya yaitu gerak snake
  - gameUpdate() // dimana kondisi terbaru akan dilempar dari fungsi ini dari gerak, makanan, hingga close
