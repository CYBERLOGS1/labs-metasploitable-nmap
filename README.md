# 🔍 Metasploitable 2 Nmap Lab

## 📝 Objective
To practice network scanning and service enumeration using **Nmap** on a vulnerable target (Metasploitable 2), while experimenting with different virtual network adapter setups for controlled communication.  

---

## 🛠️ Lab Setup
- **Host Machine**: Windows 10  
- **Virtualization**: VirtualBox  
- **Attacker**: Kali Linux  
- **Target**: Metasploitable 2  

### 🔧 Network Configuration
**Kali Linux VM** (2 adapters):  
- **Adapter 1**: **Bridged Adapter** → *Promiscuous Mode: Allow All*  
  - Purpose: Internet access + external network communication  
- **Adapter 2**: **Host-Only Adapter** (VirtualBox Host-Only Ethernet Adapter) → *Promiscuous Mode: Allow VMs*  
  - Purpose: Direct, isolated communication with Metasploitable VM  

**Metasploitable 2 VM** (1 adapter):  
- **Adapter**: **Host-Only Adapter** → *Promiscuous Mode: Allow VMs*  
  - Purpose: Isolated communication with Kali Linux only (no internet exposure)  

✅ This setup ensures:  
- Metasploitable is reachable **only** from Kali (safe & isolated)  
- Kali can still reach the internet for updates/tools  

---

## 🌐 Network Diagram# labs-metasploitable-nmap
Nmap scanning and enumeration on Metasploitable 2 virtual machine 
-  [Internet]
-     │
-     │ (Bridged Adapter - Promiscuous Allow All)
-     │
-  [Kali Linux VM]
-     │
-     │ (Host-Only Adapter - Promiscuous Allow VMs)
-     │
- [Metasploitable 2 VM]

---

## 🚀 Steps Performed
1. Verified communication with Metasploitable:  
   ```bash
   ping 192.168.56.105

