1. Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program. Jelaskan juga peran dari Bahasa pemrograman dan compiler, begitu juga dengan peran dari Sistem Operaso. Gunakan referensi : [Video referensi 1](https://www.youtube.com/watch?v=Z5JC9Ve1sfI) dan [Video referensi 2](https://www.youtube.com/watch?v=jFDMZpkUWCw)

Ini adalah bit penyimpanan cepat tempat CPU menyimpan nilai-nilai yang sedang dikerjakan saat ini.
Hal terakhir yang kita perlukan dalam komputer sederhana kita adalah tempat untuk menyimpan instruksi dan nilai apapun yang akhirnya kita hitung.
Ini adalah register yang melacak siklus instruksi kita, register lain yang memuat intruksi kita dari memori, dan Akumulator. itu adalah RAM, Memori Akses acak.
Kami menyebutnya Akses Acak karena tidak masalah kapan atau bagaimana urutan
![WhatsApp Image 2024-03-24 at 04 00 50](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/f13b2c26-bee8-4085-949c-e2b65b25672a)

Prosesor memiliki tiga langkah: 
Ambil, Dekode, Jalankan. 
Itu hanya akan mengulangi dalam satu lingkaran, itulah satu-satunya hal yang sebenarnya ada di dalamnya.jadi mari kita memuat program kita ke dalam RAM.
RAM juga digunakan untuk menyimpan jawaban kita, keluaran kita.
Sebuah instruksi memiliki 2 bagian. Bagian pertama adalah instruksi itu sendiri.
Dan bagian kedua biasanya berupa alamat memori.

Pada setiap detak jam, CPU akan melakukan salah satu dari tiga hal baerikut:
Mengambil instruksi dari alamat memori. 
Ini akan memecahkan kode instruksi itu. 
![WhatsApp Image 2024-03-24 at 04 31 18](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/a7b62b27-eb1a-45d9-b00e-ff26d7f03a73)

Fetch
dan itu akan menjalankan instruksi.
Berputar-putar dalam satu lingkaran. jadi itu akan dihitung.
Satu jam berdetak Program counter diatur ke 0, sehingga CPU mengambil instruksi pada alamat O di memori dan memasukkannya ke dalam register instruksi
![WhatsApp Image 2024-03-24 at 04 56 03](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/5b792083-36fe-4147-a2e1-024dc61dd577)

Dekode.
CPU menerjemahkan instruksi.
Bagian pertama adalah instruksi, dan bagian kedua adalah lokasi.
Dalam kasus kita, instruksinya adalah LOAD dan alamatnya adalah 6.
jadi kita akan memuat nilai di alamat 6 ke dalam akumulator.
![WhatsApp Image 2024-03-24 at 04 54 48](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/2a7ce1e6-4463-4fdf-9f9d-675c835c52da)


Execute.
CPU mengeksekusi instruksi ini dibutuhkan nilai di alamat 6 Dalam hal ini nilainya adalah 1.
![WhatsApp Image 2024-03-24 at 05 14 06](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/c3b06805-a4d3-44dc-825f-8195f962b818)

Fetch.
Menghitung program bertambah, dan CPU mengambil instruksi berikutnya di bit memori berikutnya.
![WhatsApp Image 2024-03-24 at 05 20 07](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/bcc0cbd5-e456-4d30-a61f-5add2a0ece41)

Decode.
CPU menerjemahkan instruksi, Kali ini ADD,  dan alamatnya 7.
Jadi kita akan menambahkan apa yang ada di alamat 7 ke dalam apa yang sudah ada di akumulator.
![WhatsApp Image 2024-03-24 at 05 20 07 (1)](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/21ee7c26-8d35-4738-b585-e437df8c7de1)

Execute
CPU mengeksekusi instruksi. kita tambahkan nilainya di alamat 7.Dalam hal ini nilainya 1. 1+1 adalah 2
![WhatsApp Image 2024-03-24 at 05 32 31](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/2c8aaeb7-e931-4757-81e5-2cb38f5eb771)

Fetch.
Dari lokasi memori berikutnya, nomor 2.
![WhatsApp Image 2024-03-24 at 05 36 54](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/6e4dd4d3-8c05-4a22-9b4d-0dd063dfcafe)

Decode.
Instruksi untuk MENYIMPAN nilai yang ada di akumulator ke dalam RAM, di alamat 6.
![WhatsApp Image 2024-03-24 at 05 36 54 (1)](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/4dc95137-9a49-4207-8edc-f6109d5c7fc1)

Execute
Sekarang, perhatikan bahwa kita menimpa apa yang sudah ada, jadi alamat 6 sekarang memiliki 2 di dalamnya, bukan 1.
![WhatsApp Image 2024-03-24 at 05 36 55](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/d1b889fe-f080-4414-acd1-a931e08563c1)

Fetch
Intruksi baru JUMP. dengan lompatan, alamat berikut yang kita ambil adalah alamat yang ada dalam instruksi ini.
![WhatsApp Image 2024-03-24 at 05 48 46](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/2e3a9880-1c03-469b-b5bf-866722d07a6b)

Decode
Jadi kita akan lompat ke alamat 1.
![WhatsApp Image 2024-03-24 at 05 48 47](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/4edbc7b4-e427-4d2c-bd51-d23f3cbc89ad)

Execute
Penghitungan Program sekarang kembali ke 1.
Kemampuan untuk melompat, mengulang, dan membuat instruksi secara rekursif adalah salah satu dasar ilmu komputer.
![WhatsApp Image 2024-03-24 at 05 48 47 (1)](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/fbe134cb-7749-491d-aa54-c752e50eb3ea)


Program kita, dengan instruksi sederhana ini, tidak memiliki perintah halt, atau cara apapun untuk menghentikannya, jadi program ini hanya akan terus menambah nilainya sebanyak satu (banyak klik cepat) hingga jumlahnya menjadi sangat besar sehingga bisa tidak lagi dipegang oleh alamat memori.
Ini adalah cara yang sangat rumit untuk memprogramkan komputer.


Siklus CPU Dalam Eksekusi Program

Siklus CPU Fetch, Decode, Execute
Fetch (Pengambilan):
•	Pada langkah ini, CPU mengambil instruksi program berikutnya dari memori utama.
•	Instruksi ini disalin dari memori ke dalam register instruksi di dalam CPU.
•	Analogi: Mirip dengan mengambil buku dari rak perpustakaan untuk membaca.
Decode (Dekode):
•	Setelah instruksi diambil, CPU harus memahami atau mendekode instruksi tersebut.
•	CPU menafsirkan kode instruksi yang telah diambil dan menentukan operasi apa yang perlu dilakukan.
•	Analogi: Mirip dengan membaca instruksi dalam buku dan memahami apa yang diminta.
Execute (Eksekusi):
•	Setelah instruksi didekode, CPU menjalankan atau mengeksekusi instruksi tersebut.
•	Ini melibatkan melakukan operasi matematika, logika, atau transfer data sesuai dengan instruksi yang diberikan.
•	Hasil dari eksekusi instruksi mungkin menyebabkan perubahan dalam nilai-nilai register CPU atau memori komputer.
•	Analogi: Mirip dengan melakukan tindakan yang diinstruksikan setelah memahami petunjuk yang diberikan.

Peran Bahasa Pemrograman, Compiler, dan Sistem Operasi
Bahasa Pemrograman:
•	Bahasa pemrograman adalah aturan dan struktur yang digunakan untuk mengekspresikan logika program.
•	Ini memungkinkan programmer untuk menulis instruksi-instruksi yang dapat dimengerti oleh manusia.
•	Analogi: Bahasa manusia yang digunakan untuk mengkomunikasikan instruksi kepada komputer.
Compiler:
•	Compiler adalah perangkat lunak yang menerjemahkan kode program dari bahasa pemrograman ke dalam bahasa mesin yang dapat dimengerti oleh komputer.
•	Ini memungkinkan komputer untuk menjalankan program yang ditulis dalam bahasa pemrograman tertentu.
•	Analogi: Translator yang mengubah bahasa manusia menjadi bahasa yang dimengerti oleh komputer.
Sistem Operasi:
•	Sistem operasi adalah perangkat lunak yang mengelola sumber daya komputer dan menyediakan layanan kepada program-program yang berjalan di atasnya.
•	Ini memungkinkan pengguna untuk berinteraksi dengan komputer dan mengatur penggunaan sumber daya seperti memori, CPU, dan perangkat input/output.
•	Analogi: Pengelola yang mengatur dan mengkoordinasikan berbagai aspek komputer untuk menjalankan program secara efisien.

Kesimpulan:
•	Siklus CPU (Fetch, Decode, Execute) adalah prinsip dasar yang digunakan oleh komputer untuk menjalankan program.
•	Bahasa pemrograman, compiler, dan sistem operasi memainkan peran penting dalam memungkinkan komputer untuk menjalankan program secara efisien dan efektif.
•	Dengan koordinasi yang baik antara semua komponen ini, komputer dapat menjalankan tugas-tugas yang kompleks dengan lancar dan tepat.

3. 
$ make
$ make clean
$ sudo make install
$ sudo make uninstall
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/1b1b7579-8f11-4ee2-86fe-f1b24e37847a)

