# 🔐 Cisco Secure Client no Ubuntu 22.04

Instalação do **Cisco Secure Client 5.1.6.103** no Ubuntu 22.04  
Fonte base: [https://github.com/elppans/doc-zretail/blob/main/ubuntu22_zpac.sh](https://github.com/elppans/doc-zretail/blob/main/ubuntu22_zpac.sh)

---

## ⚙️ Permissões iniciais

sudo chmod 766 /etc/resolv.conf

---

## 🧹 Remover repositórios de terceiros

sudo mkdir -p /etc/apt/repolist.old  
sudo mv /etc/apt/sources.list.d/* /etc/apt/repolist.old

---

## 📦 Reconfigurar repositórios padrão (Ubuntu 22.04)

sudo mv /etc/apt/sources.list /etc/apt/sources.list.old

echo -e 'deb http://archive.ubuntu.com/ubuntu jammy main restricted  
deb http://archive.ubuntu.com/ubuntu jammy universe  
deb http://archive.ubuntu.com/ubuntu jammy-backports main restricted universe multiverse  
deb http://archive.canonical.com/ubuntu jammy partner  
deb http://archive.ubuntu.com/ubuntu jammy-security main restricted  
deb http://archive.ubuntu.com/ubuntu jammy-security universe  
deb http://archive.ubuntu.com/ubuntu jammy-security multiverse  
deb http://archive.ubuntu.com/ubuntu jammy-updates main restricted  
deb http://archive.ubuntu.com/ubuntu jammy-updates universe  
deb http://archive.ubuntu.com/ubuntu jammy-updates multiverse  
' | sudo tee /etc/apt/sources.list &>>/dev/null

---

## 🔄 Atualizar repositórios

sudo apt update

---

## 📥 Instalar Cisco Secure Client

sudo curl -JLk -o /var/cache/apt/archives/cisco-secure-client-vpn_5.1.6.103_amd64.deb "https://www.dropbox.com/scl/fi/qcwvhmrido0u36d98n290/cisco-secure-client-vpn_5.1.6.103_amd64.deb?rlkey=xpzm362jmbw0baoovg7q81fm6&st=rerkivu2&dl=0"

sudo apt -y install /var/cache/apt/archives/cisco-secure-client-vpn_5.1.6.103_amd64.deb

---

## 📁 Adicionar profiles (VPN)

cd /tmp

curl -JLk -o /tmp/cisco-secure-client-profiles.src.tar.gz "https://www.dropbox.com/scl/fi/wxibpukki342yrswy45nw/cisco-secure-client-profiles-5.1.3.62-2.src.tar.gz?rlkey=p17hygahe71pwip2cncdb0evt&st=vbrch1xv&dl=0"

tar -zxf /tmp/cisco-secure-client-profiles.src.tar.gz -C /tmp

sudo mkdir -p /opt/cisco/secureclient/vpn/profile

sudo cp -rf /tmp/cisco-secure-client-profiles/*.xml /opt/cisco/secureclient/vpn/profile

---

## 🚀 Ativar serviço

sudo systemctl enable --now vpnagentd

---

## 🔍 Verificar status

sudo systemctl status vpnagentd

---

## 🖥️ Atalho na área de trabalho (root)

sudo cp -av /usr/share/applications/com.cisco.secureclient.gui.desktop /root/Desktop