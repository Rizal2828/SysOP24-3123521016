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


# dining problem 
Masalah dining philosophers (atau masalah filsuf makan) adalah sebuah masalah klasik dalam ilmu komputer yang menggambarkan situasi di mana beberapa filsuf duduk mengelilingi meja bundar, masing-masing dengan sebuah piring spaghetti. Di antara setiap pasangan filsuf, terdapat sebuah garpu. Untuk makan, setiap filsuf membutuhkan dua garpu—satu dari kanan dan satu dari kiri. Masalah ini menggambarkan tantangan dalam mengelola sumber daya yang terbatas (garpu) tanpa menyebabkan kondisi deadlock atau starvation. Dalam konteks pemrograman sinkronisasi, solusi harus menjamin bahwa tidak ada dua filsuf yang mengambil garpu yang sama pada waktu yang sama, serta menghindari kondisi di mana semua filsuf secara bersamaan memegang satu garpu dan menunggu garpu kedua (deadlock).
  
# Solusi dengan Semaphore
#include <pthread.h>
#include <semaphore.h>
#include <stdio.h>
#include <unistd.h>

#define N 5 // Jumlah filsuf
#define THINKING 0
#define HUNGRY 1
#define EATING 2
#define LEFT (i + 4) % N
#define RIGHT (i + 1) % N

int state[N];
int phil[N] = {0, 1, 2, 3, 4};

sem_t mutex;
sem_t S[N];

void test(int i)
{
    if (state[i] == HUNGRY && state[LEFT] != EATING && state[RIGHT] != EATING)
    {
        // keadaan di mana filsuf dapat makan
        state[i] = EATING;
        sleep(1);
        printf("Filsuf %d mengambil garpu %d dan %d\n", i + 1, LEFT + 1, i + 1);
        printf("Filsuf %d sedang makan\n", i + 1);
        sem_post(&S[i]);
    }
}

void take_fork(int i)
{
    sem_wait(&mutex);
    state[i] = HUNGRY;
    printf("Filsuf %d sedang lapar\n", i + 1);
    test(i);
    sem_post(&mutex);
    sem_wait(&S[i]);
    sleep(1);
}

void put_fork(int i)
{
    sem_wait(&mutex);
    state[i] = THINKING;
    printf("Filsuf %d meletakkan garpu %d dan %d\n", i + 1, LEFT + 1, i + 1);
    printf("Filsuf %d sedang berpikir\n", i + 1);
    test(LEFT);
    test(RIGHT);
    sem_post(&mutex);
}

void* philosopher(void* num)
{
    while (1)
    {
        int* i = num;
        sleep(1);
        take_fork(*i);
        sleep(0); // waktu makan
        put_fork(*i);
    }
}

int main()
{
    int i;
    pthread_t thread_id[N];

    sem_init(&mutex, 0, 1);

    for (i = 0; i < N; i++)
        sem_init(&S[i], 0, 0);

    for (i = 0; i < N; i++)
    {
        pthread_create(&thread_id[i], NULL, philosopher, &phil[i]);
        printf("Filsuf %d sedang berpikir\n", i + 1);
    }

    for (i = 0; i < N; i++)
        pthread_join(thread_id[i], NULL);
}

# Penjelasan Solusi
- Inisialisasi Semaphores: sem_init(&mutex, 0, 1) digunakan untuk menginisialisasi semaphore mutex sebagai kunci biner (binary semaphore). Setiap semaphore S[i] diinisialisasi dengan nilai awal 0.
- Fungsi test: Fungsi ini memeriksa apakah filsuf i bisa makan dengan memeriksa keadaan dari filsuf di sebelah kiri dan kanannya. Jika keduanya tidak sedang makan, maka filsuf i dapat mengambil garpu dan mulai makan.
- Fungsi take_fork: Filsuf mencoba mengambil garpu. Jika kondisi memungkinkan, ia akan mendapatkan kedua garpu dan mulai makan.
- Fungsi put_fork: Setelah selesai makan, filsuf meletakkan kembali garpu dan memberitahu filsuf di sebelah kiri dan kanannya untuk memeriksa apakah mereka bisa mulai makan.
- Fungsi philosopher: Merupakan fungsi yang dijalankan oleh setiap thread filsuf. Filsuf akan terus berpikir dan makan dalam loop tak berujung.

