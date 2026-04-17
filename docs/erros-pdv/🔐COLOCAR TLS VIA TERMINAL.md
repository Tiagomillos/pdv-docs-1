# 🔐 Configuração TLS – PDV Java (Terminal Linux)

## ✅ 1️⃣ Entrar na pasta do PDV Java

`cd /Zanthus/Zeus/pdvJava`

---

## ✅ 2️⃣ Criar o arquivo `CONFITLS.INI`

nano CONFITLS.INI

📌 **Copie e cole exatamente o conteúdo abaixo:**

[ConfiguracaoTLS]  
TipoComunicacaoExterna=TLSGWP  
URLTLS=tls-prod.fiservapp.com  
TokenRegistro=7876-8325-4607-2822 (exemplo)

Salvar:

- `CTRL + O` → Enter
    
- `CTRL + X`
    

⚠️ O nome do arquivo deve ser exatamente:

CONFITLS.INI

E deve estar dentro da pasta:

/Zanthus/Zeus/pdvJava

---

## ✅ 3️⃣ Editar o arquivo `CliSiTef.ini`

nano CliSiTef.ini

Localize e deixe as linhas conforme abaixo (comentadas com `#`):

[Geral]  
#TipoComunicacaoExterna=TLSGWP  
  
[SITEF]  
#EnderecoIP=tls-prod.fiservapp.com  
#ConfiguracaoEnderecoIP=tls-prod.fiservapp.com

Salvar:

- `CTRL + O` → Enter
    
- `CTRL + X`