__## ⚠️ REGRA OBRIGATÓRIA

**SEMPRE PEDIR TLS ANTES DE TUDO**

---

## 🧩 Objetivo

Procedimento correto, limpo e seguro para montar um novo PDV, copiando **somente os arquivos essenciais** do PDV antigo, evitando riscos e arquivos indevidos.

---

## 🔹 1️⃣ Acessar o diretório principal do PDV

No novo PDV (destino), abra o terminal e execute:

```bash
cd /Zanthus/Zeus/pdvJava/
```

---

## 🔹 2️⃣ Estrutura padrão do comando SCP

```bash
scp -r usuario@IP:/caminho/origem/arquivo destino/
```

Exemplo:

```bash
scp -r root@192.168.0.101:/Zanthus/Zeus/pdvJava/ECF9.CFG .
```

📌 O ponto (`.`) indica o diretório atual.

---

## 🔹 3️⃣ Usuário correto por versão do PDV

• **PDV RC antigo** → `root`  
• **PDV 1.4 (64 bits)** → `user`  
• **PDV Ubuntu 22** → `zanthus`

---

## 🔹 4️⃣ Copiar somente os arquivos necessários (um por um)

⚠️ **Nunca usar curingas amplos** (ex: `ECF9*.CFG`), pois pode copiar `ECF9F.CFG` e quebrar configurações.

### 📌 Exemplos corretos

```bash
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/ECF9.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/ECF9A.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/ECFRECEB.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/EMUL.INI .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/ZIGK.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/CLISITEF.INI .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/simula* .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/RCBCNF*.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/RESTG*.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/ZMWS*.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/ZMAN* .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/CARG*.CFG .
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/CLAZ.CFG .
```

---

## 🔹 5️⃣ ATUALIZAR CODFON (OBRIGATÓRIO)

Após copiar o **ZMAN**, atualizar o CODFON:

```bash
tar -xvzf ZMAN_ULTIMA_VERSAO.tar.gz
```

📌 Sempre utilizar a **última versão** do ZMAN.

---

# 🖥️🎨 Configuração da Interface (pdvGUI)

## 🔹 6️⃣ Acessar pasta pdvGUI

```bash
cd /Zanthus/Zeus/pdvJava/pdvGUI/
```

## 🔹 7️⃣ Copiar guiConfigProj do PDV antigo

```bash
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/pdvGUI/guiConfigProj .
```

---

## 🔹 8️⃣ Configuração de resolução

• Acessar o **Painel de Controle** da máquina  
• Alterar a resolução para **800x600**  
• Reiniciar a máquina

---

## 🔹 9️⃣ Atualizar módulo do PDV

Verificar a versão do sistema:

• **Ubuntu 22** → módulo final `8_1`  
• **Ubuntu 16** → módulo final `5_6`

---

## 🔹 🔐 10 Atualizar biblioteca TEF

### 📁 Pasta TEF112

• Verificar se é **32 ou 64 bits**  
• Copiar **somente os 4 arquivos `.so`**

### 📥 Via WinSCP

• Conectar no IP do PDV  
• Colar os arquivos na **home do usuário**

### ⚙️ Comandos no terminal

```bash
chmod 777 *.so
cp *.so /Zanthus/Zeus/pdvJava
```

Ubuntu 16:

```bash
cp *.so /Zanthus/Zeus/lib_u64
```

Ubuntu 22:

```bash
cp *.so /Zanthus/Zeus/lib_u22
```

---

## 🔹 11 Atualizar TODAS as bibliotecas

### 🔸 64 bits

```bash
cd /Zanthus/Zeus/lib_u64
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_u64/* .
```

### 🔸 32 bits

```bash
cd /Zanthus/Zeus/lib_u32
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so/*
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_ubu/*
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_co5/*
```

### 🔸 Ubuntu 22

```bash
cd /Zanthus/Zeus/lib_u22
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_u22/*
```

---



## 🔹 12 VIA MANAGER (OBRIGATÓRIO)

• Acessar o **Manager**  
• Ir em **Cadastro de PDVs**  
• Selecionar a **loja correspondente**  
• Informar a **série do PDV**  
• Conceder **licença** ao PDV

---

## ⚙️ 13 Configuração do PDV (Funções)

### 🔑 Licença

• 6060 – Licença  
• 6066 – Checar licença

### 🔗 Integrações

• 3801 – Ativar CliSiTef  
• 3401 – Comunicação com Manager  
• 12501 – Ativar FISCTX  
• 6201 – Impressora QRCode  
• 3405 – Ativar carga

### 🧩 Periféricos

• 7250 – Config PinPad (tipo 21 / porta 6)  
• 7201 – Salvar PinPad  
• 6450 – Config Scanner (porta 14)  
• 6401 – Salvar Scanner  
• 6750 – Config Balança (porta 5)  
• 6751 – Tempo Balança  
• 6701 – Salvar Balança

### 🧾 Fiscal

• 12310 – COO  
• 58 – Perfil 6 (NFC-e)  
• 12666

### 🔄 Finalização

• 854 – Puxar carga

---

## 🧪 TESTES

• 136 – Scanner  
• 201 / 75 – Impressora  
• 6777 – Balança  
• 3810 – PinPad

---

✅ **Procedimento final organizado, validado e pronto para uso em campo**