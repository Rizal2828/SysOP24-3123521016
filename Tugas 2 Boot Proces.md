Proses booting merupakan serangkaian langkah yang terjadi ketika sebuah komputer atau perangkat elektronik dinyalakan atau dihidupkan. Proses ini bertujuan untuk memulai sistem operasi dan mempersiapkan perangkat keras serta perangkat lunak agar siap digunakan oleh pengguna.

Langkah-langkah proses booting:
![Diagram sistem operasi](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/cb849a08-ee88-456c-bad3-6979ce6203d6)
1. Power On: Pengguna menyalakan atau menghidupkan komputer dengan menekan tombol power.
2. Power-On Self-Test (POST): Sekembalinya daya ke komputer, proses POST akan dijalankan oleh firmware (biasanya BIOS atau UEFI) untuk memeriksa dan menguji perangkat keras utama seperti RAM, CPU, kartu grafis, dan lainnya. Jika ada masalah dengan perangkat keras, proses booting akan dihentikan dan pesan kesalahan akan ditampilkan.
3. Inisialisasi Perangkat Keras: Setelah berhasil melewati POST, firmware akan menginisialisasi perangkat keras yang diperlukan, termasuk keyboard, mouse, hard drive, dan perangkat lainnya.
4. Memuat Boot Loader: Setelah inisialisasi perangkat keras, boot loader akan dimuat ke dalam memori. Boot loader, seperti GRUB atau LILO pada sistem Linux, bertanggung jawab untuk memuat sistem operasi ke dalam memori dari perangkat penyimpanan, seperti hard drive atau SSD.
5. Memuat Sistem Operasi: Boot loader kemudian akan memuat kernel (inti) sistem operasi ke dalam memori. Kernel adalah bagian inti dari sistem operasi yang mengelola sumber daya perangkat keras dan perangkat lunak, serta menangani komunikasi antara perangkat keras dan perangkat lunak.
6. Inisialisasi Sistem dan Layanan: Setelah kernel dimuat, sistem operasi akan mulai melakukan proses inisialisasi. Ini termasuk memuat driver perangkat keras yang diperlukan, mengaktifkan layanan sistem, dan menyiapkan lingkungan pengguna.
7. Login atau Tampilan Desktop: Setelah inisialisasi selesai, pengguna akan disajikan dengan layar login atau tampilan desktop, tergantung pada konfigurasi sistem.

Jenis-jenis booting:
Cold Booting: Cold booting terjadi saat komputer atau perangkat dinyalakan setelah sebelumnya dimatikan sepenuhnya. 
Warm Booting: Warm booting terjadi saat komputer atau perangkat di-restart tanpa dimatikan sepenuhnya. 
Network Booting: Network booting adalah proses booting di mana komputer memuat sistem operasi dari jaringan, bukan dari perangkat penyimpanan lokal seperti hard drive atau SSD
Remote Booting: Remote booting adalah proses booting di mana komputer memuat sistem operasi dan perangkat lunak lainnya dari server jarak jauh. 
Dual Booting: Dual booting adalah konfigurasi di mana sebuah komputer memiliki dua atau lebih sistem operasi yang terinstal, dan pengguna dapat memilih sistem operasi mana yang ingin dimuat saat komputer dinyalakan
Fast Booting: Fast booting adalah fitur yang mempercepat proses booting dengan mengurangi waktu yang diperlukan untuk melakukan inisialisasi perangkat keras dan perangkat lunak

Masalah booting dan cara mengatasi masalah booting:
Perangkat Keras Rusak: Periksa dan ganti komponen perangkat keras yang rusak.
Kerusakan Sistem Operasi atau Boot Loader: Perbaiki file sistem atau boot loader dengan menggunakan media instalasi sistem operasi.
Pengaturan BIOS/UEFI Salah: Periksa dan atur kembali pengaturan BIOS/UEFI yang sesuai.
Infeksi Malware atau Virus: Gunakan program antivirus untuk membersihkan sistem dari infeksi malware atau virus.
Konflik Perangkat Lunak: Boot ke dalam mode aman dan hapus atau perbarui driver perangkat keras yang bermasalah.
Perangkat Eksternal yang Terhubung: Cabut perangkat eksternal yang tidak diperlukan saat booting.

