TUGAS PENDAHULUAN:
Jawablah pertanyaan pertanyaan di bawah ini:

1. Apa yang dimaksud redirection?
2. Apa yang dimaksud pipeline?
3. Apa yang dimaksud perintah di bawah ini:
echo, cat, more, sort, grep, wc, cut, uniq

Jawaban:

1.	Redirection dalam konteks sistem operasi adalah proses mengalihkan aliran input atau output dari sebuah perintah atau program. Ini memungkinkan kita untuk mengambil input dari sumber yang berbeda atau menyimpan output dari sebuah perintah atau program ke lokasi yang berbeda dari biasanya.
2.	Pipeline adalah konsep dalam sistem operasi Unix/Linux yang memungkinkan pengguna untuk menghubungkan beberapa perintah bersama-sama, di mana output dari satu perintah menjadi input untuk perintah berikutnya. Dalam sebuah pipeline, output dari perintah pertama dikirim secara langsung ke input dari perintah kedua, dan begitu seterusnya.
3.	-echo: Perintah ini digunakan untuk menampilkan teks atau nilai variabel ke layar. Misalnya, echo "Hello, world!" akan menampilkan teks "Hello, world!" ke layar.
-cat: Singkatan dari "concatenate", perintah cat digunakan untuk menggabungkan, menampilkan, dan membuat salinan dari satu atau beberapa file teks. Misalnya, cat file1.txt file2.txt akan menampilkan isi dari kedua file file1.txt dan file2.txt ke layar.
-more: Perintah more digunakan untuk menampilkan isi file teks satu halaman sekaligus pada terminal. Pengguna bisa menggulirkan halaman dengan menggunakan tombol "Enter".
-sort: Perintah sort digunakan untuk mengurutkan baris-baris dalam sebuah file teks secara alfabetis atau numerik. Misalnya, sort file.txt akan mengurutkan baris-baris dalam file file.txt.
-grep: Perintah grep digunakan untuk mencocokkan pola teks dalam sebuah file atau output dari perintah lain. Ini sangat berguna untuk pencarian teks. Misalnya, grep "pattern" file.txt akan mencari pola "pattern" dalam file file.txt.
-wc: Singkatan dari "word count", perintah wc digunakan untuk menghitung jumlah baris, kata, dan karakter dalam sebuah file teks. Misalnya, wc file.txt akan menampilkan jumlah baris, kata, dan karakter dalam file file.txt.
-cut: Perintah cut digunakan untuk menampilkan bagian tertentu dari setiap baris dalam sebuah file teks. Misalnya, cut -d',' -f1 file.csv akan menampilkan kolom pertama dari sebuah file CSV yang menggunakan koma sebagai delimiter.
-uniq: Perintah uniq digunakan untuk menghapus atau melaporkan baris-baris berurutan yang sama dari sebuah file teks. Misalnya, uniq file.txt akan menghapus baris-baris yang duplikat dari file file.txt.






Percobaan 1 : File descriptor
1.	Output ke layar (standar output), input dari system (kernel)
$ ps
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/41fc3a5e-9bd6-401d-b5b1-5199080ff804)

Keterangan: Perintah ps digunakan untuk memperlihatkan proses yang sedang berjalan pada sistem (kernel) diperlihatkan pada layar (standart output)

2.	Output ke layar (standar output), input dari keyboard (standard input)
$ cat
hallo, apa khabar
hallo, apa khabar
exit dengan ^d
exit dengan ^d
[Ctrl-d]
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/d9212888-ae73-404b-ad40-73c62f66ac2c)

Keterangan: perintah cat digunakan untuk menampilkan isi file

3.	Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
$ mkdir mydir
$ mkdir mydir **(Terdapat pesan error)**
  
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/e21e0e7c-0b3b-4a85-98ba-acffe70abe86)
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/43104802-3dc4-46b9-b04b-fa242eb37ce8)

Keterangan: perintah mkdir digunakan untuk membuat directory yang bernama mydir kenapa kog eror yang kedua karena sudah ada directory

Percobaan 2 : Pembelokan (redirection)
1.	Pembelokan standar output
$ cat 1> myfile.txt
Ini adalah teks yang saya simpanKe file myfile.txt
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/06c93a2e-51dc-48c4-ae24-9b2c66055ed5)

