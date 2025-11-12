# Praktikum 7: PHP Dasar  
**Nama:** Manuel Johansen Dolok Saribu  
**NIM:** 312410493  
**Kelas:** Ti.24.A5  

---

## Langkah-langkah Praktikum

### Membuat File Pertama `php_dasar.php`
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

---

### Variabel PHP
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

### Form Input dan `$_POST`
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

### Operator dan Struktur Kondisi
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

### Perulangan
```php
<?php
for ($i=1; $i<=5; $i++) {
    echo "Perulangan ke-$i <br>";
}
?>
```
**Penjelasan:** Menjalankan blok kode secara berulang berdasarkan jumlah iterasi.

---

### Tugas: Program PHP Sederhana
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