![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/bf3ad905-9518-419f-a864-4b1edef68d6a)
CPU: Digunakan untuk melihat informasi tentang processor, kecepatan clocks, dan teknologi yang digunakan
Processor: Menunjukkan nama lengkap dari prosesor ini seperti “Intel core i3 1005G1”.
Code Name: Menunjukkan nama kode prosesor ini seperti “Ice Lake”.
Package: Menunjukkan jenis paket prosesor seperti “Socket 1526 FCBGA”.
Technology: Menunjukkan proses manufaktur yang digunakan untuk membuat prosesor seperti “10 nm”
Specification: Menunjukkan nama lengkap dan nomer model prosesor “Intel® Core™ i3-1005G1 CPU @ 1.20GHz” 
Family: Menunjukkan keluarga prosesor seperti”6”
Model: Menunjukkan model prosesor “E”
Intructions: Menunjukkan daftar intruksi yang didukung oleh prosesor.
Core speed: Melihat kecepatan clock saat ini dari inti prosesor seperti “1202. 18 MHz”
Multipler: Menunjukkan pengganda yang digunakan untuk menentukan kecepatan clock inti “x 12.0 (4.0 – 34.0)”
Bus Speed: Melihaat kecepatan bus yang menghubungkan  prosesor ke memori dan perangkat lain. “100. 18 MHz”  
Cache: 
L1 Data: Menunjukkan ukuran cache L1 data seperti ”2 x 48 KBytes” ”12-way”
L1 Inst.: Menunjukkan ukuran cache L1 Instruksi seperti “2 x 32 KBytes” “8-way”
Level 2: Menunjukkan ukuran cache L2  seperti “2 x 512 KBytes” “8-way”
Level 3: Menunjukkan ukuran cache L3 seperti “4 MBytes” “16-way”

![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/26f03481-25e9-4ac8-ad5e-9b5e15950fef)
Motherboard:
Manufacturer: Produsen motherboard “LENOVO”
Model: Model motherboard “LNVNB161216”
Bus Specs: Spesifikasi bus “PCI-Express 3.0 (8.0 GT/s)”
Chipset: Chipset motherboard “Intel Ice Lake” 
Southbridge: Southbridge motherboard “Intel Ice Lake PCH”
LPCIO: Informasi tentang LPCIO.

BIOS:
Brand: Merek BIOS “LENOVO”
Version: Versi BIOS “DKCNS1WW”
Date: Tanggal BIOS dibuat “12/23/2020”

![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/d191bdae-d5f5-437e-908d-59403ddd8613)
General:
Type: Menunjukkan jenis memori yang digunakan “DDR4”
Size: Menunjukkan jumlah memori yang terpasang “4 GBytes”
Channel #: Menunjukkan jumlah channel memori yang digunakan “single”
DC Mode:
Uncore Frequency: Menunjukkan clock speed uncore “1010.0 MHz”
Timings:
DRAM Frequency: Menunjukkan clock speed memori “1064.0 MHz”
FSB:DRAM: Menunjukkan rasio antara FSB dan DRAM clock speed “1:16”
CAS# Latency (CL): Menunjukkan latency CAS “15.0 docks”
RAS# to CAS# Delay (tRCD): Menunjukkan RAS# to CAS# delay “15 docks”
RAS# Precharge (tRP): Menunjukkan RAS# precharge “15 docks”
Cycle Time (tRAS): Menunjukkan cycle time “35 docks”
Row Reflesh Cycle Time (tRFC): Menunjukkan row reflesh cycle time “374 docks”
Command Rate (CR): Menunjukkan command rate “1T”

![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/180e6b49-ada9-43bc-a88c-a672ad50f5a9)
Memory Slot Selection:
Bagian ini menunjukkan slot memori yang terpasang pada komputer. Pada gambar, hanya ada satu slot memori yang terisi.
Module Size:
Bagian ini menunjukkan ukuran modul memori yang terpasang pada slot. Pada gambar, modul memorinya berukuran “4 GBytes”
Bagian ini menunjukkan nama manufaktur modul memori. Pada gambar, manufakturnya adalah “Samsung”
Part Number: Bagian ini menunjukkan nomor bagian modul memori. Pada gambar, nomor bagiannya adalah “M471A5244CB0-CTD”
Serial Number: Bagian ini menunjukkan nomor bagian Serial number “00000000”

![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/0e575a92-85bd-4b48-a208-b57b54ee36b1)
Display Device Selection: Memungkinkan Anda memilih perangkat tampilan yang ingin Anda lihat informasinya.
GPU: Menunjukkan informasi tentang GPU, seperti nama, vendor, dan clock speed.
Name: “Intel® UHD Graphics”
Board Manuf.: Menunjukkan nama pabrikan motherboard “Lenovo”
Code Name: Menunjukkan nama kode CPU.
Revision: Menunjukkan revisi CPU “7”
Technology: Menunjukkan teknologi manufaktur CPU.
