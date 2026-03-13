# Real-Time E-Commerce Streaming Pipeline & Dashboard
### Praktikum 4 - Teknologi Big Data
**Author:** Syti Masidah (230104040060)

## 📌 Deskripsi Proyek
Proyek ini mengimplementasikan sistem pengolahan data streaming secara real-time. Data transaksi disimulasikan secara incremental, diproses menggunakan **Apache Spark Structured Streaming**, disimpan ke dalam **Data Lake (Parquet)**, dan divisualisasikan melalui **Streamlit Dashboard**.

## 🛠️ Arsitektur Sistem
1. **Data Source**: Python script (`transaction_generator.py`) yang menghasilkan data transaksi format JSON secara berkelanjutan.
2. **Stream Processing**: Apache Spark yang membaca data JSON secara real-time dan melakukan transformasi.
3. **Serving Layer**: Hasil pemrosesan disimpan dalam format Parquet untuk efisiensi penyimpanan dan pembacaan.
4. **Analytics Layer**: Dashboard interaktif menggunakan Streamlit untuk menampilkan metrik bisnis secara real-time.

## 📂 Struktur Folder
```text
bigdata-project/
├── scripts/
│   ├── transaction_generator.py   # Simulator data transaksi
│   └── streaming_layer.py         # Engine Spark Streaming
├── dashboard/
│   └── dashboard_streamlit.py     # UI Dashboard Real-time
├── stream_data/                   # Folder landing data JSON (Raw)
├── data/
│   └── serving/
│       └── stream/                # Data Lake (Parquet)
├── logs/
│   └── stream_checkpoint/         # Checkpoint Spark Streaming
└── README.md

🚀 Cara Menjalankan
Pastikan environment Spark dan Python Anda sudah aktif, kemudian buka 3 terminal terpisah di VS Code:

Terminal 1: Jalankan Spark Streaming
spark-submit scripts/streaming_layer.py

Terminal 2: Jalankan Data Generator
python3 scripts/transaction_generator.py

Terminal 3: Jalankan Dashboard
streamlit run dashboard/dashboard_streamlit.py

📊 Fitur Dashboard
Key Metrics: Total Transaksi, Total Revenue, Average Transaction, dan Jumlah Kota.
Revenue by City: Grafik batang pendapatan per kota.
Top Products: Produk dengan penjualan tertinggi.
Live Transactions: Tabel transaksi terbaru yang diperbarui secara otomatis.

📝 Kesimpulan
Praktikum ini berhasil mensimulasikan alur data industri di mana data diproses saat itu juga (real-time) tanpa harus menunggu proses batch, memungkinkan pengambilan keputusan bisnis yang lebih cepat.
