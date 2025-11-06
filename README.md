# Percobaan 2 : Lab - Build a Switch and Router Network 

## Link Youtube : 
https://youtu.be/cLW8ftr3VDQ?si=WUygGsWyZ2x5zV8r

## Ping PC-B Gagal
![WhatsApp Image 2025-11-03 at 01 25 22_c8de9843](https://github.com/user-attachments/assets/cce954be-1231-48f7-88da-16dc3060de01)

<p align="justify">
Ping gagal karena router interface (default gateway) belum dikonfigurasi. Saat router interface belum diatur dengan alamat IP yang sesuai pada masing-masing jaringan (subnet), maka perangkat yang berada di jaringan tersebut tidak memiliki jalur (gateway) untuk mengirim paket ke jaringan lain. Akibatnya, komunikasi hanya bisa terjadi di dalam subnet yang sama (Layer 2), tetapi tidak bisa menembus ke subnet lain (Layer 3). Dengan kata lain, proses routing antar jaringan tidak terjadi karena router belum memiliki konfigurasi yang memungkinkan untuk meneruskan atau mengarahkan paket data antar subnet.
Selain itu, tanpa konfigurasi pada interface router, perangkat end-user tidak dapat mengenali gateway mana yang harus digunakan untuk mengirim paket ke luar jaringannya. Oleh karena itu, meskipun perangkat masih dapat berkomunikasi secara lokal (misalnya dengan perangkat yang memiliki IP dalam subnet yang sama), perintah ping ke alamat IP di subnet lain akan gagal karena tidak ada mekanisme Layer 3 yang aktif untuk meneruskan paket ke tujuan tersebut.
</p>

## Ping PC-B Berhasil
![FIX](https://github.com/user-attachments/assets/0097b528-1865-4458-8ecc-eed11cecfac1)

<p align="justify">
Ping berhasil karena router sudah melakukan proses routing antar subnet. Setelah interface pada router dikonfigurasi dengan benar (misalnya telah diberikan alamat IP pada masing-masing interface yang terhubung ke subnet berbeda dan diaktifkan), router dapat berfungsi sebagai penghubung antar jaringan. Dengan konfigurasi tersebut, router mampu meneruskan paket ICMP (ping) dari satu subnet ke subnet lain melalui proses routing di Layer 3. Selain itu, switch Cisco 2960 secara default akan mengaktifkan port-port yang terhubung ke perangkat aktif, seperti PC atau router, tanpa memerlukan konfigurasi tambahan. Hal ini memungkinkan komunikasi berjalan lancar di Layer 2, sementara router menangani lalu lintas antar subnet di Layer 3. Dengan adanya kombinasi fungsi tersebut switch yang menghubungkan perangkat dalam subnet yang sama, dan router yang mengarahkan lalu lintas antar subnet maka ketika perintah ping dijalankan antar host di subnet berbeda, paket ICMP dapat dikirim dan diterima dengan sukses. Ini menunjukkan bahwa konektivitas jaringan sudah berfungsi dengan baik dari sisi konfigurasi interface maupun proses routing-nya.
</p>

## Topologi Jaringan
 <img width="681" height="218" alt="image" src="https://github.com/user-attachments/assets/66b3fa0e-e153-441a-93d0-9578534e9648" />
