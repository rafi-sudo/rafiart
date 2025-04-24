---
layout: post
title: Pernah Kalian Susah Akses Samba ini Penyebabnya? 
date: 2025-04-23 17:00:00 +0700
category: tutorial
thumbnail: 'style/image/files.png'
icon: code
---
<p><b>HAI GUYS APAKAH KALIAN PERNAH ALAMI SUSAHNNYA SAAT PENGEN AKSES FILE ATAU PRINTER DI NETWORK DISCOVERY FILE EXPLOLER PC KAMU..</b></p><p>

</p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh4BhTshUkjwmaosPDWR5WbW7802TYoWTZV4baS8SyyjV1bBmd9B348baTTdFqTZ_fs9ZxGzN1YBJI1Ha_vL7qCEUmQapGXX8XdbiE3qk6w_nC47dg7jyDcj74BGkqDGpR2BQLFgq52IfqIYVy5atKRWxjdJHH6GMPyZzq7qHjCvwZtppmcd7yPi8_pFsQ/s1024/VirtualBox_A_20_03_2025_11_44_12.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="768" data-original-width="1024" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh4BhTshUkjwmaosPDWR5WbW7802TYoWTZV4baS8SyyjV1bBmd9B348baTTdFqTZ_fs9ZxGzN1YBJI1Ha_vL7qCEUmQapGXX8XdbiE3qk6w_nC47dg7jyDcj74BGkqDGpR2BQLFgq52IfqIYVy5atKRWxjdJHH6GMPyZzq7qHjCvwZtppmcd7yPi8_pFsQ/s320/VirtualBox_A_20_03_2025_11_44_12.png" width="320" /></a></div>
<p>*Di Network Discovery tidak ada sama sekali PC yang terhubung</p><p>
</p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgoPlAHkSmyl1u9O2YJeUrlgzd83SE4UWW9Tt1d_qn50TtjMRzofB05jq0lbC4eWl3OGTG7fPhdmIoazA4NVYSJhx3KcPeyZlqs009RyVN7dgiAhtb-E6kLrvoebBBBgPXmBtvUnkVYBdt3RswVTEXmhok3aU_Hlkc2PvPUs8I2jZccLkBQhv8o2CsGcZ8/s1024/VirtualBox_A_20_03_2025_11_46_28.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="768" data-original-width="1024" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgoPlAHkSmyl1u9O2YJeUrlgzd83SE4UWW9Tt1d_qn50TtjMRzofB05jq0lbC4eWl3OGTG7fPhdmIoazA4NVYSJhx3KcPeyZlqs009RyVN7dgiAhtb-E6kLrvoebBBBgPXmBtvUnkVYBdt3RswVTEXmhok3aU_Hlkc2PvPUs8I2jZccLkBQhv8o2CsGcZ8/s320/VirtualBox_A_20_03_2025_11_46_28.png" width="320" /></a></div>
<p>*jika diakses malah Windows cannot acces</p><p>
</p><hr />
<p><b>MARI KITA BAHAS MASALAH SEPERTI INI</b></p><p>
</p><p>1. Pertama Hostname tidak dikenali:</p><p>
Coba akses menggunakan Ping IP server langsung, misalnya ping 192.168.x.x di CMD.
Cek apakah Samba aktif di server (jika pakai server) dengan perintah
</p><pre><code id="code-block">
systemctl status smbd
</code>
</pre>
Jika tidak aktif, jalankan:
<pre><code id="code-block">
sudo systemctl start smbd
</code>
</pre>
<p>2. Pastikan didalam jaringan yang sama contoh skema :</p><p>
</p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiRs8jTK6DNIC2um5gY0aHX3JjAFMocVZ04vWT3iDR6a_x_89v7krApNsNKIq9dsbXvH3v9NsertwCtq6Y-uKmjVbmJ78HuBIO2J_wJepN-8HFrb44ozxB46ZicHkTuY7L0hQvY5Y85X8kQSGODv9Fhdr2re2CrpfYFIQniEx0TOGdv0jwlf2zk2VpmK48/s3359/skema%20jaringan%20rumah%20gw.jpg" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="2941" data-original-width="3359" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiRs8jTK6DNIC2um5gY0aHX3JjAFMocVZ04vWT3iDR6a_x_89v7krApNsNKIq9dsbXvH3v9NsertwCtq6Y-uKmjVbmJ78HuBIO2J_wJepN-8HFrb44ozxB46ZicHkTuY7L0hQvY5Y85X8kQSGODv9Fhdr2re2CrpfYFIQniEx0TOGdv0jwlf2zk2VpmK48/s320/skema%20jaringan%20rumah%20gw.jpg" width="320" /></a></div>
jika kalian akses di router yang berbeda dengan segmen IP beda kagak bisa!. Jika mau bisa diakses oleh router berbeda coba IP di satu segmenkan (jangan pakai NAT) atau di mode akses point. Caranya nanti bahas di lain kali ya...
<p>3. Pastikan konfigurasi router Forbid Ping LAN dicentang (resiko UI router kalian bisa di akses)</p><p>
</p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgI5flyyxsXka-JGFxgE79HEp8rBHDgCVuHr4BKw8zJoq9unGlbm5QuO915Lj09SvmXApNSawAqLAh1It-Z18UA_dJRNTBR5pYYzOj_FwejCWsg-oO7YjhkmGQUWhfSDK-6Ai40dwwbM2ADwKait3ADdLbyWOWuP21BvzCWms25L9qxatgCZo4Yz-HUtOA/s662/Screenshot%202025-03-20%20091329.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="449" data-original-width="662" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgI5flyyxsXka-JGFxgE79HEp8rBHDgCVuHr4BKw8zJoq9unGlbm5QuO915Lj09SvmXApNSawAqLAh1It-Z18UA_dJRNTBR5pYYzOj_FwejCWsg-oO7YjhkmGQUWhfSDK-6Ai40dwwbM2ADwKait3ADdLbyWOWuP21BvzCWms25L9qxatgCZo4Yz-HUtOA/s320/Screenshot%202025-03-20%20091329.png" width="320" /></a></div>
jika pakai wifi tamu <b>Allow Guest To Acces My Local Network dan Guest Network Isolation</b> Di Disable, tetapi saran saya untuk tamu jangan deh, takut di bruteforce (login berkali kali pakai hacktool router) atau ngupload malware ke PC/Server mu, jika Samba PC/Server terbuka (tanpa sandi/port diisolasi).
<p>4. Saran saya lebih baik pakai router pihak ketiga seperti gbr diatas pakai TP-LINK WR840N, jika pakai roter ISP coba : </p><p>
</p><p>Binding Port diceklis untuk ke pc client/pc server yang mau dituju sharing file:</p><p>
</p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEirRg9w9lYJFoHJzVbVviY4t5qQtx9vH6FAlCM4JVoMAVDtDVTHYZU-kw2BfZQKYYoBkSqIDEWTsee9KhFDqa6QzU-OtXv72VPzVVQD-sgTBe_VfBHXTulFjXMt_nTRTuTbGPdCqQ67u4MtozfFUlOmBz9skfE9WwqDAOpt6OTXBfiT3atu62KB6oYtE4s/s505/Screenshot%202025-03-20%20092609.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="98" data-original-width="505" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEirRg9w9lYJFoHJzVbVviY4t5qQtx9vH6FAlCM4JVoMAVDtDVTHYZU-kw2BfZQKYYoBkSqIDEWTsee9KhFDqa6QzU-OtXv72VPzVVQD-sgTBe_VfBHXTulFjXMt_nTRTuTbGPdCqQ67u4MtozfFUlOmBz9skfE9WwqDAOpt6OTXBfiT3atu62KB6oYtE4s/s320/Screenshot%202025-03-20%20092609.png" width="320" /></a></div>
<div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEixN6VKZc1neS73E-PgLN71T4xZe4xxn9vzf8cJJrLXdHLmIWocUPJnnIdJ7P9jZdr4DN2isIa1LwAtubFd7xLqQmoA0wxdvUyxvp0VH431-7tAMAMbetzASB8X0KBPs8ZJysKnjy9CLFXWIwPDl-unTuRagTyrpbE9r_zElOpXfjzokrh-_9OCcBlz7vc/s891/Screenshot%202025-03-20%20092922.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="350" data-original-width="891" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEixN6VKZc1neS73E-PgLN71T4xZe4xxn9vzf8cJJrLXdHLmIWocUPJnnIdJ7P9jZdr4DN2isIa1LwAtubFd7xLqQmoA0wxdvUyxvp0VH431-7tAMAMbetzASB8X0KBPs8ZJysKnjy9CLFXWIwPDl-unTuRagTyrpbE9r_zElOpXfjzokrh-_9OCcBlz7vc/s320/Screenshot%202025-03-20%20092922.png" width="320" /></a></div>
<p>Pastikan Firewall Security Level ada di configurasi <b>Lower</b></p><p>
</p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhaqdm-wI34XPgjAPLHBGsOyfT8OOzQ8SG5KuiEY6rsHNQyPC5LfgKq3w18jrrHYCWw7_z72CJ7THep6cQeKdumeJE8zXZGyDv3EOrKoPY7HqkY6KSj8dC1m43NXciX4LsRfDJrYTFnCvGMljK1W5Yga4nC9a_8bXVGoUEj_x2X_vljRnGphihr5vfhlbM/s490/Screenshot%202025-03-20%20093044.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="199" data-original-width="490" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhaqdm-wI34XPgjAPLHBGsOyfT8OOzQ8SG5KuiEY6rsHNQyPC5LfgKq3w18jrrHYCWw7_z72CJ7THep6cQeKdumeJE8zXZGyDv3EOrKoPY7HqkY6KSj8dC1m43NXciX4LsRfDJrYTFnCvGMljK1W5Yga4nC9a_8bXVGoUEj_x2X_vljRnGphihr5vfhlbM/s320/Screenshot%202025-03-20%20093044.png" width="320" /></a></div>
<p>Pastikan Port yang dibutuhkan sharing file seperti NetBiosTCP/IP,FTP,WebDAV,SMB/Cifs445/139/137-8 tidak terfilter di router :</p><p>
</p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhkx2hnlMGKSIn3Z_Rvmf3M3NNSbgWVAUm3DZgZUgNEcgA-1oHkH3xmPzzv_HQl0-LTIQ8p4xUDawZpas9JaHDkF3yGeS_9KE00meTAJwcn_8f3mLarHuluFTokP3usyKDXpnkp46VXBRcMKIRhHl9s3ZWjK_rhVnE8_0V1bHyQnk9NHViqzRAB43_uWIY/s757/Screenshot%202025-03-20%20093929.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="516" data-original-width="757" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhkx2hnlMGKSIn3Z_Rvmf3M3NNSbgWVAUm3DZgZUgNEcgA-1oHkH3xmPzzv_HQl0-LTIQ8p4xUDawZpas9JaHDkF3yGeS_9KE00meTAJwcn_8f3mLarHuluFTokP3usyKDXpnkp46VXBRcMKIRhHl9s3ZWjK_rhVnE8_0V1bHyQnk9NHViqzRAB43_uWIY/s320/Screenshot%202025-03-20%20093929.png" width="320" /></a></div>
*didalam gambar tidak ada yng difilter..
<hr />
<p><b>SOLUSI DIATAS SUDAH CUKUP APALAGI JIKA SHARING FILE MENGGUNAKAN PERANTARA SERVER(DIWINDOWS/LINUX), JIKA MASIH ERROR BISA PENYEBABNYA DARI KONFIGURASI SERVER</b></p><p>
</p><p>Jika file sharing antar Windows atau PC Lain tanpa perantara server SMB, bisa jadi masalah ada di PC kamu (di fitur Network Discovery).</p><p>
</p><p><b>KITA BAHAS MASALAH DI WINDOWS MU</b></p><p>
</p><p>1. Pertama pastikan Network And Sharing Center di konfigurasi:</p><p>
   </p><p><a>Network Discovery : ON</a><a></a></p><p><a>
   </a></p><p><a>File and Printer Sharing :ON</a><a></a></p><p><a>
   </a></p><p><a>File Sharing Connection : pilih yang direkomendasikan windows</a><a></a></p><p><a>
   </a></p><p><a>Turn Off Password Protected Sharing</a></p><p><a>    
