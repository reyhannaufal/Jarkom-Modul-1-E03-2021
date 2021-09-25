# Jarkom Modul 1 E03 2021
Daftar Kelompok:
1. Reyhan Naufal Rahman - 05111940000171
2. Vicky Thirdian - 05111940000211
3. Fiodhy Ardito Narawangsa - 05111940000218

## Soal dan Pembahasan
1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
  ```
  http.host contains "ichimarumaru.tech"
  ```
  Setelah kita menggunakkan syntax tersebut kita akan mendapatkan hasil seperti ini
  ![image](https://user-images.githubusercontent.com/73778173/134756642-204905db-a6d2-472b-b18f-70fc11d22b81.png)
  
  Dari sini kita bisa follow http stream dan dari situ bisa di diketahui server: nginx/1.18.0 (Ubuntu) seperti dibawah ini
  ![image](https://user-images.githubusercontent.com/73778173/134756791-a0f71c83-a7ec-4452-bf61-e104a6fc3103.png)

2. Temukan paket dari web-web yang menggunakan basic authentication method!
  ```
  http.authbasic
  ```
  Setelah itu dapat dilihat dari authorization di bawah ini bahwa web tersebut adalah basic
  ![image](https://user-images.githubusercontent.com/73778173/134757393-d08da247-6560-491e-ae8b-987fd9cccb9a.png)

3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
  ```
  http.host contains "basic.ichimarumaru.tech"
  ```
  Dengan menggunakan syntax ini kita akan bisa melihat username dan password dari basic.ichimarumaru.tech dibagian authorization credentials yaitu username `kuncimenujulautan` dan password `tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN`
  ![image](https://user-images.githubusercontent.com/73778173/134758494-c1db1ec9-6d3b-4071-af55-9de04e3fa220.png)

  Setelah itu basic.ichimarumaru.tech akan bisa di akses dan akan memunculkan halaman dibawah ini
  ![image](https://user-images.githubusercontent.com/73778173/134758547-c82c79ba-f2dc-4820-a4ba-e6639e3acd8f.png)

  Urutan konfigurasi T568A seperti berikut:
  ```
  Putih Hijau
  Hijau
  Putih Orange
  Biru
  Putih Biru
  Orange
  Putih Coklat
  Coklat
  ```
4. Temukan paket mysql yang mengandung perintah query select!
  ```
  mysql contains "select" || mysql contains "SELECT"
  ```
  Dengan menggunakan filter tersebut kita bisa menemukan mysql yang mengandung select seperti dibawah ini
  ![image](https://user-images.githubusercontent.com/73778173/134758723-25d8ad9b-9eb7-4c0c-8ab8-a679694fe650.png)

  Lalu apabil kita menggunakan TCP stream maka dapat dilihat syntax select yang diinginkan
  ![image](https://user-images.githubusercontent.com/73778173/134758759-2e0e535f-85ee-4e34-82b9-db2d8eee373d.png)

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
  ftp.request.command == USER || ftp.request.command == PASS
 ```
 Maka didapatkan username dan password seperti dibawah ini
 ![image](https://user-images.githubusercontent.com/54606856/134765145-9d1dd903-b229-4a4c-bd18-4fbb5d80e2fe.png)
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
  ```
  frame contains "Real.pdf"
  ```
  Dari filter itu kita mencari string dengan nama Real.pdf. Sehingga didapatkan hasil filter seperti ini
  ![image](https://user-images.githubusercontent.com/54606856/134765239-84d08fb3-2c9a-449b-95b2-317fcdf4b584.png)
  Setelah itu kita dapat follow tcp stream dan show data as raw lalu simpan dengan nama real.pdf. Sehingga didapatkan file pdf yang isinya seperti dibawah ini </br>
  ![image](https://user-images.githubusercontent.com/54606856/134765433-43c724bb-f834-40e2-bd58-6bc1b3c7bc16.png)

8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
  </br>Karena ingin menunjukkan pengambilan file maka kita menggunakan RETR dengan protokol ftp
  ```
  ftp.request.command == RETR
  ```
  ![image](https://user-images.githubusercontent.com/54606856/134765619-c630ed56-1535-4a2d-b770-a5ce6928cf45.png)
9. Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
  ```
  ftp-data.command contains "secret.zip"
  ```
  ![image](https://user-images.githubusercontent.com/54606856/134765777-8216aa39-ff8b-4335-be92-ca88c59a6805.png)
  Lalu follow tcp stream dan show data as raw setelah itu disimpan dengan nama secret.zip. Yang apabila dibuka akan ada file Wanted.pdf
  ![image](https://user-images.githubusercontent.com/54606856/134765760-0afff520-3cc2-4da3-a931-22c9c1128213.png)
10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
  ```
  ftp-data.command contains "history.txt"
  ```
  Pertama kita filter paket yang mengandung string "history.txt"
  ![image](https://user-images.githubusercontent.com/54606856/134765891-ce32a101-3683-4be8-b006-a1f26b0dddd4.png)
  Lalu follow tcp stream dan didapatkan</br>
  ![image](https://user-images.githubusercontent.com/54606856/134765947-6bb0a855-db95-438f-8850-f1b322fe28f6.png)
  </br> Lalu kita filter lagi paket yang mengandung string "bukanapaapa.txt"
  ```
  ftp-data.command contains "bukanapaapa.txt"
  ```
  ![image](https://user-images.githubusercontent.com/54606856/134765981-aa90edc7-09f4-4678-ad76-9f68a0a8817f.png)
  Lalu follow tcp stream. Sehingga didapatkan passwordnya
  ![image](https://user-images.githubusercontent.com/54606856/134766020-652e91d1-2762-4d23-8dd4-8ac0953a8a30.png)
 </br>Lalu kita buka file wanted.pdf dengan password ```d1b1langbukanapaapajugagapercaya```
  ![image](https://user-images.githubusercontent.com/54606856/134766069-9709a194-64f3-4fcc-b3fb-58e05ba1afc2.png)

11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 
  ```
  src port 80
  ```
  ![image](https://user-images.githubusercontent.com/59334824/134667641-5a112677-5f33-47ff-a665-b6e25a44d152.png)

12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
  ```
  port 21
  ```
  Pertama kita akan capture filter port 21 dan akan ditampilkan seperti dibawah ini, dimana port 21 kosong karena port 21 merupakan port FTP
  ![image](https://user-images.githubusercontent.com/73778173/134758875-cf3ebdba-04ec-44e8-8e2c-363946fa5a1d.png)
  
  untuk mengetes apakah filter port 21 dapat menangkap ftp dilakukan pengetesan dengan menggunakan `ftp://ftp.adobe.com` di windows explorer seperti dibawah ini
  
  ![image](https://user-images.githubusercontent.com/73778173/134758930-91c34e02-9012-4c81-933d-20c93c7baf6c.png)

  Setelah itu dapat terlihat di wireshark bahwa port 21 dapat menangkap ftp seperti dibawah ini
  ![image](https://user-images.githubusercontent.com/73778173/134758941-c665b2d1-0412-4f99-a45c-a7f05855e57c.png)

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

