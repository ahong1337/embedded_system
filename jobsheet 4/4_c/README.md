# C. Transmisi Data Menggunakan Protokol MQTT

## 1. Keterangan Singkat (Abstrak)
<p align="justify">Dalam percobaan ini, program ESP32 memanfaatkan protokol MQTT untuk mentransmisikan data dummy, seperti level, rainfall, dan flow. Server broker MQTT yang digunakan adalah layanan EMQ X, yang merupakan platform perangkat lunak open-source untuk implementasi MQTT. Setelah program diupload, dilakukan pemantauan melalui serial monitor untuk memastikan koneksi dan debug pada Node-Red. Hasil output dari percobaan ini meliputi data yang dipublikasikan ke topik "flood/node1", serta visualisasi data pada dashboard Node-Red.
   
## 2. Alat dan Bahan
1. Node-RED
2. ESP32
3. XAMPP

## 3. Source Code

1. Program ESP32

  ![Alt text](<../../src/4_c/Penjelasan Kode.jpeg>)

## 4. Flow Program

  ![Alt text](<../../src/4_b/Metode POST/Flow Program.jpeg>)

## 5. Hasil & Pembahasan
### Dokumentasi Hasil

1. Flow chart program ESP32
   
  ![Alt text](<../../src/4_c/Flow Chart.png>)
   
2. Output serial monitor
   
  ![Alt text](<../../src/4_c/2. Output serial monitor.jpeg>)
   
3. Debug Node-RED
   
  ![Alt text](<../../src/4_c/3. Debug Node-RED.jpeg>)
   
4. Dashboard Node-RED
   
  ![Alt text](<../../src/4_c/4. Dashboard Node-RED.jpeg>)

### Penjelasan Kode

  ![Alt text](<../../src/4_c/Penjelasan Kode.jpeg>)

Kode di atas adalah program ESP32 yang menggunakan modul WiFi untuk mengirimkan data melalui protokol MQTT ke suatu server MQTT publik broker.emqx.io. Berikut penjelasan singkat untuk setiap bagian dari kode tersebut:

1. **Inklusi Library:**
   ```cpp
   #include <WiFi.h>
   #include <PubSubClient.h>
   #include <ArduinoJson.h>
   ```
   Library WiFi.h digunakan untuk mengelola koneksi WiFi, library PubSubClient.h untuk mengimplementasikan klien MQTT, dan library ArduinoJson.h untuk memproses dan membangun data JSON.

2. **Konfigurasi Koneksi WiFi dan MQTT Server:**
   ```cpp
   const char* ssid = "KENTUNGERS";
   const char* password = "KentungMustofa";
   const char* mqtt_server = "broker.hivemq.com";
   ```
   Nama dan kata sandi WiFi, serta alamat MQTT broker yang digunakan.

3. **Inisialisasi Objek Klien WiFi dan MQTT:**
   ```cpp
   WiFiClient espClient;
   PubSubClient client(espClient);
   ```
   Inisialisasi objek klien WiFi dan klien MQTT dengan menggunakan objek klien WiFi.

4. **Fungsi Setup WiFi:**
   ```cpp
   void setup_wifi() {
     // ...
   }
   ```
   Fungsi ini menginisialisasi koneksi WiFi. Menunggu koneksi ke jaringan WiFi dan mencetak informasi IP setelah terkoneksi.

5. **Fungsi Reconnect MQTT:**
   ```cpp
   void reconnect() {
     // ...
   }
   ```
   Fungsi ini mencoba kembali terhubung ke broker MQTT jika koneksi terputus.

6. **Fungsi Setup:**
   ```cpp
   void setup() {
     // ...
   }
   ```
   Fungsi setup yang pertama kali dijalankan saat perangkat dinyalakan. Memulai serial, menginisialisasi koneksi WiFi, dan mengatur server MQTT.

7. **Fungsi Loop:**
   ```cpp
   void loop() {
     // ...
   }
   ```
   Fungsi loop yang berjalan terus-menerus setelah fungsi setup selesai. Jika koneksi MQTT terputus, akan mencoba kembali terhubung. Membaca data sensor (dalam bentuk objek JSON) dan mengirimkannya melalui MQTT setiap 10 detik.

8. **Pengiriman Data MQTT:**
   ```cpp
   char payload[200];
   StaticJsonBuffer<200> jsonBuffer;
   JsonObject& doc = jsonBuffer.createObject();
   doc["dev_id"] = 28;
   doc["level"] = 25;
   doc["rainfall"] = 5.25;
   doc["flow"] = 10;
   doc.printTo(payload);
   client.publish("flood/node1", payload);
   delay(10000);
   ```
   Bagian ini membuat objek JSON menggunakan ArduinoJson, mengonversi objek JSON tersebut menjadi string, dan kemudian mengirimkannya ke topik "flood/node1" pada broker MQTT. Data ini dikirim setiap 10 detik dengan menggunakan delay.
