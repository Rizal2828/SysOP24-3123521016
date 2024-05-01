Buat tulisan tentang konsep fork dan implementasinya dengan menggunakan bahasa pemrograman C! (minimal 2 paragraf disertai dengan gambar)
Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git
Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode program fork01.c, fork02.c, fork03.c
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/70ffb73e-4bb2-4798-9a3c-ced123d38eaa)

lalu masuk ke superuser dengan mengetikan su -
lalu ketik sudo apt intsall gcc g++

Perintah sudo apt install gcc g++ adalah perintah yang digunakan untuk menginstal compiler GNU untuk bahasa pemrograman C dan C++ di sistem operasi berbasis Debian.
gcc adalah compiler untuk bahasa pemrograman C.
g++ adalah compiler untuk bahasa pemrograman C++.
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/5c514627-2d77-4eac-9511-7374ba24502b)

Output program ini menampilkan ID proses (PID), ID proses parent (PPID), dan ID pengguna (UID). Setelah mencetak informasi tersebut, program akan berhenti selama tiga detik sebelum mencetak informasi lagi. Program ini looping sebanyak tiga kali.

lalu ketikan nano fork01.cpp lalu ketikan program berikut :
using namespace std;

#include <iostream>
#include <sys/types.h>
#include <unistd.h>

int main(void) {
pid_t mypid;
uid_t myuid;
for (int i = 0; i < 3; i++) {
mypid = getpid();
cout << "I am process " << mypid << endl;
cout << "My parent process ID is " << getppid() << endl;
cout << "The owner of this process has uid " << getuid()
<< endl;
sleep(3);
}
return 0;
}

lalu untuk keluar krtikan ctrl x untuk exit lalu pilih y untuk mrngrsave dan enter
lalu ketikan Perintah g++ fork01.cpp -o fork01.exe
perintah tersebut untuk mengkompilasi program C++ yang disebut "fork01.cpp" menggunakan compiler g++ dan memberikan output dengan nama "fork01.exe".
lalu ketikan ./fork01.exe untuk menjalankan program tersebut

Output program menampilkan ID proses (PID) mereka sendiri dan nilai variabel x dalam loop tak terbatas. Program menggunakan system call fork() untuk membuat proses saat ini, dan menciptakan child process.
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/18d6bab1-7f2d-47f7-aa49-0629bf28cdf8)
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/ed5bdbc7-98b4-4665-9818-360502b76780)

untuk yang ke 2 caranya sama seperti fork1

ketikan nano fork02.cpp
lalu ketikan kode berikut :
#include <iostream>
#include <sys/types.h>
#include <unistd.h>
using namespace std;

int main(void) {
pid_t childpid;
int x = 5;
childpid = fork();
while (1) {
cout << "This is process ID" << getpid() << endl;
cout << "In this process the value of x becomes " << x << endl;	
sleep(2);
x++;
}
return 0;
}
lalu jalankan seperti contoh fork01
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/87137b15-39df-4771-998a-cc1abdefa7f6)
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/6e92d59c-6869-4596-94c7-f6f094e349d1)

ke 3 caranya sama seperti fork1
#include <iostream>
using namespace std;
#include <sys/types.h>
#include <unistd.h>

int main(void) {
pid_t childpid;
childpid = fork();
for (int i = 0; i < 5; i++) {
cout << "This is process " << getpid() << endl;
sleep(2);
}
return 0;
}
![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/ced9e64e-a4d7-4851-a326-38f74c3709f3)

![image](https://github.com/Rizal2828/SysOP24-3123521016/assets/160558552/8ed973b8-fdbb-4af3-88c2-dd4ce57bb405)