Keterangan: perintah ini akan menjalankan perintah cat, dan output dari perintah tersebut akan dituliskan ke dalam file baru yang disebut myfile.txt.
2.	Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
$ cat 0< myfile.txt
$ cat myfile.txt
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/fb783d18-aba5-42ea-80a3-68d607bce24e)

Keterangan: $ cat 0< myfile.txt: Perintah ini menggunakan operator < untuk mengalihkan standar input dari perintah cat menjadi berasal dari file myfile.txt (file descriptor 0 menunjukkan standar input).
3.	Pembelokan standar error untuk disimpan di file
$ mkdir mydir (Terdapat pesan error)
$ mkdir mydir 2> myerror.txt
$ cat myerror.txt
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/86af4640-ed1a-46d9-a972-0bff40e1aaf3)

Keterangan: Perintah ini akan menampilkan pesan kesalahan yang terjadi saat mencoba membuat direktori "mydir".
4.	Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
$ ls filebaru (Terdapat pesan error)
$ ls filebaru 2> out.txt
$ cat out.txt
$ ls filebaru 2> out.txt 2>&
$ cat out.txt
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/3deca880-e119-4cef-a4ea-d1186df748b1)

Keterangan: pada perintah ls filebaru 2> out.txt 2>&, terjadi kesalahan sintaks karena tidak ada tujuan untuk mengalihkan standar error. Seharusnya disertakan file descriptor yang menjadi tujuan untuk alih media, seperti contoh sebelumnya menggunakan 2>&1.
5.	Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
$ echo “mencoba menulis file” 1> baru
$ cat filebaru 2> baru 1>&
$ cat baru
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/d8803c34-3a9d-4368-84d4-549d57cdb1a3)

Keterangan: Dengan demikian, tidak ada teks yang akan tertulis di dalam file "baru" karena tidak ada operasi yang dilakukan untuk menyalin output ke sana dalam perintah yang diberikan.
6.	Notasi >> (append)
$ echo “kata pertama” > surat
$ echo “kata kedua” >> surat
$ echo “kata ketiga” >> surat
$ cat surat
$ echo “kata keempat” > surat
$ cat surat
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/d0b75b01-1c5d-44f0-b742-7b53c3d55a2c)

Keterangan: Menulis "kata pertama" ke file "surat".
Menambah "kata kedua" ke file "surat" (tanpa menghapus "kata pertama").
Menambah "kata ketiga" ke file "surat" (tanpa menghapus "kata pertama" dan "kata kedua").
Menampilkan isi file "surat" ke layar, yang berisi "kata pertama", "kata kedua", dan "kata ketiga".
Mencoba menulis "kata keempat" ke file "surat", mengganti isi sebelumnya.
Menampilkan isi file "surat" ke layar, yang hanya berisi "kata keempat" karena isi sebelumnya telah diganti.
7.	Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
$ cat <<++
Hallo, apa kabar?
Baik-baik saja?
Ok!
++
$ cat <<%%%
Hallo, apa kabar?
Baik-baik saja?
Ok!
%%%
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/753d1cc1-bf7f-45cb-a7f4-9539c29e7957)

Keterangan: Notasi here document (<<) digunakan untuk menunjukkan awal dan akhir dari blok teks yang akan diambil sebagai input. Tanda pembatas (dalam contoh ini ++ dan %%%) menandai awal dan akhir blok teks. Isi dari blok teks tersebut kemudian ditampilkan oleh perintah cat.
8.	Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
$ cat myfile.txt – surat
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/ad23f532-610b-4a7d-a605-5b35de0ad77e)

Keterangan: Notasi - digunakan untuk menyelipkan input dari keyboard di antara dua file yang akan ditampilkan oleh perintah cat. Dalam contoh tersebut, cat akan menampilkan isi dari file myfile.txt, kemudian menampilkan input yang diberikan dari keyboard, dan terakhir menampilkan isi dari file surat.
Percobaan 3 : Pipa (pipeline)
1.	Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
$ who
$ who | sort
$ who | sort –r
$ who > tmp
$ sort tmp
$ rm tmp
$ ls –l /etc | more
$ ls –l /etc | sort | more
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/f96e9da9-a7ec-4b67-8605-96ee3a5db9f9)
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/05b8fb93-cf1a-448a-9c61-7507f80d596b)

