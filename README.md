📚 Praktikum Basis Data - BAB 3: Data Definition Language (DDL)

🎯 Kompetensi

1. Memahami SQL dan perintah DDL pada SQL
2. Mampu membuat tabel dengan benar beserta relationship-nya
3. Memahami type table InnoDB

📖 Topik Pembahasan

· SQL - Structured Query Language
· Membuat Table - Sintaks dan implementasi
· Constraint Relasi - Primary Key, Foreign Key, dll.
· Nilai Otomatis dan Default - Auto Increment dan Default Values

🛠️ SQL Classification

1. DDL (Data Definition Language)

Perintah untuk mendefinisikan struktur database:

· CREATE - Membuat database dan tabel
· ALTER - Mengubah struktur tabel
· RENAME - Mengubah nama tabel
· DROP - Menghapus database dan tabel

2. DML (Data Manipulation Language)

Perintah untuk memanipulasi data:

· SELECT - Menampilkan data
· INSERT - Menambah data
· UPDATE - Mengupdate data
· DELETE - Menghapus data

3. DCL (Data Control Language)

Perintah untuk mengontrol user dan hak akses:

· GRANT - Memberikan hak akses
· REVOKE - Mencabut hak akses

📋 Test Awal - Basic Database Operations

```sql
-- 1. Membuat database
CREATE DATABASE praktikum;

-- 2. Melihat seluruh database
SHOW DATABASES;

-- 3. Mengakses database
USE praktikum;

-- 4. Menghapus database
DROP DATABASE praktikum;

🗃️ Membuat Tabel

Basic Table Creation

```sql
CREATE TABLE Mahasiswa (
    NIM CHAR(11),
    Nama VARCHAR(40),
    Alamat VARCHAR(100)
);
```

Melihat Struktur Tabel

```sql
-- Melihat seluruh tabel
SHOW TABLES;

-- Melihat struktur tabel
DESC Mahasiswa;
```

🔗 Constraint Table

Jenis-jenis Constraint:

· Primary Key - Identifier unik
· Foreign Key - Relasi antar tabel
· Unique - Nilai harus unik
· Not Null - Tidak boleh kosong
· Check - Validasi nilai

Contoh Implementasi Skema Order Entry

```sql
CREATE DATABASE OrderEntry;
USE OrderEntry;

-- Tabel Vendors
CREATE TABLE Vendors (
    vend_id CHAR(4) NOT NULL PRIMARY KEY,
    vend_name VARCHAR(25) NOT NULL,
    vend_address VARCHAR(25),
    vend_city VARCHAR(20),
    vend_state VARCHAR(5),
    vend_country VARCHAR(15)
);
```

⚡ Nilai Otomatis dan Default

Auto Increment

```sql
CREATE TABLE Mahasiswa2 (
    ID INT(5) NOT NULL PRIMARY KEY AUTO_INCREMENT,
    NIM CHAR(5) NOT NULL,
    Nama_mhs VARCHAR(50),
    Jurusan VARCHAR(200),
    Fakultas VARCHAR(30)
);
```

Default Values

```sql
CREATE TABLE Mkull (
    Kode_Mkull INT(5) NOT NULL PRIMARY KEY,
    Nama_Mkull VARCHAR(50),
    SKS INT(1) DEFAULT 0,
    Semester INT(1) DEFAULT 1
);
```

🚀 Storage Engines

InnoDB vs XtraDB

· InnoDB: Default engine MySQL 5.5+, support transaction, foreign key
· XtraDB: Pengganti InnoDB di MariaDB, lebih stabil

Contoh Penggunaan

```sql
CREATE TABLE compress (
    x INT PRIMARY KEY NOT NULL,
    y VARCHAR(50) NULL
) ENGINE=InnoDB;
```

📊 Test Akhir - Skema Penjualan Barang

Entity Relationship Diagram

```
Pelanggan → Nota_Penjualan ← Detail_Jual → Barang
```

Tabel yang Harus Dibuat:

1. Pelanggan - Data customer
2. Nota_Penjualan - Transaksi penjualan
3. Barang - Data produk
4. Detail_Jual - Detail transaksi

📁 Laporan Praktikum

Format Laporan:

· Nama File: PrakDB_Bab3_NIM.odt
· Isi:
  · Source code SQL
  · Screenshot hasil eksekusi di CMD
· Penyimpanan: Folder PrakDB-NIM

