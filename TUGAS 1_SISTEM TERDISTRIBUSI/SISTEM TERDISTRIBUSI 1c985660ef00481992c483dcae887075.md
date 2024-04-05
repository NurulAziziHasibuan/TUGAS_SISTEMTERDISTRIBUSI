# SISTEM TERDISTRIBUSI

1. install wsl 
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled.png)
    
2. install server host
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%201.png)
    
3. mengganti source list ubuntu 22.04
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%202.png)
    
4. setelah mengganti source list ubuntu maka update dan upgrade dengan perintah “sudo apt update; sudo apt upgrade -y”
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%203.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%204.png)
    
5. install lxc
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%205.png)
    
6. check configurasi 
7. menampilkan template container yang tersedia pada ubuntu masing-masing dengan menggunakan perintah “sudo /usr/share/lxc/templates/”
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%206.png)
    
8. membuat container Ubuntu dengan menjalankan perintah seperti dibawah ini 
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%207.png)
    
9. install nginx
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%208.png)
    
10.  kemudian pindah ke direktori “sites-enabled” dengan menjalankan “cd /etc/nginx/sites-enabled/” lalu ls-la, untuk menampilkan daftar isi dari sebuah direktori, sedangkan cp default azizi.local, untuk membuat salinan dari file “default” dan diberi nama “azizi.local”. lalu masuk ke, “nano azizi.local”
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/98ebae98-2267-40d5-8ab5-95c2d5e47e33.png)
    
    lalu masuk pada file local 
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%209.png)
    
11. Tes konfigurasi
    
    sudo nginx -t
    
    sudo nginx -s reload
    
    Kemudian masuk ke direktori var/www/html
    
    sudo cp index.nginx-debian.html index.html
    
    lalu masuk ke, sudo nano index.html
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/d9be68f4-d81e-4265-b7ad-59ef7a681bb2.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%2010.png)
    
12. kemudian masuk ke ssd C - windows -system32 - drivers - etc - hosts, lalu buka file hosts pada notepad, kemudian tambahkan seperti gambar dibawah 
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%2011.png)
    
13. lalu masuklah ke web browser dengan mengetikkan nama file local yang telah dibuat sebelumnya sehingg muncul tampilan seperti dibawah ini 
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/24716eff-be11-4ece-ad2f-a0d756400115.png)
    
14. cat index.html
    
    untuk menampilakn isi dari file di terminal
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/Untitled%2012.png)
    
15. sudo lxc-create -n microservice1 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --server [images.linuxcontainers.org](http://images.linuxcontainers.org/)
    
    sudo lxc-create -n microservice2 -t download -- --dist ubuntu --release bionic --arch amd64 --force-cache --server [images.linuxcontainers.org](http://images.linuxcontainers.org/)
    
    perintah diatas digunakan untuk membuat sebuah kontainer lxc
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/bf51c6e8-bdaa-4925-8be8-7d4d08f451b8.png)
    
16. sudo lxc-start -n microservice2
    
    sudo lxc-attach -n microservice2
    
    sudo lxc-ls -f, untuk mengecek status mcsv2 apakah sudah running
    
    perintah diatas juga berlaku untuk microservice1
    
17. chech ip pada mcsv2 dan mcsv1
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/8734e926-c021-4a38-96e9-e62c1a9a3571.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/3ed9c424-ce55-4102-aade-745046d93499.png)
    
18. apt install nano pada mcsv1 dan mcsv2
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/d38642be-f91e-4ba4-b893-3f503fd856d9.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/41b51de3-515d-4e44-9084-800ad76212db.png)
    
19. lalu buatlah perintah yaml untuk mcsv1 dan mcsv2 dengan menjalankan perintah “sudo nano/etc/netplan/10-lxc.yaml”
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/5496dc4d-4bd6-4df5-a9e9-5fa0216f19a8.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/96371153-3140-4e7f-b4f0-6358e6b1b794.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/8ca19c0a-57c2-4aaa-8ada-681dafa7b542.png)
    
20. lalu, jalankan sudo netplan apply pada mcsv1 dan mcsv2
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/eed2f73e-358e-4c78-a36a-8b084eb594e8.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/4d42379e-f674-4623-b300-916a514d4452.png)
    
21. ping [google.com](http://google.com) pada mcsv1 dan mcsv2
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/79978216-c980-454d-ba15-b266cc96f6f5.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/54561837-3215-453b-8b62-3e9a317a5a16.png)
    
22. selanjutnya, update dan upgradelah mcsv1 dan mcsv2
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/f278ad20-7ea6-4e07-9e4e-ab438e6b0a80.png)
    
23. install nginx nginx-extras pada mcsv1 dan mcsv2 
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/eb01259a-a224-4461-881c-e77da2b93518.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/041f8c7a-f5ab-40ce-aea2-29f4d45cbe3a.png)
    
24. Masuk ke direktori var/www/html
    
    cd /var/www/html/
    
    berlaku pada mcsv1 dan mcsv2
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/257a8a23-665c-47d7-969c-649125347348.png)
    
25. ls
    
    nano index.nginx-debian.html
    
    kemudian merubah isinya seperti gambar dibawah
    
    pada mcsv1 dan mcsv2
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/046586bb-760c-416e-81b7-651b3a05c335.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/0e94a21c-0601-4d5b-9819-0fde592b29cf.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/f9f61076-7d28-48e7-96ba-b53670f90409.png)
    
26. curl [localhost](http://localhost) untuk mengirim permintaan HTTP ke alamat localhost pada mcsv1 dan mcsv2 
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/9168d048-4c39-49a2-881d-4249d9653792.png)
    
27. Masuk ke direktori sites-enabled cd sites-enabled, ls cp default mcsv1.local nano mcsv1.local berlaku juga untuk mcsv2
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/aed11887-786e-4a59-85dd-ed5a5450bef6.png)
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/2561c572-b071-4e7f-93b3-8082f517f4ba.png)
    
28. sudo nano /etc/hosts
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/2a3d53e8-9267-4cb4-9eb2-9f8fb0875271.png)
    
29. curl mcsv1.local
    
    curl mcsv2.local
    
30. sudo nano “nama file local”
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/6c3a4c5e-bad3-4586-be1a-6001a6e01d05.png)
    
31. lalu buka web browser ketik nama file local yang telah dibuat sebelumnya, akan muncul tampilan seperti dibawah
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/3c0e0a00-57c3-416f-9ae0-03180d1a9501.png)
    
32. lalu buka web browser ketik nama file lokal masing-masing yang telah dibuat tadi, akan muncul tampilan seperti dibawah
    
    ![Untitled](SISTEM%20TERDISTRIBUSI%201c985660ef00481992c483dcae887075/d298e76f-2bed-4575-b5c2-cb31000445eb.png)