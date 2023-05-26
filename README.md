# Praktikum3
Latihan 3
MEMBUAT DATABASE LATIHAN 3

# 1.	Implementasikan penggunaan constraint foreign key pada semua table yang berelasi 
my sql> create table dosen (kd_ds varchar (10),primary key,nama varchar (50));
my sql> create table mahasiswa ( nim varchar(10) not null,nama varchar(50),jenis_kelamin varchar(10),tgl_lahir varchar(10),jalan varchar(10),kota varchar(10),kode_pos varchar(10), no_hp varchar(12), kd_ds varchar(10));
[gambar 1](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss1.jpeg)

# 2.	Lakukan penambahan pada data table dengan mengisi kd_ds yang belum ada pada data dosen 
my sql> insert into dosen (kd_ds, nama) 
        value ('DS001', 'Ahmad'),('DS002', 'Hamzah');
my sql>  insert into mahasiswa (nim, nama,jenis_kelamin,tanggal_lahir, jalan, kota , kode_pos, no_hpkd_ds)
         value ('312210491', 'Ridha', 'laki-laki', '2004_07_27', 'villa 2', 'Bekasi', '17530', '082133795530', 'DS001')
[gambar 2](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss2.jpeg)
[gambar 2.2](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss2.2.jpeg)

# 3. 	Hapus satu record data pada table dosen yang telah dirujuk pada table mahasiswa
my sql> delete from dosen where kd_ds = 'DS001';
[gambar 3](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss3.png)

# 4.    Ubah mode menjadi ON UPDATE CASCADE ON DELETE RESTRIC
my sql> alter table mahasiswa add constraint fk_mahasiswa_dosen foreign key (kd_ds) references dosen (kd_ds) on update cascade on delete        restrict;
[gambar 4](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss4.png)

# 5.	Lakukan perubahan data pada table dosen (kd_ds)
my sql> update dosen set kd_ds = 'DS001' where kd_ds = 'DS002'; 
[gambar 5](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss5.png)

# 6.	Lakukan penghapusan data pada table dosen
my sql> delete from dosen where kd_ds='DS001';
[gambar 6](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss6.png)

# 7. 	Ubah menjadi ON UPDATE CASCADE ON DELETE SET NULL
my sql> alter table mahasiswa add constraint fk_mahasiswa_dosen foreign key (kd_ds) references dosen (kd_ds) on update cascade on delete set null;
[gambar 7](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss7.png)

# 8. 	Menghapus data pada table dosen
my sql> delete from dosen;
[gambar 8](https://github.com/dhomuhammad/Praktikum3/blob/main/skrinsutpraktikum3/ss8.png)

# Pertanyaan :

Apa bedanya penggunaan RESTRIC dan penggunaan CASCADE !

•	Restrict merupakan perubahan data dan penghapusan data tidak diijinkan pada table referensi (parent table) apabila pada table child sudah ada yang merujuk pada data tersebut, Sedangkan
Cascade merupakan perubahan atau penghapusan data pada table referensi (parent table) akan di ikuti oleh table child.

# Kesimpulan :

•	Dalam penulisan sebuah query SQL, dengan menggunakan constraint, kita dapat menghindari kesalahan penulisan data, sehingga konsistensi dan integritas dari sebuah data dapat terjaga dengan baik untuk digunakan pada proses selanjutnya. performa dari database juga dapat ditingkatkan karena dengan adanya constraint, maka jumlah kesalahan yang mungkin terjadi dapat berkurang. Salah satu keuntungan lainnya adalah dapat mencegah pengguna lain untuk memasukkan data yang tidak sah pada kolom tertentu.








