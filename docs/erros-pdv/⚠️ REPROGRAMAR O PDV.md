# 📦 Backup e Processamento PDV Java

## 📁 Acessar diretório do PDV

cd /Zanthus/Zeus/pdvJava

## 📂 Criar pasta de backup

mkdir bkpnvl

## 📦 Mover arquivos para backup

mv *.NVL bkpnvl  
mv *.TRA bkpnvl  
mv *.XXX bkpnvl

## ⚙️ Executar utilitário (FABRICAR)

./util_R90.xz64 FABRICAR

## ▶️ Executar processamento ECF

Escolher conforme a loja:

./util_R90.xz64 PROG=param.ecf

ou

./util_R90.xz64 PROG=simula.ecf

## 🔁 Finalização

- Executar novamente os comandos no PDV