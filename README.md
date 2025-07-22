
# 📦 Bin-to-Bin Inventory Management Rollout  

<img width="736" height="439" alt="Screenshot 2025-07-22 113326" src="https://github.com/user-attachments/assets/6cd63ecf-b895-4939-86a6-e86973b40c9a" />

**Project Name:** Inter-Building Bin-to-Bin Control System  
**Author:** Martell Johnson  
**Site Locations:**  
- 4300 (Casting/Receiving)  
- 4413 (Machine Shop)  
- 4366 (Logistics)

---

## 🧭 Objective  
To implement a **Bin-to-Bin transfer system** within Global Shop Solutions (GSS) ERP that improves tracking of inventory between physical buildings along our street. This system aims to enhance:
- Inventory visibility  
- Real-time WIP tracking  
- Fulfillment accuracy  
- Material handler and room manager efficiency  
- Final goods (FG) readiness

---

## 🏗️ System Design Overview

### 🏢 Building Layout + Bin Roles
Refer to the included facility map:
- **Inbound Bins**: Where Room Managers receive and put away parts
- **Outbound Bins**: Where Material Handlers retrieve parts for delivery
- **Staging Areas**: Designated transfer zones between buildings (e.g., CASOUT, LOGINB, MACOUT)

### 👤 Role Responsibilities
- **Casters & Ramp Operators**: Clock in > Run Jobs > Select Destination Bin > Stage output to `CASOUT`
- **Room Managers**: Monitor inbound bins and relocate to final storage
- **Material Handlers**: Pick from outbound bins and deliver to designated staging areas
- **Bin Managers**: Maintain control and audit of bin states

---

## 🧪 Process Flow

### 1. 🛠 Casters / Ramp  
- Clock In (GUI)
- Navigate to Job/Order > Start Job
- Complete Job > Update Job
- **Pop-up: Select Destination BIN**
  - **4300 Building**: Choose `CASOUT` or `4300RO` for ramp-based flow
- Record good/scrap pieces, click **Process**
- **Material physically placed in CASOUT staging area**

### 2. 🚛 Material Handler
- Picks up from `CASOUT`
- Transfers to corresponding Inbound Bin:
  - `LOGINB`, `MACINB`, etc.
- Confirms delivery in system or form log

### 3. 🏢 Room Manager
- Scans inbound BIN
- Confirms delivery and places in inventory
- Inventory is now live in receiving location

---

## 📋 BIN Naming Conventions

| Bin Code | Description |
|----------|-------------|
| CASINB   | Casting Inbound Bin |
| CASOUT   | Casting Outbound Bin |
| MACINB   | Machine Shop Inbound Bin |
| MACOUT   | Machine Shop Outbound Bin |
| LOGINB   | Logistics Inbound Bin |
| LOGOUT   | Logistics Outbound Bin |
| 4300RO   | Ramp Output (intermediate stage) |

---

## ✅ Functional Gains

- Improved part traceability: “Where are my parts?”
- Leaner operations with real-time handoff tracking
- Reduced misplacements and redundant status checks
- Logical staging and transfer accountability across departments

---

## 📂 Artifacts Included

- Facility layout image with bin staging locations
- GUI screenshots of Bin Selector pop-up in GSS  
- Process trees for **Casters** and **Ramp Operators**  
- Training visuals for roles: Bin Manager, Room Manager, Material Handler
  
<img width="639" height="776" alt="image" src="https://github.com/user-attachments/assets/aadc8804-77aa-427c-aa49-57f65837ddbc" />
<img width="719" height="619" alt="Screenshot 2025-07-22 115108" src="https://github.com/user-attachments/assets/79383978-54cd-4e00-a905-110bb0bd0e4b" />
<img width="719" height="619" alt="Screenshot 2025-07-22 115108" src="https://github.com/user-attachments/assets/83dca8a9-41eb-4ca0-9c0b-586056ca1c32" />

---

## 🚀 Future Enhancements
- Automate BIN audit logs via Power Automate  
- Add timestamps for pickup/drop-off to drive KPI metrics  
- Enable email triggers on inbound deliveries per department  

---

## 🗂 Versioning
- `v1.0` Initial rollout — Staging Bins and Roles Defined  
- `v1.1` Final Goods functionality integrated (June 2024)  
