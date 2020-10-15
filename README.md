#  Lapres Modul 1 Jarkom 2020

**Oleh Kelompok A01 :**
- Wisnu (05111740000170)
- Salsabila Harlen (05111840000127)

## Display Filter
**1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!!**
- Menggunakan syntax `http.host == " testing.mekanis.me"` untuk Menampilkan semua paket dengan protokol HTTP yang host nya mengandung " testing.mekanis.me"

![Alt Text](/img/no1.jpg)

- Pilih salah satu file dari hasil filter tadi lalu klik kanan untuk memilih menu Follow -> TCP Stream. Kemudian tulis server di menu text filter maka akan terlihat web server yang dipakai adalah Nginx/1.14.0 (Ubuntu).

![Alt Text](/img/no1.2.jpg)

![Alt Text](/img/no1.3.jpg)

**2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!**
- Buka menu file ->Export Object-> HTTP Object List lalu masukkan nama file yang akan dicari di text filter. Kemudian, mencari Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg. Kemudian, save as/save untuk menyimpan gambar.

![Alt Text](/img/no2.jpg)

![Alt Text](/img/no2.2.jpg)

**3. Cari username dan password ketika login di "ppid.dpr.go.id"!**
- Menggunakan Syntax `http.request.method == POST && http.host == " ppid.dpr.go.id "` setelah itu cari menu HTML Form URL Encoded di packet details panel/detail paket data. 
- Lalu, bisa dilihat bahwa user untuk login = "10pemuda" dan password = "guncangdunia".

![Alt Text](/img/no3.jpg)

**4. Temukan paket dari web-web yang menggunakan basic authentication method!**
- Menggunakan Syntax `http.authbasic`

![Alt Text](/img/no4.jpg)

**5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!**
- Menggunakan syntax `http.host ==  "aku.pengen.pw"`

![Alt Text](/img/no5.jpg)

![Alt Text](/img/no5.2.jpg)

![Alt Text](/img/no5.3.jpg)

![Alt Text](/img/no5.4.jpg)

**6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).**
- Menggunakan syntax `ftp-data.command contains zipkey.txt` untuk menfilter

![Alt Text](/img/no6.jpg)

- Lalu, follow TCP Stream, dan terdapat string berupa hey997400323051 yang merupakan password dari Answer.zip

![Alt Text](/img/no6.2.jpg)

- Kemudian, untuk mencari file Answer.pdf, menggunakan syntax `ftp-data.command contains Answer.zip`

![Alt Text](/img/no6.3.jpg)

- Setelah paket ditemukan, follow TCP Stream, dan Show and save data as RAW, dan disimpan dengan nama file Answer.zip

![Alt Text](/img/no6.4.jpg)

- Ekstrak file tersebut dengan menggunakan password hey997400323051. Lalu, buka file nya Open This.pdf

![Alt Text](/img/no6.5.jpg)

**7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"**
- Menggunakan syntax` ftp-data contains Yes.pdf`

![Alt Text](/img/no7.jpg)

- Lalu, klik kanan untuk follow TCP Stream, Show dan save data as RAW, kemudian disimpan dengan nama file 473.zip

![Alt Text](/img/no7.2.jpg)

- Ekstrak file tersebut, dan ditemukan Yes.pdf. Kemudian, buka file Yes.pdf

![Alt Text](/img/no7.3.jpg)

**8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!**
- Menggunakan syntax `ftp contains Microsoft` untuk mencari ip destination dari koneksi FTP dengan Microsoft FTP Service. Kemudian, klik kanan, dan klik Apply as Filter - Selected

![Alt Text](/img/no8.jpg)

- Menambahkan filter dengan menggunakan syntax `ftp.request.command == RETR && ip.dst == 198.246.117.106` untuk mencari file yang didownload. Maka ditemukan file yang didownload adalah Readme

![Alt Text](/img/no8.2.jpg)

**9. Cari username dan password ketika login FTP pada localhost!**
- Menggunakan syntax `ftp.request.command == USER || ftp.request.command == PASS`

![Alt Text](/img/no9.jpg)

**10. Cari file .pdf di wireshark lalu download dan buka file tersebut!! clue: "25 50 44 46"**
- Mencari menggunakan hex value dengan ctrl f, dan memasukkan hex value 25 50 44 96, lalu klik find
- Lalu follow tcp stream, dijadikan raw, kemudian di download
- Buka file yang sudah di download

![Alt Text](/img/no10.jpg)


![Alt Text](/img/no10.2.jpg)


![Alt Text](/img/no10.3.jpg)


## Capture Filter
**11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!**
- syntax: `port 21`

![Alt Text](/img/no11.jpg)

**12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!**
- syntax: `src port 80`

![Alt Text](/img/no12.jpg)

**13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!**
- syntax: `dst port 443`

![Alt Text](/img/no13.jpg)

**14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!**
- Mencari ipnya dengan membuka cmd > lalu ketik ipconfig

![Alt Text](/img/no14.jpg)

- ip ditemukan: 192.168.1.11
- syntax: `ip src 192.168.1.11`

![Alt Text](/img/no14.2.jpg)

**15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!**
- syntax: `dst host monta.if.its.ac.id`

![Alt Text](/img/no15.jpg)


 
