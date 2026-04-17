# 🧾 Resolução de Chamado — TEF / TLS

## 📌 Exemplo do cenário

![[Pasted image 20260416154335.png]]

---

## 🔧 Procedimento

### 1️⃣ Verificar configuração TLS

- Copiar o arquivo de outro PDV:

CliSiTef.ini

- Verificar se a TLS está configurada via:

CONFITLS

> Caso não exista o `CONFITLS.INI`, solicitar o arquivo de TLS.

---

### 2️⃣ Acessar diretório do PDV

No terminal:

cd /home/zanthus

---

### 3️⃣ Verificar arquivo de chaves

- Procurar pelo arquivo:

ChavesCliSiTef

- Caso exista:
    - Excluir o arquivo

---

### 4️⃣ Reiniciar e testar

- Subir o PDV novamente
- Executar teste de carga de tabelas:

Função: 3810

---

## ✅ Resultado esperado

- Comunicação TEF funcionando
- Carga de tabelas realizada com sucesso
- PDV operando normalmente

---

## ✔️ Conclusão

Chamado finalizado após validação do funcionamento do TEF.