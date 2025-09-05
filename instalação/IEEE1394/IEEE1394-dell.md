# Como corrigir erro de instalação do Windows em notebooks Dell (IEEE 1394)

Durante a instalação do Windows em alguns notebooks Dell, pode aparecer a seguinte mensagem de erro:

> **A instalação não dá suporte à configuração ou instalação em discos conectados por meio de uma porta USB IEEE 1394.**

---

## 🔎 Causa
O instalador do Windows está reconhecendo o HD/SSD interno como se fosse um dispositivo externo (USB/FireWire/IEEE 1394).  
Isso normalmente acontece devido à configuração incorreta do **SATA Operation** na BIOS.

---

## ✅ Solução rápida
1. Reinicie o notebook Dell.  
2. Pressione **F2** para entrar na **BIOS/UEFI**.  
3. Vá em: **System Configuration → SATA Operation**.  
4. Altere a opção para **AHCI** (se estiver em RAID ou ATA).  
5. Salve (**F10**) e reinicie.  
6. Volte ao instalador do Windows e continue normalmente.

---

## 🛠️ Caso o disco ainda não apareça
Use o **DiskPart** no instalador do Windows para limpar e reconfigurar o disco:

```bash
diskpart
list disk
select disk X   # substitua X pelo número do seu disco
clean
convert gpt     # para instalações em UEFI
exit
