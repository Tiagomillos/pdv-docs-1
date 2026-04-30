🖥️ Habilitar Balança USB (Elgin)

---

📌 Objetivo

Configurar o reconhecimento automático da balança USB no PDV por meio de regras do udev, garantindo que o dispositivo seja identificado corretamente pelo sistema.

---

📥 1. Transferir o arquivo de regra

Utilize o WinSCP (ou outro cliente SFTP) para enviar o arquivo:

Arquivo: 99-elgin.rules

Destino: /home/user

---

💻 2. Acessar o terminal

Abra o terminal no PDV para executar os comandos necessários.

---

📁 3. Acessar o diretório de regras do udev


cd /etc/udev/rules.d

📖 Este diretório contém as regras responsáveis pelo gerenciamento de dispositivos conectados ao sistema (como USB).

---

📁 4. (Opcional) Criar pasta adicional

mkdir rules


⚠️ Atenção:
Essa etapa normalmente não é necessária. O diretório padrão já é rules.d. Utilize apenas se houver alguma necessidade específica no ambiente.

---

📂 5. Acessar o diretório onde o arquivo foi enviado

cd /home/user


---


🔐 6. Ajustar permissões do arquivo

chmod 777 99-elgin.rules

📖 Isso garante acesso completo ao arquivo.


💡 Recomendação:
Para ambientes mais seguros, utilize permissões mais restritas:

chmod 644 99-elgin.rules


---


🚚 7. Mover o arquivo para o diretório do udev

mv 99-elgin.rules /etc/udev/rules.d/

📖 Após essa etapa, o sistema passará a considerar a nova regra ao gerenciar dispositivos USB.


---


🔄 8. Reiniciar o sistema

reboot

📖 A reinicialização garante que as novas regras do udev sejam carregadas corretamente.

---


✅ Resultado esperado

Após a reinicialização, a balança USB deve ser reconhecida automaticamente pelo sistema, sem necessidade de configuração manual adicional.