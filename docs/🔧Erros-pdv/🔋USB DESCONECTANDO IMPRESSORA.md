# COMANDOS

sudo sed -i 's/GRUB_CMDLINE_LINUX="/GRUB_CMDLINE_LINUX="usbcore.autosuspend=-1 /' /etc/default/grub ; sudo update-grub

mkdir -p /boot/efi/EFI/grub/ ; cp -r /boot/grub/* /boot/efi/EFI/grub/ ; cp -r /boot/grub/* /boot/efi/EFI/ubuntu/ ; update-grub

Valida quantas desconexões ocorreram no pdv:

journalctl -k --since yesterday --until now | grep -i "disconnect"