# ODOT PLC Integration
  <img width="609" height="398" alt="FairinoOdot" src="https://github.com/user-attachments/assets/2c520f63-4bb6-459b-b5e2-8339da075d1d" />
  This document describes the integration between Fairino Robot and ODOT PLC using Modbus communication.

---

## 1. Purpose
Integrating module between Fairino Robot and ODOT PLC (CodeSys environment).

## 2. Outline
Technical information for integrating Fairino robot with ODOT PLC system.

## 3. Scope of Construction
- Design Architecture  
- USP / Main Advantage  
- Detailed Instructions  
- Next Step Work  

## 4. Design Conditions
- PLC: Odot C3351
- Fairino: FR5 3.9.4

## 5. Main Advantages
- Low-cost integration (No additional software purchase required)  
- Compatible with CodeSys-based systems  
- Flexible Modbus communication  


## 6. Communication Setup
### 6.1 Architecture
  - PLC → Master  
  - Robot → Slave  

### 6.2 Settings
### 6.2.1 Robot Settings
  - Use Pendant Robot, Set Eth 0 to default (192.168.57.2)
  - Turn On Modbus Slave in that port
  - Use Modbus Pool to check if the modbus status are OK

### 6.2.2 PLC Settings
  - Make sure PLC are initialized and can work properly (ladder program are exceuted)
  - Change PLC Address to 192.168.57.1 can be done via 'IO Config' Software
  - Open CodeSYS, you may need to change your PC IP address
  - Add Ethernet Device to Tree fill in PLC IP address
  - Inside Ethernet Device, Add Modbus master. The PLC will act as modbus master device.
  - Then Add Modbus Slave inside Master for registering the slave device connected to the master device.
  - Fill in Robot IP address 192.168.57.2 port 502
  - Open ... this is where you need to put the Modbus Mapping
  - Download Appendix 1: ODOT Modbus Mapping
  - Upload the file to CodeSYS to make change.
  - Compile then upload to check the change.
          
--- 

