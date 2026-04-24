## 🔐 Atualização do CliSiTef no PDV

### 📌 Procedimento

• **Verificar** a versão atual do **CliSiTef** instalada no PDV  
• **Matar a aplicação** após a verificação da versão  
• **Copiar** a versão mais atual da sua máquina para a máquina do cliente

- Versão utilizada: **112**  
    • No PDV do cliente, **descompactar (unzip)** o arquivo do **CliSiTef**  
    • Copiar **todos os arquivos `.so`** para os diretórios corretos  
    • **Subir novamente a aplicação** ao finalizar o processo
    

---

### 🖥️ Comandos de Cópia

`cp -rfv *.so /Zanthus/Zeus/pdvJava`

`cp -rfv *.so /Zanthus/Zeus/lib_u64`

> 💡 Em ambientes **Ubuntu 22***, garantir que as bibliotecas `.so` estejam também no diretório correto.

---

### ✅ Checklist Final

• Versão do CliSiTef validada  
• Aplicação encerrada antes da cópia  
• Arquivos `.so` copiados corretamente  
• Aplicação iniciada novamente  
• Testar comunicação do **CliSiTef**