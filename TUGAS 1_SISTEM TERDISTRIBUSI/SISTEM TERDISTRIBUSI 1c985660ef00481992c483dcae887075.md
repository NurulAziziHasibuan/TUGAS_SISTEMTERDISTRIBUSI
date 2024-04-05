# SISTEM TERDISTRIBUSI

1. install wsl 
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled.png?raw=true)
    
2. install server host
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%201.png?raw=true)
    
3. mengganti source list ubuntu 22.04
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%202.png?raw=true)
    
4. setelah mengganti source list ubuntu maka update dan upgrade dengan perintah “sudo apt update; sudo apt upgrade -y”
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%203.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%204.png?raw=true)
    
5. install lxc
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%205.png?raw=true)
    
6. check configurasi 
7. menampilkan template container yang tersedia pada ubuntu masing-masing dengan menggunakan perintah “sudo /usr/share/lxc/templates/”
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%206.png?raw=true)
    
8. membuat container Ubuntu dengan menjalankan perintah seperti dibawah ini 
    
   ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%207.png?raw=true)
    
9. install nginx
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%208.png?raw=true)
    
10.  kemudian pindah ke direktori “sites-enabled” dengan menjalankan “cd /etc/nginx/sites-enabled/” lalu ls-la, untuk menampilkan daftar isi dari sebuah direktori, sedangkan cp default azizi.local, untuk membuat salinan dari file “default” dan diberi nama “azizi.local”. lalu masuk ke, “nano azizi.local”
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/98ebae98-2267-40d5-8ab5-95c2d5e47e33.png?raw=true)
    
    lalu masuk pada file local 
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%209.png?raw=true)
    
11. Tes konfigurasi
    
    sudo nginx -t
    
    sudo nginx -s reload
    
    Kemudian masuk ke direktori var/www/html
    
    sudo cp index.nginx-debian.html index.html
    
    lalu masuk ke, sudo nano index.html
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/d9be68f4-d81e-4265-b7ad-59ef7a681bb2.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%2010.png?raw=true)
    
12. kemudian masuk ke ssd C - windows -system32 - drivers - etc - hosts, lalu buka file hosts pada notepad, kemudian tambahkan seperti gambar dibawah 
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%2011.png?raw=true)
    
13. lalu masuklah ke web browser dengan mengetikkan nama file local yang telah dibuat sebelumnya sehingg muncul tampilan seperti dibawah ini 
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/24716eff-be11-4ece-ad2f-a0d756400115.png?raw=true)
    
14. cat index.html
    
    untuk menampilakn isi dari file di terminal
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/Untitled%2012.png?raw=true)
    
15. sudo lxc-create -n microservice1 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --server [images.linuxcontainers.org](http://images.linuxcontainers.org/)
    
    sudo lxc-create -n microservice2 -t download -- --dist ubuntu --release bionic --arch amd64 --force-cache --server [images.linuxcontainers.org](http://images.linuxcontainers.org/)
    
    perintah diatas digunakan untuk membuat sebuah kontainer lxc
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/bf51c6e8-bdaa-4925-8be8-7d4d08f451b8.png?raw=true)
    
16. sudo lxc-start -n microservice2
    
    sudo lxc-attach -n microservice2
    
    sudo lxc-ls -f, untuk mengecek status mcsv2 apakah sudah running
    
    perintah diatas juga berlaku untuk microservice1
    
17. chech ip pada mcsv2 dan mcsv1
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/8734e926-c021-4a38-96e9-e62c1a9a3571.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/4d42379e-f674-4623-b300-916a514d4452.png?raw=true)
    
18. apt install nano pada mcsv1 dan mcsv2
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/d38642be-f91e-4ba4-b893-3f503fd856d9.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/41b51de3-515d-4e44-9084-800ad76212db.png?raw=true)
    
19. lalu buatlah perintah yaml untuk mcsv1 dan mcsv2 dengan menjalankan perintah “sudo nano/etc/netplan/10-lxc.yaml”
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/5496dc4d-4bd6-4df5-a9e9-5fa0216f19a8.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/96371153-3140-4e7f-b4f0-6358e6b1b794.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/8ca19c0a-57c2-4aaa-8ada-681dafa7b542.png?raw=true)
    
20. lalu, jalankan sudo netplan apply pada mcsv1 dan mcsv2
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/eed2f73e-358e-4c78-a36a-8b084eb594e8.png?raw=true)
    
21. ping [google.com](http://google.com) pada mcsv1 dan mcsv2
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/79978216-c980-454d-ba15-b266cc96f6f5.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/54561837-3215-453b-8b62-3e9a317a5a16.png?raw=true)
    
22. selanjutnya, update dan upgradelah mcsv1 dan mcsv2
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/f278ad20-7ea6-4e07-9e4e-ab438e6b0a80.png?raw=true)
    
23. install nginx nginx-extras pada mcsv1 dan mcsv2 
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/eb01259a-a224-4461-881c-e77da2b93518.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/041f8c7a-f5ab-40ce-aea2-29f4d45cbe3a.png?raw=true)
    
24. Masuk ke direktori var/www/html
    
    cd /var/www/html/
    
    berlaku pada mcsv1 dan mcsv2
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/046586bb-760c-416e-81b7-651b3a05c335.png?raw=true)
    
25. ls
    
    nano index.nginx-debian.html
    
    kemudian merubah isinya seperti gambar dibawah
    
    pada mcsv1 dan mcsv2
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/0e94a21c-0601-4d5b-9819-0fde592b29cf.png?raw=true)
    
26. curl [localhost](http://localhost) untuk mengirim permintaan HTTP ke alamat localhost pada mcsv1 dan mcsv2 
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/0e94a21c-0601-4d5b-9819-0fde592b29cf.png?raw=true)
    
27. Masuk ke direktori sites-enabled cd sites-enabled, ls cp default mcsv1.local nano mcsv1.local berlaku juga untuk mcsv2
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/aed11887-786e-4a59-85dd-ed5a5450bef6.png?raw=true)
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/2561c572-b071-4e7f-93b3-8082f517f4ba.png?raw=true)
    
28. sudo nano /etc/hosts
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/2a3d53e8-9267-4cb4-9eb2-9f8fb0875271.png?raw=true)
    
29. curl mcsv1.local
    
    curl mcsv2.local
    
30. sudo nano “nama file local”
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/6c3a4c5e-bad3-4586-be1a-6001a6e01d05.png?raw=true)
    
31. lalu buka web browser ketik nama file local yang telah dibuat sebelumnya, akan muncul tampilan seperti dibawah
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/3c0e0a00-57c3-416f-9ae0-03180d1a9501.png?raw=true)
    
32. lalu buka web browser ketik nama file lokal masing-masing yang telah dibuat tadi, akan muncul tampilan seperti dibawah
    
    ![alt text](https://github.com/NurulAziziHasibuan/TUGAS_SISTEMTERDISTRIBUSI/blob/main/TUGAS%201_SISTEM%20TERDISTRIBUSI/d298e76f-2bed-4575-b5c2-cb31000445eb.png?raw=true)