# Reader Writer Problem
Masalah Reader-Writer adalah masalah sinkronisasi klasik dalam ilmu komputer yang melibatkan beberapa proses pembaca (reader) dan penulis (writer) yang berusaha mengakses sumber daya bersama (biasanya sebuah database atau file) secara bersamaan. Masalah ini bertujuan untuk memastikan bahwa beberapa pembaca dapat membaca secara bersamaan, tetapi penulis memerlukan akses eksklusif.

# Solusi dengan Semaphore
#include <pthread.h>
#include <semaphore.h>
#include <stdio.h>
#include <unistd.h>

sem_t wrt;
pthread_mutex_t mutex;
int read_count = 0;
int data = 0;  // Sumber daya bersama

void* writer(void* wno) {
    while (1) {
        // Penulis menunggu untuk mendapatkan akses ke sumber daya
        sem_wait(&wrt);
        data++;  // Menulis data (sebagai contoh, menambah nilai data)
        printf("Penulis %d menulis data: %d\n", *((int*)wno), data);
        sleep(1);  // Simulasi waktu penulisan
        // Penulis melepaskan akses ke sumber daya
        sem_post(&wrt);
        sleep(1);  // Penundaan sebelum mencoba menulis lagi
    }
}

void* reader(void* rno) {
    while (1) {
        // Pembaca mendapatkan akses ke read_count
        pthread_mutex_lock(&mutex);
        read_count++;
        if (read_count == 1) {
            // Pembaca pertama yang masuk, meminta akses ke sumber daya
            sem_wait(&wrt);
        }
        pthread_mutex_unlock(&mutex);

        // Membaca data
        printf("Pembaca %d membaca data: %d\n", *((int*)rno), data);
        sleep(1);  // Simulasi waktu pembacaan

        // Pembaca melepaskan akses ke read_count
        pthread_mutex_lock(&mutex);
        read_count--;
        if (read_count == 0) {
            // Pembaca terakhir yang keluar, melepaskan akses ke sumber daya
            sem_post(&wrt);
        }
        pthread_mutex_unlock(&mutex);
        sleep(1);  // Penundaan sebelum mencoba membaca lagi
    }
}

int main() {
    pthread_t read[5], write[2];
    pthread_mutex_init(&mutex, NULL);
    sem_init(&wrt, 0, 1);

    int reader_ids[5] = {1, 2, 3, 4, 5};
    int writer_ids[2] = {1, 2};

    // Membuat thread untuk penulis
    for (int i = 0; i < 2; i++) {
        pthread_create(&write[i], NULL, writer, &writer_ids[i]);
    }

    // Membuat thread untuk pembaca
    for (int i = 0; i < 5; i++) {
       
# Penjelasan Solusi
1. Inisialisasi Semaphore dan Mutex:
- sem_init(&wrt, 0, 1): Inisialisasi semaphore wrt untuk mengendalikan akses ke sumber daya bersama.
- pthread_mutex_init(&mutex, NULL): Inisialisasi mutex mutex untuk mengendalikan akses ke read_count.

2. Fungsi Writer:
- Penulis mendapatkan akses eksklusif ke sumber daya dengan sem_wait(&wrt).
- Menulis data ke sumber daya bersama.
- Melepaskan akses eksklusif dengan sem_post(&wrt).

3. Fungsi Reader:
- Pembaca pertama yang masuk akan meminta akses ke sumber daya dengan sem_wait(&wrt).
- Setiap pembaca menambah read_count yang dilindungi oleh mutex.
- Membaca data dari sumber daya bersama.
- Pembaca terakhir yang keluar akan melepaskan akses ke sumber daya dengan sem_post(&wrt).

4. Thread Creation and Joining:
- Membuat dan menjalankan thread pembaca dan penulis.
- Bergabung dengan thread untuk memastikan program berjalan sampai semua thread selesai.
