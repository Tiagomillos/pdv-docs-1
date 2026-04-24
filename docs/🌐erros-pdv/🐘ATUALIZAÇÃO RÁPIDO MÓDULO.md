# 🔧 Procedimento Completo — Montagem de Novo PDV + Atualização de Módulo

## ⚠️ REGRA OBRIGATÓRIA

**SEMPRE PEDIR TLS ANTES DE TUDO**

---

## 🧩 Objetivo

Procedimento correto, limpo e seguro para montar um novo PDV copiando apenas arquivos essenciais, com atualização de bibliotecas e módulo integrada no fluxo.

---

## 🔹 1️⃣ Acessar diretório principal

```bash
cd /Zanthus/Zeus/pdvJava/
```

---

## 🔹 2️⃣ Estrutura padrão SCP

```bash
scp -r usuario@IP:/caminho/origem/arquivo destino/
```

Exemplo:

```bash
scp -r root@192.168.0.101:/Zanthus/Zeus/pdvJava/ECF9.CFG .
```

---

## 🔹 3️⃣ Usuário correto por versão

* PDV RC antigo → root
* PDV 1.4 (64 bits) → user
* Ubuntu 22 → zanthus

---

## 🔹 4️⃣ Copiar arquivos necessários

(segue sua lista de SCPs individuais conforme já validada)

* ECF9.CFG
* ECF9A.CFG
* ECFRECEB.CFG
* EMUL.INI
* ZIGK.CFG
* CLISITEF.INI
* simula*
* RCBCNF*.CFG
* RESTG*.CFG
* ZMWS*.CFG
* ZMAN*
* CARG*.CFG
* CLAZ.CFG

⚠️ Nunca usar curingas amplos indevidos.

---

## 🔹 5️⃣ Atualizar CODFON

```bash
tar -xvzf ZMAN_ULTIMA_VERSAO.tar.gz
```

---

# 🖥️ Configuração da Interface (pdvGUI)

## 🔹 6️⃣ Entrar na pasta

```bash
cd /Zanthus/Zeus/pdvJava/pdvGUI/
```

## 🔹 7️⃣ Copiar guiConfigProj

```bash
scp -r user@192.168.0.101:/Zanthus/Zeus/pdvJava/pdvGUI/guiConfigProj .
```

## 🔹 8️⃣ Ajustar resolução

* 800x600
* Reiniciar máquina

---

## 🔹 9️⃣ Atualizar módulo final do PDV

* Ubuntu 22 → módulo 8_1
* Ubuntu 16 → módulo 5_6

---

## 🔹 🔐 10 Atualizar biblioteca TEF

```bash
unzip -o arquivo_tef
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

### 64 bits

```bash
cd /Zanthus/Zeus/lib_u64
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_u64/* .
```

### 32 bits

```bash
cd /Zanthus/Zeus/lib_u32
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so/*
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_ubu/*
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_co5/*
```

### Ubuntu 22

```bash
cd /Zanthus/Zeus/lib_u22
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/so_u22/*
```

---

# 🔄 11.1 Atualização do Módulo PDV (logo após bibliotecas)

> ⚠️ Fazer backup antes.

## 🐘 PHP 5.6

```bash
cd /Zanthus/Zeus/PdvJava/GERAL/SINCRO/WEB/moduloPHPPDV
ls
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Retail/ModuloPDV/moduloPHPPDV_2_14_184_159b_26073_php_5_6.zip .
ls
unzip -o moduloPHPPDV_2_14_184_159b_26073_php_5_6.zip
```

---

## 🐘 PHP 8.1

```bash
cd /Zanthus/Zeus/PdvJava/GERAL/SINCRO/WEB/moduloPHPPDV
ls
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Retail/ModuloPDV_8_1/moduloPHPPDV_2_14_184_159b_26073_php_8_1.zip .
ls
unzip -o moduloPHPPDV_2_14_184_159b_26073_php_8_1.zip
```

---

## 🔹 12 Via Manager

* Cadastro de PDVs
* Loja correta
* Série do PDV
* Conceder licença

---

## ⚙️ 13 Funções

### Licença

* 6060
* 6066

### Integrações

* 3801
* 3401
* 12501
* 6201
* 3405

### Periféricos

* 7250
* 7201
* 6450
* 6401
* 6750
* 6751
* 6701

### Fiscal

* 12310
* 58 Perfil 6
* 12666

### Finalização

* 854 puxar carga

---

## 🧪 Testes

* 136 Scanner
* 201 / 75 Impressora
* 6777 Balança
* 3810 PinPad

---

## ✅ Resultado esperado

* PDV montado
* Bibliotecas atualizadas
* Módulo atualizado
* Licenciamento validado
* Testes finais concluídos
