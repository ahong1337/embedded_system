# B. Transmisi Data Menggunakan Protokol HTTP

## 1. Keterangan Singkat (Abstrak)
<p align="justify">Percobaan ini dimulai dengan pembuatan database lokal "banjir_db" dan tabel "smartwater" menggunakan phpMyAdmin. Lalu diberikan kode JSON untuk flow program Multi-Protocol IoT Server yang perlu diimport di Node-RED. Selanjutnya, melalui program pada ESP32 dilakukan transmisi data dummy ke Node-Red menggunakan protokol HTTP metode GET dan protokol HTTP metode POST. Output dari percobaan ini berupa hasil dari serial monitor, debugging Node-Red, dan tampilan dashboard Node-RED.
   
## 2. Alat dan Bahan
1. Node-RED
2. ESP32
3. XAMPP

## 3. Source Code

1. Program ESP32 transmisi data dummy menggunakan protokol HTTP metode GET

  ![Alt text](<../../src/4_b/Metode GET/Penjelasan Kode.jpeg>)

2. Program ESP32 transmisi data dummy menggunakan protokol HTTP metode POST

  ![Alt text](<../../src/4_b/Metode POST/Penjelasan Kode.jpeg>)

## 4. Flow Program

  ![Alt text](<../../src/4_b/Metode GET/Flow Program.jpeg>)

## 5. Hasil Percobaan Transmisi Data Dummy Menuju Node-Red Menggunakan Protokol HTTP Metode GET

1. Flow chart program ESP32
   
  ![Alt text](<../../src/4_b/Metode GET/1. Flow Chart program ESP32.png>)
   
2. Output serial monitor
   
  ![Alt text](<../../src/4_b/Metode GET/2. Output serial monitor.jpeg>)
   
3. Debug Node-RED
   
  ![Alt text](<../../src/4_b/Metode GET/3. Debug Node-RED.jpeg>)
   
4. Dashboard Node-RED
   
  ![Alt text](<../../src/4_b/Metode GET/4. Dashboard Node-RED.jpeg>)
   
5. Tabel database MySQL
   
  ![Alt text](<../../src/4_b/Metode GET/5. Tabel database MySQL.jpeg>)

## 6. Hasil Percobaan Transmisi Data Dummy Menuju Node-Red Menggunakan Protokol HTTP Metode POST
1. Flow chart program ESP32
   
  ![Alt text](<../../src/4_b/Metode POST/1. Flow Chart program ESP32.png>)

2. Output serial monitor
   
  ![Alt text](<../../src/4_b/Metode POST/2. Output serial monitor.jpeg>)
   
3. Debug Node-RED
   
  ![Alt text](<../../src/4_b/Metode POST/3. Debug Node-RED.jpeg>)
   
4. Dashboard Node-RED
   
  ![Alt text](<../../src/4_b/Metode POST/4. Dashboard Node-RED.jpeg>)