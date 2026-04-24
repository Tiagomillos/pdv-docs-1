## 🧩 Correção de Tela 3810 / ZIGK

### 🔹 Passo 1 – Testar função 3810

- Execute a **função 3810** no PDV
    
- Verifique se **sobe a tela de opções**
    
- ⚠️ **Se a tela não aparecer**, o problema provavelmente é o **ZIGK**
    

---

### 🔹 Passo 2 – Matar a aplicação

- Encerre a aplicação do PDV antes de qualquer alteração
    
- (garante que o arquivo não esteja em uso)
    

---

### 🔹 Passo 3 – Copiar o ZIGK de outro PDV

- Pegue o arquivo **ZIGK.CFG** de um PDV que esteja funcionando corretamente
    
- Utilize o comando `scp`:
    

`scp -r user@ippdv:/Zanthus/Zeus/pdvJava/ZIGK.CFG .`

- O arquivo será copiado para o diretório atual do PDV destino
    

---

### ✅ Observação

- Após copiar o arquivo, **suba o PDV novamente**
    
- Teste a **função 3810** para confirmar se a tela voltou a aparecer