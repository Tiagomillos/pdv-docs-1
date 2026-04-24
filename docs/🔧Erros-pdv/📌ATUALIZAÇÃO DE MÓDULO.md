## 📌 Passo a Passo – Atualização de Módulos nos PDVs

🔹 1️⃣ Verificação dos PDVs

• Acesse o AnyDesk  
• Identifique os PDVs que precisam ter os módulos atualizados  
• Exemplo: 10 PDVs pendentes de atualização

  

🔹 2️⃣ Acesso ao PDV via PuTTY

• Abra o PuTTY  
• Informe o IP do PDV  
• Conecte-se ao terminal

Credenciais:  
• Usuário: user  
• Senha: zanthus

Após o login, ative o superusuário:

sudo su

  
  

🔹 3️⃣ Envio do Módulo via WinSCP

• Abra o WinSCP  
• Crie uma nova conexão com o IP do PDV  
• Navegue até a pasta onde ficará o módulo  
• Clique com o botão direito → Upload do módulo atualizado

  

🔹 4️⃣ Validação e Cópia do Módulo no Terminal

Acesse o diretório do usuário:

cd /home/user

ls

  

Copie o módulo atualizado para o diretório do sistema:

cp -rfv moduloPHP_atualizado.zip /Zanthus/Zeus/pdvJava/GERAL/Sincro/Web/ModuloPHP/

  

Acesse a pasta de destino e valide:

cd /Zanthus/Zeus/pdvJava/GERAL/Sincro/Web/ModuloPHP

ls

  
  

🔹 5️⃣ Descompactação do Módulo

Descompacte o módulo atualizado sobrescrevendo os arquivos existentes:

unzip -o e cole o modulo aqui