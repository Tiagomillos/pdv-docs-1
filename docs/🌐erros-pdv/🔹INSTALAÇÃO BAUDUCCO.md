## INSTALAÇÃO BAUDUCCO – GUIA SIMPLES E EXPLICADO

Este passo a passo serve para preparar um **PDV Ubuntu 22.04** do zero, deixando VPN, arquivos e módulos funcionando corretamente.

---

### 1️⃣ PASSO – INSTALAR VPN CISCO

A VPN é necessária para acessar a rede da Bauducco.

#### 1. Permitir comunicação externa

```bash
sudo chmod 766 /etc/resolv.conf
```

#### 2. Limpar repositórios antigos da Zanthus

```bash
sudo mkdir -p /etc/apt/repolist.old
sudo mv /etc/apt/sources.list.d/* /etc/apt/repolist.old
```

#### 3. Restaurar repositórios padrão do Ubuntu 22.04

```bash
sudo mv /etc/apt/sources.list /etc/apt/sources.list.old

echo -e 'deb http://archive.ubuntu.com/ubuntu jammy main restricted

deb http://archive.ubuntu.com/ubuntu jammy universe

deb http://archive.ubuntu.com/ubuntu jammy-updates main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu jammy-security main restricted universe multiverse' | sudo tee /etc/apt/sources.list
```

#### 4. Atualizar sistema

```bash
sudo apt update
```

#### 5. Baixar e instalar o Cisco Secure Client

```bash
sudo curl -o /tmp/cisco.deb "https://www.dropbox.com/scl/fi/qcwvhmrido0u36d98n290/cisco-secure-client-vpn_5.1.6.103_amd64.deb?dl=0"

sudo apt install -y /tmp/cisco.deb
```

#### 6. Adicionar profiles da Bauducco

```bash
cd /tmp
curl -o profiles.tar.gz "https://www.dropbox.com/scl/fi/wxibpukki342yrswy45nw/cisco-secure-client-profiles-5.1.3.62-2.src.tar.gz?dl=0"

tar -zxf profiles.tar.gz
sudo mkdir -p /opt/cisco/secureclient/vpn/profile
sudo cp cisco-secure-client-profiles/*.xml /opt/cisco/secureclient/vpn/profile
```

#### 7. Ativar e validar VPN

```bash
sudo systemctl enable --now vpnagentd
sudo systemctl status vpnagentd
```

---

### 2️⃣ PASSO – COPIAR CONFIGURAÇÕES DE OUTRO PDV

Copiar arquivos essenciais (ECF e configurações gerais):

```bash
scp -r PDVTEC@192.168.158.51:/Zanthus/Zeus/pdvJava/ECF9*.CFG .
```

> ⚠️ Copie somente os arquivos necessários (evite duplicados).

---

### 3️⃣ PASSO – COPIAR PDVGUI

```bash
scp -r PDVTEC@192.168.158.52:/Zanthus/Zeus/pdvJava/okgui.tar.gz .

tar -zxvf okgui.tar.gz
```

---

### 4️⃣ PASSO – ATUALIZAR MÓDULO PHP

1. Envie o arquivo `moduloPHP_atualizado.zip` via **WinSCP** para `/home/user`
    
2. No terminal:
    

```bash
cd /home/user
cp -rfv moduloPHP_atualizado.zip /Zanthus/Zeus/pdvJava/GERAL/Sincro/Web/ModuloPHP/

cd /Zanthus/Zeus/pdvJava/GERAL/Sincro/Web/ModuloPHP
unzip -o moduloPHP_atualizado.zip
```

---

### 5️⃣ PASSO – INSTALAR CLISITEF 112

1. Envie o ZIP do CliSiTef via **WinSCP** para `/home/user`
    
2. No terminal:
    

```bash
cd /home/user
unzip -o CLISiTefLinux64.zip
cd clisitef-7.0.117.112

chmod +x *.so
cp -r *.so /Zanthus/Zeus/lib_u22/
cp -r *.so /Zanthus/Zeus/pdvJava


```

---

✅ **PRONTO**  
VPN configurada, arquivos copiados, módulos atualizados e CliSiTef funcionando.

Se algo não subir, reinicie o PDV e valide novamente.