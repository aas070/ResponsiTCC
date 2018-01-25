# ResponsiTCC


# Overview Praktikum Teknologi CLoud Computing
# A. Pengenalan Docker
## Dimulai dari pengertian Docker yang merupakan sebuah project open-source yang menyediakan platform terbuka untuk developer maupun sysadmin untuk dapat membangun, mengemas, dan menjalankan aplikasi dimanapun sebagai sebuah wadah (container) yang ringan. 
### 1. Dokcer Images
#### Lalu, menciptakan sebuah image Docker. Disini saya menggunakan httpd sebagai image - nya. Cara membuatnya : Pertama harus memiliki akun di github terlebih dahulu ataupun dockerHub. Jikalau sudah memiliki keduanya tinggal eksekusi saja. Jikalau belum buat keduanya terlebih dahulu. Langkah selanjutnya, membuat direktori lewat terminal (example : #mkdir ujian) kemudian, masuk ke direktori tersebut (#cd ujian). Buat file Dockerfile untuk menuliskan semua perintah yang akan dieksekusi. Jikalau sudah, buat image (#docker build -t httpd .). Tunggu sejenak, proses, dan nanti akan berhasil membuat image. Setelah membuat image, lalu di push ke dockerHub. Lakukan login ke dockerHub, commit (#docker commit idcontainer httpd), tag (#docker tag userdockerhub/httpd) dan push (#docker push userdockerhub/http) di dockerHub tersebut. Cek di dockerHub apakah sudah terupload atau belum.

### 2. Docker Composes
#### Docker compose sendiri merupakan tool yang digunakan untuk menggabungkan image-image docker yang sudah dibuat atau yang sudah ada. Kemarin saya menggunakan image wordpress yang akan di compose. Caranya : membuat direktori seperti sebelum - sebelumnya, kemudian, masuk ke dalam direktori tersebut. Lalu, memasukkan script di file docker-compose.yml. Dalam file tersebut berisi image apa saja yang akan dicompose. Saya menggunakan image mysql dan wordpress. Jika sudah, langsung di build compose nya tadi dengan perintah #docker-compose up -d. Jika berhasil maka cek di http://localhost:8000 nanti akan masuk ke dalam halaman wordpress dan siap untuk digunakan.


### 3. Docker Machine
#### Kali ini menggunakan docker swarm. Dimana swarm ini akan membagi - bagi menjadi beberapa cluster. Service tool yang saya gunakan adalah virtualbox. Cara membuatnya : Pertama sudah memiliki direktori terlebih dahulu, masuk ke dalam direktori tersebut. (Notes : sudah terinstal docker machine nya ya disini). Melanjutkan untuk membuat node 1 dengan perintah (#docker-machine create --driver virtualbox endah1) dan buat node 2 nya sama hanya penamaan nodenya menjadi endah2. Disini nanti akan melihat mana yang menjadi worker dan manager. Perintah selanjutnya adalah #docker ssh endah1, masukkan perintah #docker swarm init --advertise-addr (IP docker laptop kita) dan akan ada hasilnya. Hasil tersebut dicopy dan dipaste di node endah2. Setelah keluar dari node endah2, masuk lagi ke node endah1 guna menentukan servicenya. Mengunakan perintah #docker service create --name endah -p 80:80 --replicas 2 userdockerHub/nama images. Kemudian, untuk pengecekannya docker service ls. Untuk menentukan scale nya gunakan perintah #docker service scale endah=6 dan untuk melihatnya #docker service ps endah.

### 4. Kubernetes
#### Menggunakan minikube yang merupakan bentuk kecilnya kubernetes. Disini implementasinya menggunakan document dari minikube. (tutorial internet)

### 5. Uni Kernels
#### Menggunakan unikernel yang implementasinya dari document unikernels sendiri. (tutorial internet)




######## By : ENDAH PRASTIWI/165410225
