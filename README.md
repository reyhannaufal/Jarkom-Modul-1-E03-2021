# Jarkom Modul 1 E03 2021
Daftar Kelompok:
1. Reyhan Naufal Rahman - 05111940000171
2. Vicky Thirdian - 05111940000211
3. Fiodhy Ardito Narawangsa - 05111940000218

## Soal dan Pembahasan
1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
  ```
  base
  ```
2. Temukan paket dari web-web yang menggunakan basic authentication method!
  ```
  base
  ```
3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
  ```
  base
  ```
4. Temukan paket mysql yang mengandung perintah query select!
  ```
  base
  ```
5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
  Masukan display filter menggunakan code dibawah ini 
  ```
  mysql contains “INSERT INTO users”
  ```
  ![image](https://user-images.githubusercontent.com/59334824/134667817-ce6fda85-6e11-4130-8d52-7874e97ac5e5.png)
  Ketika user dan password telah ditemukan, masuk ke web portal.ichimarumaru.tech dan isikan dengan user dan password yang telah didapatkan
  ![image](https://user-images.githubusercontent.com/59334824/134667753-fa29fa7a-6840-4ca2-91a1-03ff9844bf1c.png)
  
  Urutan konfigurasi T568B seperti berikut:
  
   `oranye putih - oranye - hijau putih - biru - biru putih - hijau - coklat putih - coklat`
  
  
6. Cari username dan password ketika melakukan login ke FTP Server!
 ```
  base
 ```
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
  ```
  base
  ```
8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
  ```
  base
  ```
9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
  ```
  base
  ```
10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
  ```
  base
  ```
11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 
  ```
  src port 80
  ```
  ![image](https://user-images.githubusercontent.com/59334824/134667641-5a112677-5f33-47ff-a665-b6e25a44d152.png)

12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
  ```
  base
  ```
13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
  ```
  dst port 443
  ```
  ![image](https://user-images.githubusercontent.com/59334824/134667570-6ca896c5-b01a-4ce4-841e-8a4eaa250ed9.png)

14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
  ```
  dst host kemenag.go.id
  ```
  ![image](https://user-images.githubusercontent.com/59334824/134667517-af1b1303-ffa4-46a0-8879-646d8fd266a5.png)

15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
  ```
  src host 192.168.18.6
  ```
  Mendapatkan IP dengan cara(MacOS):
  ![image](https://user-images.githubusercontent.com/59334824/134667118-0687bb44-1d73-4fbe-9fd1-4308a6270989.png)
  ![image](https://user-images.githubusercontent.com/59334824/134667282-aa9b3592-461c-40e4-bbae-3536b63927a2.png)

