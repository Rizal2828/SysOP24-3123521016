# SERIAL
![WhatsApp Image 2024-05-16 at 19 00 26](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/c7f331c8-5256-4282-ab00-8f0751f2dbfd)

Serial adalah metode pemrosesan di mana tugas-tugas dijalankan satu per satu dalam urutan yang telah ditentukan. Setiap tugas harus diselesaikan sepenuhnya sebelum tugas berikutnya dapat dimulai. Ini memastikan bahwa tidak ada dua tugas yang berjalan secara bersamaan.

Contoh serial dalam kehidupan sehari-hari:
- Mengantri di kasir: Setiap pelanggan dilayani satu per satu, dan pelanggan berikutnya hanya bisa dilayani setelah pelanggan sebelumnya selesai.
- Pemrograman: Sebuah program yang mengeksekusi instruksi satu per satu, di mana setiap instruksi harus selesai sebelum instruksi berikutnya dimulai.

# konkuren, parallel, dan konkuren paralel
![WhatsApp Image 2024-05-16 at 19 00 25](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/b9458562-d6e3-4c5c-a654-c89b20bd397d)
# Konkuren
Konkuren adalah metode pemrosesan di mana beberapa tugas atau proses dijalankan secara tumpang tindih dalam waktu. Ini tidak berarti bahwa tugas-tugas tersebut berjalan benar-benar bersamaan, tetapi mereka saling berbagi waktu CPU melalui pengalihan konteks (time-slicing). Pemrosesan konkuren memungkinkan sistem untuk menangani beberapa tugas secara efektif tanpa harus menunggu satu tugas selesai sepenuhnya sebelum memulai yang lain.

Contoh konkuren dalam kehidupan sehari-hari:
- Multitasking di komputer: Sistem operasi dapat menjalankan beberapa aplikasi seperti browser, pemutar musik, dan pengolah kata secara bersamaan dengan cara beralih di antara tugas-tugas ini sangat cepat sehingga pengguna merasakan seolah-olah semuanya berjalan secara bersamaan.
- Pekerjaan kantor: Seorang sekretaris mungkin menangani panggilan telepon, menulis email, dan menyusun dokumen pada waktu yang hampir bersamaan, berpindah dari satu tugas ke tugas lainnya sesuai kebutuhan.

# parallel
Paralel adalah metode pemrosesan di mana beberapa tugas atau proses dijalankan secara bersamaan pada waktu yang sama. Ini membutuhkan beberapa prosesor atau inti CPU sehingga setiap tugas dapat berjalan di prosesor atau inti yang berbeda secara simultan. Pemrosesan paralel meningkatkan efisiensi dan kecepatan penyelesaian tugas, terutama untuk tugas yang bisa dibagi menjadi subtugas yang lebih kecil dan dikerjakan secara bersamaan.

Contoh paralel dalam kehidupan sehari-hari:
- Prosesor multi-core: Sebuah komputer dengan prosesor multi-core dapat menjalankan beberapa aplikasi atau tugas pada inti prosesor yang berbeda secara bersamaan, seperti menjalankan simulasi kompleks sambil menonton video.
- Pekerjaan rumah: Jika beberapa orang membersihkan rumah bersama-sama, masing-masing orang dapat menangani tugas yang berbeda (menyapu, mengepel, membersihkan jendela) pada saat yang sama, sehingga pekerjaan selesai lebih cepat dibandingkan jika dilakukan sendiri-sendiri.

# konkuren parallel
Konkuren paralel adalah metode pemrosesan di mana beberapa tugas atau proses dijalankan secara tumpang tindih (konkuren) dan beberapa di antaranya berjalan benar-benar bersamaan (paralel). Ini menggabungkan keuntungan dari konkuren dan paralel, memungkinkan penggunaan sumber daya yang efisien dan penyelesaian tugas dengan lebih cepat.

Contoh konkuren parallel dalam kehidupan sehari-hari:
- Server web: Sebuah server yang melayani banyak permintaan dari pengguna secara bersamaan. Setiap permintaan bisa ditangani oleh thread atau proses yang berbeda, dan jika server memiliki beberapa prosesor atau inti, beberapa permintaan bisa diproses secara paralel.
- Pengeditan video: Software pengeditan video dapat mengkodekan berbagai bagian video secara bersamaan menggunakan beberapa inti CPU, sementara juga mengizinkan pengguna untuk melakukan tugas-tugas lain seperti memotong atau menambahkan efek, yang ditangani secara konkuren.
