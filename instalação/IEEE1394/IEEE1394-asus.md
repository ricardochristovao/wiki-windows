# ⚫ ASUS - Erros IEEE1394 durante instalação

## 💬 Mensagem de erro exata
IEEE1394 device driver not found

ou, em alguns modelos:
FireWire controller initialization failed

---

## 🔎 Causa provável
- Controlador **VMD (Volume Management Device)** ativado no BIOS, que oculta o SSD sob uma camada extra.  
- Isso faz o instalador do Windows não enxergar corretamente o NVMe e dar erro de driver.  

---

## 🛠️ Soluções

### ✅ Solução 1 — Desabilitar VMD no BIOS
1. Reinicie o computador e entre no **Setup/BIOS** (geralmente `F2` ou `Del`).  
2. Vá em:
Advanced → VMD Configuration → Disable

3. Isso faz o SSD aparecer direto como **NVMe/AHCI**, sem precisar de driver adicional.  
4. Salve e reinicie a instalação.

---

### 🔄 Alternativa
- Se quiser manter o **VMD habilitado**, baixe os drivers da Intel RST (Rapid Storage Technology) no site da ASUS e carregue durante a instalação do Windows (`Carregar Driver`).  

---

## 📌 Observações adicionais
- Em modelos ASUS de linha **gamer** (ROG/ZenBook), este erro é **bem comum**.  
- Desabilitar o VMD **não afeta o desempenho** se você não usa RAID.  
- Após desabilitar, o Windows deve instalar normalmente sem pedir drivers extras. 🚀