</a></p><p><a>2. Pastikan fitur pendukung File Sharing (FTP,SMB/cifs,Netbios) aktif di windows mu)</a></p><p><a>
</a></p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg0EANSJYoJ9ywmRnEchm4otroliICcaP2t4wJqOCH6z5H7z7eRdyjd6ivquXSDp2y1O9fTWuYw7x2hzpiKYvFv6MM7GWtSo7-tP3S7b3kDSqIqQTKTujCSy2bUSZ0_7OUDeZja7QRSdjU-sEcmlqR8QpZC27RdprR6Oj9VfPa8N762_eNug6umqtPj6nE/s399/Screenshot%202025-03-20%20100450.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="195" data-original-width="399" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg0EANSJYoJ9ywmRnEchm4otroliICcaP2t4wJqOCH6z5H7z7eRdyjd6ivquXSDp2y1O9fTWuYw7x2hzpiKYvFv6MM7GWtSo7-tP3S7b3kDSqIqQTKTujCSy2bUSZ0_7OUDeZja7QRSdjU-sEcmlqR8QpZC27RdprR6Oj9VfPa8N762_eNug6umqtPj6nE/s320/Screenshot%202025-03-20%20100450.png" width="320" /></a></div>
ceklis semuanya yang ada digambar, coba di perbesar list dengan klik tambah (+) ceklis semua
<p>3. Cek dengan <b>sc.exe qc lanmanworkstation</b> jika :</p><p>
</p><pre><code id="code-block">
SERVICE_NAME: lanmanworkstation
        TYPE               : 20  WIN32_SHARE_PROCESS
        START_TYPE         : 2   AUTO_START
        ERROR_CONTROL      : 1   NORMAL
        BINARY_PATH_NAME   : C:\Windows\System32\svchost.exe -k NetworkService -p
        LOAD_ORDER_GROUP   : NetworkProvider
        TAG                : 0
        DISPLAY_NAME       : Workstation
        DEPENDENCIES       : Bowser
                           : MRxSmb20
                           : NSI
        SERVICE_START_NAME : NT AUTHORITY\NetworkService
