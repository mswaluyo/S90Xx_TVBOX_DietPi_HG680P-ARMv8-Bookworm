# S90Xx_TVBOX_DietPi_H680P-ARMv8-Bookworm
DietPi for STB H680P-S90Xx
========================================
# 🚀 Pamsimas Selur - Server STB HG680P (DietPi Edition)

Repositoy ini berisi catatan konfigurasi dan file sakti untuk mengubah STB HG680P (Amlogic S905X) menjadi server web Pamsimas yang super enteng menggunakan **DietPi**.

---

## 🛠️ Spesifikasi Hardware
* **Device:** ZTE ZXV10 HG680P
* **Chipset:** Amlogic S905X
* **Storage Utama:** eMMC 8GB (Internal)
* **Storage Data:** SSD 110GB (External via USB)
* **OS:** DietPi (Based on Debian Bookworm)

---

## 📂 Struktur File Boot (Penting!)
Agar STB bisa booting, pastikan file-file berikut ada di partisi FAT32 (BOOT) pada SD Card/eMMC:

### 1. `dietpiEnv.txt`
File ini adalah kemudi utama untuk mencari "Kunci" (DTB).
```text
rootdev=UUID=(sesuai-id-partisi)
rootfstype=ext4
fdtfile=/dtb/amlogic/meson-gxl-s905x-p212.dtb
consoleargs=console=ttyAML0,115200 console=tty1
extraargs=fsck.repair=yes net.ifnames=0 dwc_otg.lpm_enable=0 rootwait
