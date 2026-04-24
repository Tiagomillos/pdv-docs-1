### 📌 Objetivo

Este script serve para **identificar automaticamente a versão do PHP instalada no PDV** e **baixar a versão correta do módulo PHP**, garantindo que o sistema funcione após a atualização.

---

## ⚠️ Importante

> ✅ **Todo o script deve ser executado diretamente no PDV (terminal do servidor PDV).**  
> ❌ Não execute apenas partes do código  
> ❌ Não execute fora do ambiente do PDV

👉 O processo depende do ambiente local (PHP instalado, diretórios e permissões).

---

## ▶️ Execução do Script

### 1. Acesse o terminal do PDV

Conecte-se ao servidor onde o PDV está instalado.

---

### 2. Cole e execute o script completo

#!/bin/bash

DIRETORIO_ALVO="/Zanthus/Zeus/pdvJava/GERAL/SINCRO/WEB/moduloPHPPDV/"
USER_FTP="pdvtec"
PASS_FTP="I37#P84G0qx@"

echo "=== Iniciando Atualização do Módulo PHP PDV (Versão 26086) ==="

if [ ! -d "$DIRETORIO_ALVO" ]; then
    echo "Erro: O diretório $DIRETORIO_ALVO não existe!"
    exit 1
fi

cd "$DIRETORIO_ALVO" || exit 1

PHP_VERSION=$(php -r 'echo PHP_MAJOR_VERSION.".".PHP_MINOR_VERSION;')
echo "Versão do PHP detectada: $PHP_VERSION"

if [[ "$PHP_VERSION" == "5.6" ]]; then
    URL="ftp://ftp.zanthus.com.br:2142/pub/Zeus_Retail/ModuloPDV/moduloPHPPDV_2_14_184_159c_26086_php_5_6.zip"
    ARQUIVO="moduloPHPPDV_2_14_184_159c_26086_php_5_6.zip"

elif [[ "$PHP_VERSION" == "8."* ]]; then
    URL="ftp://ftp.zanthus.com.br:2142/pub/Zeus_Retail/ModuloPDV_8_1/moduloPHPPDV_2_14_184_159c_26086_php_8_1.zip"
    ARQUIVO="moduloPHPPDV_2_14_184_159c_26086_php_8_1.zip"

else
    echo "Erro: Versão do PHP ($PHP_VERSION) incompatível."
    exit 1
fi

echo "Baixando $ARQUIVO..."
wget --user "$USER_FTP" --password="$PASS_FTP" -c "$URL"

if [ $? -ne 0 ]; then
    echo "Erro no download via FTP."
    exit 1
fi

echo "Extraindo arquivos..."
unzip -o "$ARQUIVO"

echo "=== Atualização concluída com sucesso ==="

## ✅ Resultado Esperado

- O script identifica automaticamente o ambiente do PDV
- Baixa o módulo correto
- Atualiza os arquivos automaticamente

---

## 💡 Dica

Se quiser deixar mais seguro, você pode rodar antes:

cp -r moduloPHPPDV moduloPHPPDV_backup

👉 Isso cria um backup antes da atualização.