</code>
</pre>
berarti file sharing bisa berfungsi karena tertulis <b>2. AUTOSTART, ERROR_CONTROL: 1. NORMAL</b> biasanya <b>DISABLED ATAU 0. N/A</b>
<p>4. jika masih Error coba buka service.msc di <b>Win + R</b>,jika lewat start menu ketik <b>Service</b>:</p><p>
     </p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjvNrx5ZEJrIHhZGmexbobyhA_ARfrYaTnSY3SggcTAJIMKOpFhUjcPC5I3sKu-gUDQv4hLs7MZinuIPfQH2Xk6g1wsWZUpkcFTFz6mnxXIgJiqYyVqxxREVv9e9oBhORuipk6A1uXkhic5V9JC05y7Ip780tXm80Yun7O97OFL4d7QZzxYRhPZE-JqrqU/s643/Screenshot%202025-03-20%20102121.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="234" data-original-width="643" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjvNrx5ZEJrIHhZGmexbobyhA_ARfrYaTnSY3SggcTAJIMKOpFhUjcPC5I3sKu-gUDQv4hLs7MZinuIPfQH2Xk6g1wsWZUpkcFTFz6mnxXIgJiqYyVqxxREVv9e9oBhORuipk6A1uXkhic5V9JC05y7Ip780tXm80Yun7O97OFL4d7QZzxYRhPZE-JqrqU/s320/Screenshot%202025-03-20%20102121.png" width="320" /></a></div>
     <p>Workstation (lanmanworkstation) harus Running dan Startup: <b>Automatic</b></p><p>
     </p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh1YlFDgHTkwQi3yT4BtWbVvroRnNXTV7ZFeBppy9LIJ1Aj8w0oVJzvVz9kNokHLCuyFCdcJm5wazCzXFFWOmCXTmrG3iUs4KYW6C4xxRa6C1qdIQpJKHmEP7mgg6vTRrfF3zW7LIXJvGa_4115FutfBG1Dwx2LggFG71Z0TS5GgZCruaFBCfm6eR1Rnxc/s420/Screenshot%202025-03-20%20102246.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="47" data-original-width="420" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEh1YlFDgHTkwQi3yT4BtWbVvroRnNXTV7ZFeBppy9LIJ1Aj8w0oVJzvVz9kNokHLCuyFCdcJm5wazCzXFFWOmCXTmrG3iUs4KYW6C4xxRa6C1qdIQpJKHmEP7mgg6vTRrfF3zW7LIXJvGa_4115FutfBG1Dwx2LggFG71Z0TS5GgZCruaFBCfm6eR1Rnxc/s320/Screenshot%202025-03-20%20102246.png" width="320" /></a></div>
     <p>TCP/IP NetBIOS Helper (lmhosts) harus Running dan Startup: <b>Automatic atau Manual</b></p><p>
     </p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgEH0ReQu4YKT-8idfAz-XHN4HFbpBrN_V0BeaojVDJNmomko1kI4wJ1cNO2KOCWugF4sp5QYLslKNx91bHynx1y4V8-3LU2MokR2nB2_X4tnNX7fEqheH54C8dKgKy5uVLs32zgjUcqUJC0OZ2cpAxwH5-SivCecKnuxajiNzs0MdoKVeisNLucO49-U0/s632/Screenshot%202025-03-20%20102504.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="219" data-original-width="632" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgEH0ReQu4YKT-8idfAz-XHN4HFbpBrN_V0BeaojVDJNmomko1kI4wJ1cNO2KOCWugF4sp5QYLslKNx91bHynx1y4V8-3LU2MokR2nB2_X4tnNX7fEqheH54C8dKgKy5uVLs32zgjUcqUJC0OZ2cpAxwH5-SivCecKnuxajiNzs0MdoKVeisNLucO49-U0/s320/Screenshot%202025-03-20%20102504.png" width="320" /></a></div>
     <p>Server (lanmanserver) harus Running dan Startup : <b>Automatic</b>
       </p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhfhpVXDP6HJ-ZR954EYQ4Oe6OqDRVFd5hrdrpN6y-MH1Xq6Urdk_Qt-3uJ3sD3kI5JhXgYVBp6dVfOHeWJXGyNeDYzw4yHV78qCX__Qsfql-PRNP58nDlzLKLpjizR5ePIipBQi_voK04-7DaaDGkIg2HqIdlSj-tqClBFusvEfLucv_afdf6o_hbthdk/s426/Screenshot%202025-03-20%20102748.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="56" data-original-width="426" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhfhpVXDP6HJ-ZR954EYQ4Oe6OqDRVFd5hrdrpN6y-MH1Xq6Urdk_Qt-3uJ3sD3kI5JhXgYVBp6dVfOHeWJXGyNeDYzw4yHV78qCX__Qsfql-PRNP58nDlzLKLpjizR5ePIipBQi_voK04-7DaaDGkIg2HqIdlSj-tqClBFusvEfLucv_afdf6o_hbthdk/s320/Screenshot%202025-03-20%20102748.png" width="320" /></a></div>
     <p>Function Discovery Provider Host (fdPHost) dan Function Discovery Resource Publication <b>(FDResPub)</b> harus Running dan Startup :<b> Automatic atau Manual Trigger</b></p><p>
     </p><p>Terakhir DNS Client (Dnscache) harus Running dan Startup : <b>Automatic</b></p><p>