Keterangan: who: Menampilkan daftar pengguna yang sedang login.
who | sort: Mengalirkan output dari perintah who ke perintah sort, yang mengurutkan baris-baris berdasarkan urutan alfabetis (default).
who | sort –r: Mengalirkan output dari perintah who ke perintah sort dengan opsi -r yang mengurutkan baris-baris secara terbalik (berdasarkan urutan alfabetis terbalik).
who > tmp: Mengalirkan output dari perintah who ke file sementara tmp.
sort tmp: Mengurutkan isi file tmp yang sebelumnya dihasilkan oleh perintah who.
rm tmp: Menghapus file sementara tmp yang sudah tidak diperlukan lagi.
ls –l /etc | more: Menampilkan isi dari direktori /etc dengan format panjang menggunakan ls, dan kemudian outputnya dialirkan ke perintah more untuk ditampilkan secara bertahap.
ls –l /etc | sort | more: Menampilkan isi dari direktori /etc dengan format panjang menggunakan ls, kemudian outputnya diurutkan dengan sort, dan akhirnya outputnya dialirkan ke perintah more untuk ditampilkan secara bertahap.
2.	Untuk membelokkan standart output ke file, digunakan operator ">"
$ echo hello
$ echo hello > output
$ cat output
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/b3d9026f-3e70-4854-ba8b-acaab6132fc0)

Keterangan: echo hello: Menampilkan teks "hello" ke layar.
echo hello > output: Mengalirkan output dari perintah echo hello ke file output. Jadi, teks "hello" akan disimpan dalam file output.
cat output: Menampilkan isi dari file output, yang sebelumnya berisi teks "hello".
3.	Untuk menambahkan output ke file digunakan operator ">>"
$ echo bye >> output
$ cat output
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/9c74c023-e5dc-41f0-803d-49e7707e3615)

Keterangan: echo bye >> output: Menambahkan teks "bye" ke dalam file output, tanpa menghapus isi yang sudah ada di dalamnya.
cat output: Menampilkan isi dari file output, yang sekarang berisi teks "hello" diikuti oleh "bye".
4.	Untuk membelokkan standart input digunakan operator "<"
$ cat < output
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/dbfa6668-f9d0-43f4-a71a-1906e1188b8b)

Keterangan: cat < output: Perintah cat membaca input dari file output dan menampilkannya ke layar. Artinya, isi dari file output akan ditampilkan oleh perintah cat.
5.	Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
$ cat < output > out
$ cat out
$ cat < output >> out
$ cat out
$ cat < output > output
$ cat output
$ cat < out >> out (Proses tidak berhenti)
[Ctrl-c]
$ cat out
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/0885cdad-b469-498f-84e7-3f662c1521c2)

Keterangan: cat < output > out: Perintah cat membaca input dari file output dan menuliskannya ke file out.
cat out: Isi dari file out ditampilkan oleh perintah cat.
cat < output >> out: Perintah cat membaca input dari file output dan menambahkan isinya ke file out.
cat out: Isi dari file out tetap sama dengan sebelumnya karena tidak ada tambahan.
cat < output > output: Proses ini mencoba menggunakan nama file yang sama untuk standar input dan output. Ini bukan praktik yang dianjurkan dan dapat menyebabkan hasil yang tidak terduga. Pada beberapa sistem, ini dapat menghasilkan loop tak terbatas atau mengunci file.
cat output: Karena proses sebelumnya mungkin telah menyebabkan masalah, isinya mungkin tidak berubah.
cat < out >> out: Proses ini mencoba membaca dari file out dan menambahkan outputnya ke file yang sama. Hal ini dapat menyebabkan loop tak terbatas karena setiap kali konten out ditambahkan ke out, maka ukurannya akan terus bertambah.
Percobaan 4 : Filter
1.	Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
$ w –h | grep <user>
$ grep <user> /etc/passwd
$ ls /etc | wc
$ ls /etc | wc –l
$ cat > kelas1.txt
Badu
Zulkifli
Yulizir
Yudi
Ade
[Ctrl-d]
$ cat > kelas2.txt
Budi
Gama
Asep
Muchlis
[Ctrl-d]
$ cat kelas1.txt kelas2.txt | sort
$ cat kelas1.txt kelas2.txt > kelas.txt
$ cat kelas.txt | sort | uniq
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/46d8995b-c9d4-42c0-bee1-434b8c7ce229)
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/2b4be556-fd84-438b-af7e-85ecd410ef10)

 
Keterangan: pipa (|) digunakan untuk mengalirkan output dari satu perintah ke perintah lainnya, membentuk fungsi yang lebih kompleks.

