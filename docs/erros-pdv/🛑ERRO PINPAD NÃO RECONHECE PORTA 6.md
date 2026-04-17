## 🧾 Erro na Porta 6 – Função 7250

Quando executamos a **função 7250 no PDV** e aparece **erro na porta 6**, siga o procedimento abaixo.

---

## 🛑 1. Encerrar a aplicação

Primeiro, finalize os processos do PDV.

pkill -9 pdvJava2  
pkill -9 jav  
pkill -9 lnx  
pkill -9 chro

---

## 📂 2. Acessar o diretório da aplicação

Entre na pasta do **pdvJava**:

cd /Zanthus/Zeus/pdvJava

---

## ⚙️ 3. Editar o arquivo de configuração

Abra o arquivo **ECF9A.CFG**:

nano ECF9A.CFG

Verifique a linha conforme a referência abaixo:

![[Pasted image 20260313093729.png]]

⚠️ **Importante:**  
Se nesta linha estiver configurado **6**, o sistema **não irá reconhecer**.

Altere para **qualquer outro número diferente de 6**.