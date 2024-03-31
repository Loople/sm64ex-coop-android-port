## Cara Mengkompilasi sm64ex coop android

ini adalah tutorial berbahasa indonesia dari repository [sm64ex-coop-32-64-bits XxCmbRxX](https://github.com/XxCmbRxX/sm64ex-coop-32-64-Bits).

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
> Jika kau mengunduh game berformat n64 dan mengubahnya menjadi z64. Maka saat proses kompilasi akan terjadi error.
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

## Pengkompilasi
 
Baiklah jika syarat diatas sudah terpenuhi maka saatnya proses pengkompilasi

**PERINTAH PERTAMA**

Ketikan atau salin perintah berikut:
```bash
termux-change-repo
```
lalu klik [Enter].

![Gambar](https://i.imgur.com/mHfxFzl.jpeg)

Maka akan muncul sebuah tampilah pilihan Mirror, pilih `Single mirror | Choose a single mirror to use`.

tekan [OK].

lalu akan muncul tampilan pilihan Repository, pilih `Mirror by Tsinghua University TUNA Association | mirrors.tuna.tsinghua.edu.cn`.

tekan [OK].

![Gambar](https://i.imgur.com/X5onkWN.jpeg)
__________________________________________________

**PERINTAH KE-DUA**

Ketikan atau salin perintah berikut:
```bash
yes|pkg update && yes|pkg upgrade
```
lalu klik [Enter].

Perintah ini hanya mengkonfirmasi secara otomatis saat mengupdate dan mengupgrade package termux, tanpa perlu mengkonfirmasi secara manual.
__________________________________________________

**PERINTAH KE-TIGA**

Ketikan atau salin perintah berikut:
```bash
termux-setup-storage
```
lalu klik [Enter].

Maka akan muncul pesan perizinan agar Termux dapat mengakses File dari perangkat. Yang kamu harus lakukan ialah mengizinkan pesan tersebut.

![Gambar](https://i.imgur.com/RrqKgPD.jpeg)
__________________________________________________

**PERINTAH KE-EMPAT**

Keyikan atau salin perintah berikut:
```bash
pkg remove libglvnd
```
lalu klik [Enter].

Dengan perintah ini kamu akan menghapus sebuah alat bernama [*`GL Vendor-Neutral Dispatch`*](https://github.com/NVIDIA/libglvnd). kamu bisa mengklik jika ingin inormasi lebih lanjut.

> ada beberapa hal dalam alat ini yang menyebabkan kesalahan dan masalah besar saat mengkompilasi, jadi perlu untuk dihapus.

![Gambar](https://i.imgur.com/CFml5QB.jpeg)
__________________________________________________

**PERINTAH KE-LIMA**

Ketikan atau salin perintah berikut:
```bash
pkg install git wget make python getconf zip apksigner clang binutils libglvnd-dev aapt which
```
lalu klik [Enter].

Dengan perintah ini kamu akan menginstal alat yang diperlukan untuk mengkompilasi game nya dan juga memerlukan cukup ruang penyimpanan sebanyak `1006 MB` atau `1GB` untuk menginstal.

Jika diminta untuk mengkonfirmasi ketik `Y` lalu klik [Enter].

![Gambar](https://i.imgur.com/VcdzPBC.jpeg)
__________________________________________________


