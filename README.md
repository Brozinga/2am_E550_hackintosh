#  2AM E550 - Big Sur

####  Screenshot
![screenshot](https://user-images.githubusercontent.com/28004053/139112858-a3c80404-befd-46b4-8823-974e9f3c2fcc.png)


##  Meu Sistema
- Processador: Intel® Core ™ i5 9400 Coffee Lake
- Ram: 24GB DDR4
- Chipset: H370
- Gráfico: Intel® UHD Graphics 630 e Nvidia GeForce® GTX 1050 3GB
- Armazenamento: 256GB M.2 Nvme (Windows) / 480GB SSD Sata (MacOS) / 1TB Nvme SATA (Arquivos)
- Rede e Bluetooth: Intel(R) Wireless-AC 9462
- Áudio: Realtek ALC269
- Touchpad: Synaptics SMBus TouchPad
- BIOS: American Megatrends Inc 1.07.08X (16/08/2019)

##  BIOS
- Desabilite o Boot via Rede.
- Habilite VT-X
- Defina o modo SATA para AHCI.
- Desativar inicialização segura
- Gerar novo SMBIOS [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
- Corrija o CFG-Lock para um melhor gerenciamento de energia [Dortania](https://dortania.github.io/OpenCore-Desktop-Guide//extras/msr-lock)

## DICAS
- Eu não sou um profissional da parte de Hackintosh, então essas UEFIs são o resultado de muita pesquisa e umas modificações leves.
- A EFI que está na pasta PENDRIVE-INTALAÇÃO ele serve para substituir a EFI do pendrive com a instalação do BigSur (baixe o RAW no site [olarila.com](https://www.olarila.com/topic/6278-hackintosh-olarila-vanilla-images/) e faça o pendrive com Rufus ou Balena Etcher)
- Após a instalação no HD de boot você vai inserir a outra EFI que já tem as Kexts corretas para o funcionamento de tudo o que está descrito abaixo.
- Se você conheçe mais desse universo e conseguir melhorias faça a solicitação de Pull Request, será um prazer testar e adicionar melhorias.

##  O que está funcionando:
- [x] Áudio, entrada / microfone, saída e [ComboJack](https://github.com/hackintosh-stuff/ComboJack)
- [x] HDMI (Essa é ligada ao chipset e não a GTX)
- [x] Gerenciamento de bateria
- [x] Leitor de Cartão
- [x] Wi-fi e Bluetooth de forma nativa
- [x] Ethernet
- [x] Sleep & Wake
- [x] WebCam
- [x] Usb 3.1 e Tipo C
- [x] Suporte nativo de tecla de atalho com teclas Fn (exceto brilho)

##  Não funciona:
- Mini Display Port devido a ligação com a GTX 1050
- Nvidia GeForce® GTX 1050
- Trackpad/TouchPad a kext do Voodoo causa travamento na inicialização
- Alteração das Luzes do teclado.

## Fix para Trackpad

Para o correto funcionamento do trackpad basta seguir os passos:

Remover as seguintes Kexts [de OC > Kexts]:
VoodooI2C
VoodooI2CHID
[deixar somente a kext "VoodooPS2Controller"]
Com o python atualizado para qualquer versão 3.X (recomendado), abrir o config.plist com o ProperTree e:
Fazer um OC Clean Snapshot (caso apareça algum aviso basta clicar em Sim)
Fazer um OC Snapshot
Salvar o config.plist
Realizar a limpeza da NVRAM (recomendo fazer pela ferramenta do próprio OC, no boot [Tools: Clean NVRAM.efi])

Reiniciar a máquina

![image](https://user-images.githubusercontent.com/28004053/146005801-23bbcc92-4a3b-4b80-93b1-4b22aea9c641.png)


##  Créditos
- Agradecimento a [atosfull](https://github.com/atosfull) pela correção do Trackpad.
-  ** Agradecimentos especiais ** a [dortania](https://dortania.github.io/vanilla-laptop-guide) pelo guia do laptop vanilla.
-  ** Agradecimentos especiais ** a [Acidanthera](https://github.com/acidanthera) pela maioria dos Kexts.
- Graças a [OpenCore Bootloader](https://github.com/acidanthera/OpenCorePkg).
- Agradecimentos a [daliansky](https://github.com/daliansky) por [ACPI Hotpatch Samples for the OpenCore Bootloader](https://github.com/daliansky/OC-little).
- Agradecimentos a [alexandred] (https://github.com/alexandred) por [VoodooI2C](https://github.com/alexandred/VoodooI2C).
- Agradecimentos a [hackintosh-stuff] (https://github.com/hackintosh-stuff) para [ComboJack support for ALC255](https://github.com/hackintosh-stuff/ComboJack).
- Agradecimentos a [corpnewt](https://github.com/corpnewt) para [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS).
