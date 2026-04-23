# ☕ Atualização Java 16 na pdvGUI

## 📌 Objetivo

Atualizar a versão do Java utilizada pela pdvGUI e apontar o link simbólico para o novo pacote.

---

## 1️⃣ Acessar diretório da aplicação

Entrar na pasta da pdvGUI:

```bash
cd /Zanthus/Zeus/pdvJava/pdvGUI
```

---

## 2️⃣ Download do Java 16

Executar:

```bash
wget --user pdvtec --password="I37#P84G0qx@" -c ftp://ftp.zanthus.com.br:2142/pub/Zeus_Frente_de_Loja/_Complementares/Java/java/jpdvgui6_v7_7_15_16.jar
```

---

## 3️⃣ Atualizar link simbólico

Após concluir o download:

```bash
ln -sf jpdvgui6_v7_7_15_16.jar jpdvgui6.jar
```

---

## 🔎 Validação

Confirmar se o link foi atualizado:

```bash
ls -l jpdvgui6.jar
```

Deve apontar para:

```text id="l2ebp1"
jpdvgui6_v7_7_15_16.jar
```

---

## ✅ Resultado esperado

- Java 16 atualizado com sucesso  
- Link simbólico ajustado para a nova versão  
- pdvGUI pronta para testes e operação

---

## ✔️ Conclusão

Procedimento finalizado após validação do ambiente.