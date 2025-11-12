
# 🧩 Praktikum 7: PHP Dasar  
**Nama:** _(isi namamu)_  
**NIM:** _(isi NIM-mu)_  
**Kelas:** _(isi kelasmu)_  

---

## 🎯 Tujuan
1. Memahami konsep dasar *Server Side Scripting*.  
2. Memahami dasar pemrograman PHP.  
3. Memahami variabel dan tipe data pada PHP.  
4. Memahami struktur kondisi dan perulangan dalam PHP.  
5. Mampu membuat program PHP sederhana.

---

## 🧰 Persiapan
1. Instal dan jalankan **XAMPP**.  
2. Pastikan modul **Apache** aktif.  
3. Buat folder baru di direktori:
   ```
   xampp/htdocs/lab7_php_dasar/
   ```
4. Gunakan **VSCode** atau text editor lainnya untuk menulis kode PHP.

---

## 🧪 Langkah-langkah Praktikum

### 1️⃣ Membuat File Pertama `php_dasar.php`
```php
<!DOCTYPE html>
<html>
<head>
    <title>PHP Dasar</title>
</head>
<body>
    <h1>Belajar PHP Dasar</h1>
    <?php
        echo "Hello World";
    ?>
</body>
</html>
```
**Hasil:** Menampilkan tulisan **“Hello World”** di browser.

---

### 2️⃣ Variabel PHP
```php
<?php
$nim = "0411500400";
$nama = "Abdullah";
echo "NIM : $nim <br>";
echo "Nama : $nama";
?>
```
**Penjelasan:** Variabel di PHP diawali dengan tanda `$` dan dapat menyimpan berbagai tipe data.

---

### 3️⃣ Form Input dan `$_POST`
```php
<!DOCTYPE html>
<html>
<head>
    <title>Form Input</title>
</head>
<body>
<form method="post">
    <label>Nama: </label>
    <input type="text" name="nama">
    <input type="submit" value="Kirim">
</form>
<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```
**Penjelasan:** Menggunakan **method POST** untuk mengirim data dari form ke server.

---

### 4️⃣ Operator dan Struktur Kondisi
```php
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji * $pajak);
echo "Gaji sebelum pajak = Rp. $gaji <br>";
echo "Gaji yang dibawa pulang = Rp. $thp";
?>
```
```php
<?php
$nama_hari = date("l");
if ($nama_hari == "Sunday") {
    echo "Minggu";
} elseif ($nama_hari == "Monday") {
    echo "Senin";
} else {
    echo "Hari lainnya";
}
?>
```
**Penjelasan:** Digunakan untuk membuat logika pengambilan keputusan berdasarkan kondisi tertentu.

---

### 5️⃣ Perulangan
```php
<?php
for ($i=1; $i<=5; $i++) {
    echo "Perulangan ke-$i <br>";
}
?>
```
**Penjelasan:** Menjalankan blok kode secara berulang berdasarkan jumlah iterasi.

---

### 6️⃣ Tugas: Program PHP Sederhana
```php
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Form Data Diri</title>
</head>
<body>
    <h2>Form Input Data Diri</h2>
    <form method="post" action="">
        <label>Nama:</label><br>
        <input type="text" name="nama" required><br><br>

        <label>Tanggal Lahir:</label><br>
        <input type="date" name="tgl_lahir" required><br><br>

        <label>Pekerjaan:</label><br>
        <select name="pekerjaan" required>
            <option value="">-- Pilih Pekerjaan --</option>
            <option value="Programmer">Programmer</option>
            <option value="Desainer">Desainer</option>
            <option value="Guru">Guru</option>
            <option value="Dokter">Dokter</option>
            <option value="Mahasiswa">Mahasiswa</option>
        </select><br><br>

        <input type="submit" value="Tampilkan">
    </form>
    <hr>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $nama = $_POST['nama'];
        $tgl_lahir = $_POST['tgl_lahir'];
        $pekerjaan = $_POST['pekerjaan'];

        $lahir = new DateTime($tgl_lahir);
        $hari_ini = new DateTime();
        $umur = $hari_ini->diff($lahir)->y;

        switch ($pekerjaan) {
            case "Programmer": $gaji = 8000000; break;
            case "Desainer": $gaji = 6000000; break;
            case "Guru": $gaji = 5000000; break;
            case "Dokter": $gaji = 10000000; break;
            default: $gaji = 0;
        }

        echo "<h3>Hasil Data:</h3>";
        echo "Nama: <strong>$nama</strong><br>";
        echo "Tanggal Lahir: <strong>$tgl_lahir</strong><br>";
        echo "Umur: <strong>$umur tahun</strong><br>";
        echo "Pekerjaan: <strong>$pekerjaan</strong><br>";
        echo "Gaji: <strong>Rp " . number_format($gaji, 0, ',', '.') . "</strong><br>";
    }
    ?>
</body>
</html>
```
**Penjelasan:**
- Mengambil input dari form (nama, tanggal lahir, pekerjaan).  
- Menghitung umur menggunakan kelas `DateTime`.  
- Menentukan gaji dengan `switch`.  
- Menampilkan hasil di bawah form.

---

## 📸 Dokumentasi
Tambahkan screenshot hasil tampilan di browser untuk setiap langkah:
1. Tampilan “Hello World”  
2. Tampilan Form Input  
3. Tampilan Hasil Data Diri (Nama, Umur, Gaji)

---

## 🧾 Penutup
Dari praktikum ini, mahasiswa dapat memahami dasar PHP seperti:
- Penggunaan variabel dan form input.  
- Struktur kondisi dan perulangan.  
- Pengolahan data dengan `$_POST`.  
- Membuat aplikasi web sederhana berbasis PHP.
