# 🧾 Configuração de Balança Toledo USB no PDV

## 📌 Identificação do dispositivo

- Vendor ID e Product ID da balança:

1509:2206

- Identificação completa:

usb-TOLEDO_CDC_DEVICE_0123456789-if00

---

## 🔍 1️⃣ Verificar porta da balança

Listar dispositivos seriais por ID:

ls -all /dev/serial/by-id/

### 📄 Exemplo de saída:

usb-TOLEDO_CDC_DEVICE_0123456789-if00 -> ../../ttyACM2

> 💡 Isso indica que a balança está usando a porta `ttyACM2`

---

## 🔍 2️⃣ Confirmar via USB (lsusb)

Executar:

lsusb

### 📄 Exemplo de saída:

Bus 002 Device 006: ID 1509:2206 First International Computer, Inc.

---

##  3️⃣ Criar regra udev

Editar o arquivo:

/etc/udev/rules.d/99-balanca.rules

Adicionar ao final:

ACTION=="add", ATTRS{idProduct}=="2206", ATTRS{idVendor}=="1509", SYMLINK+="ttyS2"  
ACTION=="remove", ATTRS{idProduct}=="2206", ATTRS{idVendor}=="1509", SYMLINK-="ttyS2"

> 💡 Isso cria um alias fixo (`ttyS2`) para a balança

---

## ⚙️ 4️⃣ Ajustar configuração do GRUB

Editar o arquivo:

/etc/default/grub

Localizar a variável:

GRUB_CMDLINE_LINUX_DEFAULT

### ✏️ Alterar:

**Antes:**

8250.nr_uarts=4

**Depois:**

8250.nr_uarts=2

---

## 🔄 5️⃣ Atualizar GRUB

Executar:

update-grub

---

## 🔁 6️⃣ Reiniciar o PDV

reboot

---

## 🧪 7️⃣ Configuração no sistema

Após subir o PDV:

- Tipo da balança:

0

- Porta:

COM3

> 💡 COM3 corresponde ao `ttyS2` configurado via udev

---

## ✅ Resultado esperado

- Balança reconhecida corretamente
- Comunicação estável com o PDV
- Pesagem funcionando normalmente no sistema

---

## ⚠️ Observações

- Sempre validar se o `idVendor` e `idProduct` estão corretos (`lsusb`)
- Caso não funcione:
    - Revisar regra udev
    - Confirmar porta correta (`ttyACM*`)
    - Verificar permissões de acesso