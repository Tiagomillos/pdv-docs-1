# 🧾 Atualizar TEF para 112P

## 📌 1º Passo — Verificar sistema do PDV

- Identifique se o PDV está rodando:
    - Ubuntu 22
    - 64 bits
    - 32 bits

> 💡 Isso é importante para garantir compatibilidade da versão do TEF.

---

## 📌 2º Passo — Verificar configuração do CliSiTef

- Acesse o arquivo:

CliSiTef.ini

- Procure pela linha:

#TransacoesHabilitadas=

- Verifique se contém os códigos de PIX:

#TransacoesHabilitadas=7;8

> ⚠️ Se **não tiver `7;8`**, adicione para habilitar PIX.

---

## 🔁 Teste

- Após ajustar o arquivo:
    - Salve as alterações
    - Reinicie o PDV (se necessário)
    - Teste novamente a transação PIX

---

## ✅ Observação

- Caso o PIX ainda não funcione:
    - Revisar novamente o `CliSiTef.ini`
    - Confirmar se a versão do TEF realmente é **112P**
    - Validar comunicação com o servidor TEF