$ iops64 $(nproc) 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/02fb2a5c-c3bd-4062-9033-f85c99161b82)

$ flops64 $(nproc)
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/3cd12814-b000-4126-bd29-39770370c6fc)

IOPS (Input/Output Operations Per Second) dan FLOPS (Floating Point Operations Per Second) adalah dua metrik yang umum digunakan untuk mengukur kinerja komputer dalam konteks operasi masukan/keluaran dan operasi titik mengambang.

IOPS (Input/Output Operations Per Second):
IOPS mengukur jumlah operasi masukan/keluaran yang dapat dilakukan oleh sebuah sistem dalam satu detik.
Operasi masukan/keluaran mencakup pembacaan dan penulisan data dari atau ke perangkat penyimpanan, seperti hard drive, SSD, atau jaringan.
IOPS adalah metrik penting dalam sistem penyimpanan karena membantu menentukan seberapa cepat data dapat dibaca atau ditulis dari atau ke penyimpanan.

FLOPS (Floating Point Operations Per Second):
FLOPS mengukur jumlah operasi matematika titik mengambang yang dapat dilakukan oleh sebuah sistem dalam satu detik.
Operasi titik mengambang melibatkan pengolahan angka-angka dengan titik desimal, yang sering digunakan dalam komputasi ilmiah dan teknik, seperti simulasi fisika atau analisis numerik.
FLOPS adalah metrik penting dalam mengevaluasi kinerja komputasi yang memerlukan operasi matematika yang intensif.

Kesimpulannya, IOPS dan FLOPS adalah dua metrik yang berbeda tetapi keduanya penting dalam mengevaluasi kinerja sistem komputer dari dua sudut pandang yang berbeda: kinerja penyimpanan dan kinerja komputasi. Dengan memahami kedua metrik ini, pengguna dapat memilih sistem yang sesuai dengan kebutuhan mereka, apakah itu fokus pada kinerja penyimpanan yang tinggi atau kinerja komputasi yang cepat.

4. Apabila Debian VM mu masih belum terdapat packeage gcc, make dan git, lakukan instalasi dan catat setiap langkahnya!
$ su -l
$ apt install make
$ apt install git
$ apt install gcc
$ git clone  https://github.com/ferryastika/flops-iops
$ cd flops-iops