</p><p>5. Jika masih Error? cek apakah pc penerima dan pengirim file smb nya versi 1 atau 2, jika pc disekeliling Network Discovery SMBv.2 semua, tapi pc kamu yang search Nteowrk Discovery SMBv1 yang ga bakal bisa, kamu harus upgrade ke v2 juga, kecuali SMBv2 bisa kedeteksi pc yang menggunakan smbv1 tanpa perlu enable smbv1 ( ini jika hanya pakai protokol SMB) cara diatas sudah bisa jika pakai ftp,webDAV</p><p>
Caranya cek smb kalian versi berapa di<b> control panel &gt; Programs &gt; Turn Windows Feature on or off</b> &gt; liat smb versi berapa seperti gambar diatas (point : "Pastikan fitur pendukung File Sharing (FTP,SMB/cifs,Netbios) aktif di windows mu)", jika versi 1 coba jalankan PowerShell :<b> Get-SmbClientConfiguration</b>
</p><p>Jika keluar ini :</p><p>
     </p><pre><code id="code-block">
ConnectionCountPerRssNetworkInterface : 4
DirectoryCacheEntriesMax              : 16
DirectoryCacheEntrySizeMax            : 65536
DirectoryCacheLifetime                : 10
DormantFileLimit                      : 1023
EnableBandwidthThrottling             : True
EnableByteRangeLockingOnReadOnlyFiles : True
EnableInsecureGuestLogons             : True
EnableLargeMtu                        : True
EnableLoadBalanceScaleOut             : True
EnableMultiChannel                    : True
EnableSecuritySignature               : True
ExtendedSessionTimeout                : 1000
FileInfoCacheEntriesMax               : 64
FileInfoCacheLifetime                 : 10
FileNotFoundCacheEntriesMax           : 128
FileNotFoundCacheLifetime             : 5
KeepConn                              : 600
MaxCmds                               : 50
MaximumConnectionCountPerServer       : 32
OplocksDisabled                       : False
RequireSecuritySignature              : False
SessionTimeout                        : 60
UseOpportunisticLocking               : True
WindowSizeThreshold                   : 8
</code>
</pre>
<p>SMB V2 tidak aktif, sekali lagi SMBv2 tidak aktif maka kamu gak bisa terhubung ke sharing file pc lain , harus aktifkan SMBv2 dengan ketik powershell: <b>Set-SmbClientConfiguration -EnableSMB2Protocol $true</b>, karena output shell yang keluar tidak ada baris EnableSMB2Protocol = $True atau $false, dimungkinkan windows kurang update</p><p>
</p><p>maka itu pastikan PC disekitar kamu harus aktifkan SMBv1 supaya bisa berkomunikasi file sama kamu, caranya di gambar (point : "Pastikan fitur pendukung File Sharing (FTP,SMB/cifs,Netbios) aktif di windows mu), jika di Windows feature hanya SMBv2 maka aktifkan dengan ketik Powershell : <b>Enable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol -NoRestart</b></p><p>
</p><p>5. Jika juga masih Error coba Klik kanan <b>"This PC"</b> &gt; Map Network Drive , Di kolom "Folder", masukkan:</p><p>
</p><pre><code id="code-block">
\\192.168.x.x\NamaPC atau Nama Hostname PC
</code>
</pre>
<p>Centang Reconnect at sign-in, lalu klik Finish</p><p>
</p><p>6. Jika keluar : </p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiDyGX2KaEl2uzDn8d7NGOeP4BGG0xqGu4mkpZlhP5KDGpbWl8y36BUjtmJi7rl5ul0kemV5JZSAh8opPWQb4iYWVoya_r0kpw-3-ACy7YJ9YEQFjGnCvxeqFNJzV3cKMa2h8hiK-dIaAoirSWbwD6TrXTiY-vMyyQG0OxrMZK2GP725S4DQokpwmtqWX4/s381/Screenshot%202025-03-20%20115557.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="285" data-original-width="381" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiDyGX2KaEl2uzDn8d7NGOeP4BGG0xqGu4mkpZlhP5KDGpbWl8y36BUjtmJi7rl5ul0kemV5JZSAh8opPWQb4iYWVoya_r0kpw-3-ACy7YJ9YEQFjGnCvxeqFNJzV3cKMa2h8hiK-dIaAoirSWbwD6TrXTiY-vMyyQG0OxrMZK2GP725S4DQokpwmtqWX4/s320/Screenshot%202025-03-20%20115557.png" width="320" /></a></div><p>
Buka Registry Editor <b>(Win + R → ketik regedit → Enter)</b>. Lalu Navigasikan ke:
</p><pre><code id="code-block">
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters
</code>
</pre>
<p>Cari DWORD <b>"AllowInsecureGuestAuth"</b></p><p>
Jika tidak ada, buat DWORD baru dengan nama AllowInsecureGuestAuth, Ubah nilainya menjadi 1
  </p><p>Restart Windows dan coba akses kembali.</p>
<p>Jika berhasil berarti bisa ditarik kesimpulan :
</p><hr />
<p><b>KESIMPULAN</b></p><p>
</p><p>1. Permasalahan dari Kompatibilitas Versi SMB</p><p>
</p><p>2. Windows memblokir akses Guest (tanpa autentikasi) ke shared folder. Ini sering terjadi karena kebijakan keamanan Windows.</p><p>
</p><p>3. Router tidak mendukung apalagi pakai router ISP, kadang configurasi Firewall,Filter Port,Binding di user root admin ISP, harus izin ke ISP</p><p>
</p><p>4. Banyak layanan filesharing, juga seperti <b>Netbios</b> yang penting, disabled di Services</p><p>
</p><p>5. Windows kurang update ,solusi pakai router sendiri, pasang Server Samba versi yang kompatibel ke semua pc di jaringan sekitar, kalau ga bisa ya terpaksa update</p><p>
Kalau sudah berhasil tapi tidak keluar folder atau file ,atau ada dialog box
 </p><div class="separator" style="clear: both;"><a href="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhX53Hw_Gau7HFXFG7rtMmo4liiHuFHjmc6QQpJPdb2nuy6cDK7If5uCco1vtM42Q5eWEQJDBLNeNnEtPc_Y6qStV2gMG0c9MRUqDq9nRG-l5x1_xgzPiVQzJiKZ4JqOs88ELGymbWgEuSHRyHFvA4OSoAuUkPemL0RvlEJ0EqXuvRV38XHnNBcITDFngA/s1280/gbr.png" style="display: block; padding: 1em 0px; text-align: center;"><img alt="" border="0" data-original-height="720" data-original-width="1280" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhX53Hw_Gau7HFXFG7rtMmo4liiHuFHjmc6QQpJPdb2nuy6cDK7If5uCco1vtM42Q5eWEQJDBLNeNnEtPc_Y6qStV2gMG0c9MRUqDq9nRG-l5x1_xgzPiVQzJiKZ4JqOs88ELGymbWgEuSHRyHFvA4OSoAuUkPemL0RvlEJ0EqXuvRV38XHnNBcITDFngA/s320/gbr.png" width="320" /></a></div>
     <b>"Windows cannot access \NAMAPC\XXX\XXXX\XXX"
"You do not have permission to access this file. Contact your network administrator to request access."</b>, itu permasalahan di hak izin dan shared folder configuration di properties folder, nanti lah bahas lagi, kepanjangan.... Thanksss..

<p>SEMOGA ARTIKEL INI BERMANFAAT<p/>  
#FYI
