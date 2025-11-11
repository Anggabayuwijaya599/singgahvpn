# CARA INSTALL SCRIPT FORCE SINGGAH VPN

## 1. DAFTARKAN IP VPS DI FILE IJIN LINK DI BAWAH INI :

https://github.com/Anggabayuwijaya599/singgahvpn/blob/main/izin






## 2. COPY PASTE SCRIPT LINK UNTUK INSTALL BERIKUT INI KE VPS :


```
sysctl -w net.ipv6.conf.all.disable_ipv6=1 && sysctl -w net.ipv6.conf.default.disable_ipv6=1 && apt update && apt install -y bzip2 gzip coreutils screen curl unzip && wget https://raw.githubusercontent.com/Anggabayuwijaya599/installsinggah/refs/heads/main/vpn && chmod +x vpn && sed -i -e 's/\r$//' vpn && screen -S setup ./vpn
```



## 3. MASUKAN SUBDOMAIN.DOMAIN KE DALAM VPS YANG SEDANG DI INSTALL KETIKA DI MINTA MASUKAN DOMAIN


## 4. SETELAH SELESAI INSTALL OTOMATIS AKAN REBOOT VPS ATAU JIKA DI MINTA REBOT TEKAN YES ATAU ENTER



========================================================================================================


# UPDATE FORCE

```
rm update.sh
wget https://raw.githubusercontent.com/Anggabayuwijaya599/singgahvpn/refs/heads/main/update.sh && chmod +x update.sh && ./update.sh

```
## DOWN GRADE  XRAY VERSI 2.1


~~~
sudo systemctl stop xray
sudo systemctl stop xray-core
sudo mv /usr/local/bin/xray /usr/local/bin/xray.bak.v25.10
wget https://github.com/XTLS/Xray-core/releases/download/v25.1.30/Xray-linux-64.zip

# 4. Unzip
unzip Xray-linux-64.zip
# misalnya akan menghasilkan file bernama “xray”

# 5. Pasang binary baru
sudo mv xray /usr/local/bin/xray
sudo chmod +x /usr/local/bin/xray
# Pastikan owner/root sesuai: sudo chown root:root /usr/local/bin/xray

# 6. Verifikasi versi
/usr/local/bin/xray version
# Pastikan tertulis v25.1.30

# 7. Mulai kembali service
sudo systemctl start xray
sudo systemctl enable xray

# 8. Cek log & status
sudo systemctl status xray
sudo journalctl -u xray -f
