# Kafka Bitcoin Producer
Producer Python untuk mengirimkan data harga Bitcoin ke Apache Kafka. 

## Deskripsi
Projek ini bertujuan untuk membaca data harga Bitcoin dari file CSV dan mengirimkannya ke topik Kafka menggunakan Avro.

### Persyaratan

- Python 3.5
- Kafka broker berjalan (lihat `docker-compose.yaml`)
- Schema Registry berjalan (lihat `docker-compose.yaml`)
- `pip` untuk menginstal dependensi

### Instalasi

1. Pastikan Kafka dan Schema Registry sudah berjalan menggunakan Docker Compose:
    ```bash
    docker-compose up -d
    ```
2. Buat environment baru dan instal dependensi:
    ```bash
    python -m venv env
    env\Scripts\activate   # Untuk Windows
    source env/bin/activate  # Untuk macOS/Linux
    pip install -r requirements.txt
    ```
3. Siapkan file konfigurasi `.env` dengan konfigurasi Kafka dan Schema Registry:
    ```
    BOOTSTRAP_SERVERS=localhost:9092
    SCHEMA_REGISTRY_URL=http://localhost:8081
    TOPIC_NAME=bitcoin_price
    ```

## Penggunaan
1. Pastikan Kafka broker dan Schema Registry sudah berjalan.
2. Aktifkan environment:
    ```bash
    env\Scripts\activate   # Untuk Windows
    source env/bin/activate  # Untuk macOS/Linux
    ```
3. Jalankan producer:

    ```bash
    python producer_bitcoin.py
    ```
