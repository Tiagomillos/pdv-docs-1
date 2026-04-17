`Na sua maquina compacta o arquivo e via WinScp passa esse arquivo para o pdv.`

![[Pasted image 20260305163442.png]]
___________________________________________

#PDV

Já dentro do pdv esse arquivo estará na pasta `/home/user/`
e o `Interface.zip`.

#comandos
`unzip -o Interface.zip`
![[Pasted image 20260305163909.png]]
Nesta pasta Interface terá mais arquivo dentro.
![[Pasted image 20260305164105.png]]
Esse arquivo pode estar com outro nome, por exemplo: 

InterfaceN. então de o comando:
`mv InterfaceN Interface`

e mova para pasta /Zanthus/Zeus/
`cp -r  Interface  /Zanthus/Zeus`

______________
Agora mate a aplicação 

`pkill -9 pdvJava2`
`pkill -9 jav`
`pkill -9 lnx`
`pkill -9 chro`

E suba novamente o Pdv.