LATIHAN: 
1.	Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru. 
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/63af4e88-d355-4793-9083-b44ef76a0d1d)

Keterangan: daftar lengkap dari direktori aktif akan ditampilkan di terminal, dan pada saat yang sama, daftar tersebut juga akan disimpan dalam file baru

2.	Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya. 
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/37cba31b-4eb6-4c87-8f98-471c9a001dd6)

Keterangan: daftar lengkap dari file /etc/passwd akan ditampilkan di terminal, dan pada saat yang sama, daftar tersebut juga akan ditambahkan pada file baru 

3.	Urutkan file baru dengan cara membelokkan standard input.
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/0f8372b1-5534-4833-91fb-eebe6aa2c220)

Keterangan: dengan menggunakan operator < untuk mengambil input dari sebuah file, kita dapat mengurutkan isinya menggunakan perintah sort

4.	Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut.
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/6853a01b-b438-479a-908d-3589d46f088e)

Keterangan: perintah sort digunakan untuk mengurutkan masukannya berdasarkan urutan nomor, “< “ baru mengarahkan isi file baru sebagai input untuk perintah sort.”>” mengarahkan output dari perintah sort ke file baru dengan nama baru.urut .
5.	Buatlah direktori latihan2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/812ec9ec-d944-4e58-b40d-3f3f6f2f9e59)

Keterangan: penggunaan operator 2> dan 2>> memungkinkan kita untuk mengalihkan pesan error ke file yang ditentukan saat menjalankan perintah di lingkungan Unix/Linux.

6.	Urutkan kalimat berikut : 
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung 
Dengan menggunakan notasi   here document (<@@@ …@@@)
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/17d3439c-3616-441d-9a5c-d96a7db15a3a)

Keterangan: menggunakan notasi here document (<<) bersama dengan perintah sort untuk mengurutkan kalimat-kalimat tersebut.

7.	Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan
filter dan tambahkan data tersebut ke file  baru.
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/9fe1419f-04f3-41c2-9026-f6531d2659dc)

Keterangan: Untuk menghidung jumlah baris, kata dan karakter kita harus menggunakan perintah wc -l untuk menghitung jumlah baris, wc -w untuk menghitaung jumlah kata, dan wc -c untuk menghitung jumlah karakter kemudian menggunakan perintah pengelompokan “{}” untuk memindahkan jumlah baris, kata dan karakter, menggunakan perintah “>>” untuk memindahkan file tersebut ke file Bernama baru.

8.	Gunakan perintah  di bawah ini dan perhatikan hasilnya. 
$ cat > hello.txt
dog cat
cat duck 
dog chicken
chicken duck
chicken cat
dog duck 
[Ctrl-d] 
$ cat hello.txt | sort | uniq
$ cat hello.txt | grep “dog” | grep –v “cat” 
 
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/99edcbb1-ccaa-4664-b8d1-4d62e0ff5950)

Keterangan: Perintah pertama membuat file hello.txt dan mengisinya dengan teks yang diberikan. Perintah kedua akan menampilkan isi file hello.txt yang sudah diurutkan secara alfabetis. Perintah ketiga akan menampilkan baris-baris dari file hello.txt yang mengandung kata "dog" tetapi tidak mengandung kata "cat".
LAPORAN RESMI: 
1.	Analisa hasil percobaan 1 sampai dengan 4, untuk setiap perintah jelaskan tampilannya.
2.	Kerjakan latihan diatas dan analisa hasilnya
3.	Berikan kesimpulan dari praktikum ini.
Kesimpulan: Pemahaman Operator: Penting untuk memahami berbagai operator yang digunakan dalam lingkungan Unix/Linux, seperti operator redirection (>, >>, <) untuk mengalihkan input dan output, serta operator pipeline (|) untuk menghubungkan output dari satu perintah ke input dari perintah lainnya.
