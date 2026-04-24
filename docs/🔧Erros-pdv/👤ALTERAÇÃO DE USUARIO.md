## 👤 Usuários, Senhas e Comandos – PDV

---

## 🔐 Informações

⚠️ **Uso interno / técnico**

• **zanthus** = `upvJ;<]=77o2`  
• **pdvtec** = `ZN6jyI84L`  
• **sustentacao** = `1GW5RrQgv`  
• **VNC** = `0rltVP75z`

---

## 💻 Comandos de criação e configuração de usuários

### 🔹 Criar usuário `pdvtec`

```bash
sudo useradd -m -s /bin/bash pdvtec
sudo usermod -aG sudo pdvtec
sudo passwd pdvtec
```

### 🔹 Criar usuário `sustentacao`

```bash
sudo useradd -m -s /bin/bash sustentacao
sudo usermod -aG sudo sustentacao
sudo passwd sustentacao
```

### 🔹 Alterar senha do usuário `zanthus`

```bash
sudo passwd zanthus
```

---

## 🖥️ Configuração de senha VNC

```bash
x11vnc -storepasswd /root/.vncpasswd
```

---

📌 **Observações**  
• Garantir que os usuários tenham sido criados corretamente antes de liberar acesso  
• Usar com cautela em ambiente de produção  
• Manter este registro restrito ao time técnico