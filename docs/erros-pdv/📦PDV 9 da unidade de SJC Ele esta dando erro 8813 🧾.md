## 🔄 Atualização do Módulo PHP – PDV

---

## 📤 Envio do módulo via WinSCP

Copiar o módulo da sua máquina para o PDV do cliente.

• Abrir o **WinSCP**  
• Criar nova conexão com o **IP do PDV**  
• Navegar até a pasta onde o módulo ficará no PDV  
• Botão direito → **Upload** do módulo atualizado (`.zip`)

---

## 💻 Validação e cópia do módulo no terminal

### 🔹 Acessar diretório do usuário

```bash
cd /home/user
ls
```

### 🔹 Copiar o módulo para o diretório do sistema

```bash
cp -rfv moduloPHP_atualizado.zip /Zanthus/Zeus/pdvJava/GERAL/Sincro/Web/ModuloPHP/
```

### 🔹 Acessar pasta de destino e validar

```bash
cd /Zanthus/Zeus/pdvJava/GERAL/Sincro/Web/ModuloPHP
ls
```

---

## 📦 Descompactação do módulo

Descompactar o módulo **sobrescrevendo os arquivos existentes**:

```bash
unzip -o moduloPHP_atualizado.zip
```

---

## 🔁 Finalização

• Matar a aplicação do PDV  
• Subir a aplicação novamente  
• Validar o módulo pela **função 1350**  
• Reiniciar a máquina (**reboot**)  
• Testar **carga de tabelas**

---

📌 **Observação**  
Sempre confirmar se o módulo carregado corresponde à versão correta antes de liberar o PDV.