## Cara Mengkompilasi sm64ex coop android

ini adalah tutorial berbahasa indonesia dari [sm64ex-coop-32-64-bits](https://github.com/XxCmbRxX/sm64ex-coop-32-64-Bits).

### Persyaratan

* Termux
* Super Mario 64 (USA) `.z64`
* File Manager
* Ruang Penyimpanan 2GB
__________________________________________________

**Termux**

Diperlukan aplikasi Termux, sebuah aplikasi Terminal Linux untuk Android.

Bisa didapatkan di internet, namun disarankan menggunakn [Termux dari F-droid](https://f-droid.org/repo/com.termux_118.apk), atau [Termux Monet](https://github.com/HardcodedCat/termux-monet/releases/latest).

> [!NOTE]
> Aplikasi Termux dari PlayStore sudah kadaluarsa dan tidak berfungsi, jadi disarankan menggunakan Termux dari link diatas.

>[!TIP]
> Disarankan menggunakan Termux dari F-droid karena dibutuhkan Repository yang berbeda.
__________________________________________________

**ROM**

Yang paling penting adalah sebuah file klon daei game `Super Mario 64(USA).z64` untuk membuatnya dapat dimainkan di android. ingat untuk mengunduh game berformat `.z64`.

Sayangnya saya tidak dapat membagikan file tersebut karna suatu alasan. Jadi silahkan cari dari internet.

>[!important]
> Jika kau mengunduh game berformat n64 dan mengubahnya menjadi z64. Maka saat proses kompilasi akan terjadi eror.
__________________________________________________

**File Manager**

Ada banyak sekali File Manager yang dapat digunakan, seperti [**MT Manager**](https://d-11.winudf.com/b/APK/YmluLm10LnBsdXNfMjQwMzA2NjNfNjFhNGM0NWI?_fn=TVQgTWFuYWdlcl8yLjE1LjBfQXBrcHVyZS5hcGs&_p=YmluLm10LnBsdXM%3D&download_id=otr_1868209534382651&is_hot=true&k=d185795f3a53b5bb03a6d18c7120d7ad660b1857), [**My Files**](https://play.google.com/store/apps/details?id=com.myfiles.filefolder.filemanager), [**Es File Explorer**](https://dw.uptodown.com/dwn/FfozR53P70_m9L4wu2-vW6stssHC6mph3bIPvMoUav-jJ4btU7ZwB-PlXwZeSiYCJB70pcKdAUg403Nh5cWCj5pOh9-UIc5V9_t2_LrmT56RccKWpNR0s5mm-IGCnHgW/NtNwqW-9qh0zueEKw9jQSZoVSI9QhpMC0U88XwgVxA0h8V8cdPJAbeDgRpZnKNdpqG9qdE-CBsvcnCsVFllNIWOOd-_DhM7CNRaVDKYJS7K-EfuTVimV-d0PnSoikI5_/H880-v7XrEC_MPiJ6a9tlul-6cL5NPtwqMgT9XGcwLCfNDWiZnZvP355YWL7swFtXOxZnIlmKPqE4y2APHUfnDGLv1b4fQgepFGHD0rO4pE=/), [**Zarchiver**](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver).

Tapi saya sendiri memilih [**Zarchiver**](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver) karena alasan kenyamanan.
__________________________________________________

**Hal Lain**

Sebelum melakukan Kompilasi ada beberapa hal yg harus dilakukan dan diperhatikan !

Untuk file game `Super Mario 64(USA).z64` ubah menjadi `baserom.us.z64`, lalu taruh di file direktori perangkat `/storage/emulated/0/`.

![Gambar](https://i.imgur.com/AXjMMBB.png)

>[!TIP]
> Agar saat proses pengkompilasi tidak mengalami masalah, **jangan keluar dari aplikasi Termux**, kemudian **jangan menutup ataupun mengunci layar pernangkat**.
__________________________________________________

## Persiapan
 
jika syarat diatas sudah terpenuhi, selanjutnya untuk persiapan

**PERINTAH PERTAMA**

Ketikan atau salin perintah berikut:
```
termux-change-repo
```
lalu klik [Enter].

![Gambar](https://i.imgur.com/mHfxFzl.jpeg)

Maka akan muncul sebuah tampilah pilihan Mirror, pilih `Single mirror | Choose a single mirror to use`.

tekan [OK].

lalu akan muncul tampilan pilihan Repositori, pilih `Mirror by Tsinghua University TUNA Association | mirrors.tuna.tsinghua.edu.cn`.

tekan [OK].

![Gambar](https://i.imgur.com/X5onkWN.jpeg)
__________________________________________________

**PERINTAH KE-DUA**

Ketikan atau salin perintah berikut:
```
yes|pkg update && yes|pkg upgrade
```
lalu klik [Enter].

Perintah ini hanya mengkonfirmasi secara otomatis saat mengupdate dan mengupgrade package termux, tanpa perlu mengkonfirmasi secara manual.
__________________________________________________

**PERINTAH KE-TIGA**

Ketikan atau salin perintah berikut:
```
termux-setup-storage
```
lalu klik [Enter].

Maka akan muncul pesan perizinan agar Termux dapat mengakses File dari perangkat. Yang kamu harus lakukan ialah mengizinkan pesan tersebut.

![Gambar](https://i.imgur.com/RrqKgPD.jpeg)
__________________________________________________

**PERINTAH KE-EMPAT**

Keyikan atau salin perintah berikut:
```
pkg remove libglvnd
```
lalu klik [Enter].

Dengan perintah ini kamu akan menghapus sebuah alat bernama [*`GL Vendor-Neutral Dispatch`*](https://github.com/NVIDIA/libglvnd). kamu bisa mengklik jika ingin informasi lebih lanjut.

> ada beberapa hal dalam alat ini yang menyebabkan kesalahan dan masalah besar saat mengkompilasi, jadi perlu untuk dihapus.

![Gambar](https://i.imgur.com/CFml5QB.jpeg)
__________________________________________________

**PERINTAH KE-LIMA**

Ketikan atau salin perintah berikut:
```
pkg install git wget make python getconf zip apksigner clang binutils libglvnd-dev aapt which
```
lalu klik [Enter].

Dengan perintah ini kamu akan menginstal alat yang diperlukan untuk mengkompilasi game nya dan juga memerlukan cukup ruang penyimpanan sebanyak `1006 MB` atau `1GB` untuk menginstal.

Jika diminta untuk mengkonfirmasi ketik `Y` lalu klik [Enter].

![Gambar](https://i.imgur.com/VcdzPBC.jpeg)
__________________________________________________

**PERINTAH KE-ENAM**

Ketikan atau salin perintah berikut:
```
git clone https://github.com/robertkirkman/sm64ex-coop.git
```
lalu klik [Enter].

Ini akan mengklon repositori OWOKITTY untuk mengkompilasi game agar berjalan di android.

![Gambar](https://i.imgur.com/dWVKja0.jpeg)
__________________________________________________

**PERINTAH KE-TUJUH**

Ketikan atau salin perintah berikut:
```
cp /storage/emulated/0/baserom.us.z64 sm64ex-coop/baserom.us.z64
```
lalu klik [Enter].

ini akan mengklon file game dari file direktori perangkat ke repositori sm64ex coop dengan nama yang sama `baserom.us.z64`.

![Gambar](https://i.imgur.com/y2clxLx.jpeg)
__________________________________________________

**PERINTAH KE-DELAPAN**

Ketikan atau salin perintah berikut
```
cd sm64ex-coop
```
lalu klik [Enter].

ini akan membuka repositori sm64ex coop dari dalam Termux.

![Gambar](https://i.imgur.com/twIOFYj.jpeg)
__________________________________________________

**PERINTAH KE-SEMBILAN**

Ketikan atau salin perintah berikut:
```
git pull
```
lalu klik [Enter].

ini hanya akan memperbarui game dan git yang telah di pasang `jika diperlukan`.

__________________________________________________

**PERINTAH KE-SEPULUH**

Ketikan atau salin perintah berikut:
```
git submodule update --init --recursive
```
lalu klik [Enter].

ini akan mengupdate file CoopNet yang dibutuhkan sm64ex coop untuk tersambung ke server. agar terhindar dari masalah atau eror saat proses kompilasi.
__________________________________________________

## Mengompilasi Game

Setelah persiapan diatas telah terpenuhi saatnya untuk mengompilasi game agar dapat dimainkan di android

Ketikan atau salin perintah berikut:
```
make
```
lalu klik [Enter].

Setelah perintah dijalankan itu akan membutuhkan waktu yg sedikit lama. Jika tidak ada kesalahan atau eror maka proses kompilasi berhasil.

Selanjutnya kita perlu mengklon sm64ex coop yaitu `sm64ex.us.apk`ke file direktori perangkat.

Ketikan atau salin perintah berikut:
```
cp build/us_pc/sm64.us.apk /storage/emulated/0
```
lalu klik [Enter].

Keluar dari Termux dengan Tekan `Ctrl` + `D` untuk logout, atau ketikan perintah `exit` untuk keluar, lalu buka File Manager kalian untuk menginstal Gamenya.

![Gambar](https://i.imgur.com/cP9dt0V.png)
__________________________________________________

## Mengupdate Versi game

Jika suatu hari gamenya mengupdate ke versi terbaru, kita bisa mengupdatenya sendiri.

untuk itu kalian jangan menghapus termux ataupun file didalamnya karena akan berguna untuk mengupdate gamenya

Ketikan atau salin perintah berikut:
```
yes|pkg update && yes|pkg upgrade
```
lalu klik [Enter].

lalu Ketikan atau salin perintah:
```
cd sm64ex-coop
```
lalu klik [Enter].

kemudian hapus kompilasi versi sebelumnya dengan perintah:
```
make distclean
```
lalu klik [Enter].

lalu update file game, git, dan juga file coopnet nya juga dengan perintah:
```
git pull
```
lalu klik [Enter].

kemudian perintah:
```
git submodule update --init --recursive
```
lalu klik [Enter].

lalu kompilasikan gamenya dengan perintah:
```
make
```
lalu klik [Enter].

kini tinggal mengklon gamenya ke dalam file direktori perangkat dengan perintah:
```
cp build/us_pc/sm64.us.apk /storage/emulated/0
```
lalu klik [Enter].

Buka File Manager dan instal gamenya seperti sebelumnya, dan kalian punya gamenya dalam versi terbaru.
__________________________________________________
