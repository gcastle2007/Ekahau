# Если у вас зависает WLAN PI с Mediatek mt7925.

Попробуйте обновить драйвера:
```
sudo wget -O /lib/firmware/mediatek/mt7925/BT_RAM_CODE_MT7925_1_1_hdr.bin https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/plain/mediatek/mt7925/BT_RAM_CODE_MT7925_1_1_hdr.bin
sudo wget -O /lib/firmware/mediatek/mt7925/WIFI_MT7925_PATCH_MCU_1_1_hdr.bin https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/plain/mediatek/mt7925/WIFI_MT7925_PATCH_MCU_1_1_hdr.bin
sudo wget -O /lib/firmware/mediatek/mt7925/WIFI_RAM_CODE_MT7925_1_1.bin https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/plain/mediatek/mt7925/WIFI_RAM_CODE_MT7925_1_1.bin
sudo reboot
```