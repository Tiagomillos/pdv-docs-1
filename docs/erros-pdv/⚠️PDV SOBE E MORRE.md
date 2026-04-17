# ⚠️ PDV fecha ao iniciar (Erro de Biblioteca)

Se ao **subir o PDV a aplicação fechar automaticamente**, na maioria dos casos o problema está relacionado a **bibliotecas duplicadas ou incorretas**.

Siga o procedimento abaixo.

---

# 📂 1. Verificar pasta de bibliotecas

Primeiro verifique qual é a **versão do Ubuntu** utilizada no PDV.

## Ubuntu 22

/Zanthus/Zeus/lib_u22

## Ubuntu 64

/Zanthus/Zeus/lib_u64

---

# 🔎 2. Verificar bibliotecas duplicadas

Dentro da pasta correspondente:

- Verifique se **existe alguma pasta duplicada**
    
- Verifique se **há bibliotecas repetidas ou extras**
    

Caso encontre **pastas duplicadas**, siga o procedimento abaixo.

---

# 🗂️ 3. Correção de Pasta de Biblioteca Duplicada

Se existir uma pasta duplicada (exemplo: `so_u22`), faça o seguinte:

## Entrar na pasta duplicada

cd so_u22

---

## Mover os arquivos para a pasta correta

Verifique se existem arquivos dentro da pasta e execute:

#comandos 
`mv * ..`


Esse comando irá **mover todos os arquivos da pasta atual para a pasta anterior**, que é a pasta correta das bibliotecas.

---

# 🧹 4. Limpeza (opcional)

Após mover os arquivos:

- Verifique se a pasta duplicada ficou **vazia**
    
- Caso esteja, ela pode ser **removida para evitar confusão futura**
    

Exemplo:

rmdir so_u22

---

# ▶️ 5. Subir o PDV novamente

Após corrigir as bibliotecas:

1. Inicie novamente o **PDV**
    
2. Verifique se a aplicação **sobe normalmente**
    

---

✅ **Resultado esperado:**

- Bibliotecas organizadas corretamente
    
- PDV iniciando sem encerrar automaticamente
  
  
  
  