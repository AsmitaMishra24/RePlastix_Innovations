# ♻️ RePlastix Innovations

## 🌱 About the Project

**RePlastix Innovations** is a sustainability-focused Salesforce CRM solution developed as part of a virtual internship to modernize the operations of a recycling enterprise. The project replaces outdated manual processes with real-time automation for tracking plastic waste, managing recycled product inventory, processing orders, and triggering restock workflows.

This implementation leverages both low-code tools like Flow Builder and pro-code techniques like Apex Triggers to ensure seamless, scalable operations with a focus on environmental impact. The system empowers different departments (Recycling, Sales, Warehouse) through role-based access and facilitates secure, efficient collaboration.

## ✨ Key Features

- 📦 **Plastic Waste Tracking:** Monitor weight, type, collection dates, and recycling centers
- 📊 **Inventory Monitoring:** Recycled product stock with threshold alerts for low inventory
- 🔁 **Automated Restocking:** Auto-create and approve restock requests based on stock thresholds
- 🛒 **Order Management:** Capture product orders, update stock upon fulfillment
- 📬 **Email Notifications:** Send alerts to warehouse managers after restock approvals
- 🔐 **Role-Based Access:** Data visibility controlled by roles, profiles, and sharing rules
- 📈 **Insightful Reports:** Dashboards and reports provide decision-making insights
- ⚙️ **Custom Logic with Apex:** Handles complex scenarios like duplicate restock prevention
- ✅ **Validation & Formula Fields:** Ensure clean, accurate data and low stock detection

## 📁 Project Structure

The project is organized as follows:
```bash
RePlastix_Innovations/
├── force-app/
│ └── main/default/
│           ├── applications/
│           ├── classes/
│           ├── flowDefinitions/
│           ├── flows/
│           ├── layouts/
│           ├── objects/
│           ├── permissionsets/
│           ├── profiles/
│           ├── roles/
│           ├── sharingRules/
│           ├── tabs/
│           └── triggers/
│
├── Screenshots/
│   ├── Apex/
│   ├── Fields/
│   ├── Final App Screenshot/
│   ├── Flow/
│   ├── Formula Field/
│   ├── Lightning App/
│   ├── Objects/
│   ├── Profiles/
│   ├── Roles/
│   ├── Sharing Rules/
│   ├── Tabs/
│   ├── Test Record/
│   ├── Users/
│   └── Validation Rules/
│
└── RePlastix Innovations.pdf
```

## 📦 Metadata Configuration (force-app/main/default)

This folder contains all custom Salesforce metadata built for the **RePlastix Innovations** recycling and inventory automation app.

### 🧩 Custom Objects & Key Fields

1. **Plastic Waste (`Re_Plastic_Innovations_Plastic_Waste__c`)**
   - `Weight__c`, `Type__c`, `Collection_Date__c`, `Status__c`, `Recycling_Center__c`, `Location__c`

2. **Recycling Center (`Re_Plastic_Innovations_Recycling_Center__c`)**
   - `Location__c`, `Capacity__c`

3. **Recycled Product (`Re_Plastic_Innovations_Recycled_Product__c`)**
   - `Stock_Level__c`, `Threshold__c`, `Price__c`

4. **Order (`Re_Plastic_Innovations_Order__c`)**
   - `Customer__c`, `Recycled_Product__c`, `Quantity__c`, `Delivery_Date__c`

5. **Restock Request (`Re_Plastic_Innovations_Restock_Request__c`)**
   - `Product__c`, `Requested_Quantity__c`, `Status__c`

---

### 🗂️ Tabs

- `Re_Plastic_Innovations_Plastic_Waste`  
- `Re_Plastic_Innovations_Recycling_Center`  
- `Re_Plastic_Innovations_Recycled_Product`  
- `Re_Plastic_Innovations_Order`  
- `Re_Plastic_Innovations_Restock_Request`

---

### ⚡ Lightning App

- **App Name:** `Re Plastic Innovations`  
- Includes all key tabs for object access and visibility.

---

### 👥 Roles

- **CEO**
- **Recycling Manager**
- **Sales Representative**
- **Warehouse Supervisor**

---

### 🔐 Profiles

- **Platform 1:** Recycling Manager  
- **Platform 2:** Sales Representative  
- **Platform 3:** Warehouse Supervisor

---

### 👤 Sample Users

| Name                            | Role                  |
|---------------------------------|-----------------------|
| John (Sandbox 1 – Production Engg) | Recycling Manager     |
| Quality Inspector               | Sales Representative  |
| Plant Manager Albert           | Warehouse Supervisor  |

---

### 🔄 Sharing Rules

1. **Recycling Manager** → Read access to `Plastic_Waste__c`  
   ➝ CEO → Recycling Manager  

2. **Sales Representative** → Read access to `Recycled_Product__c`  
   ➝ CEO → Sales Representative  

3. **Warehouse Supervisor** → Read access to `Restock_Request__c`  
   ➝ Sales Representative → Warehouse Supervisor  

---

### 🧠 Logic & Automation

- **Formula Field:** `Stock_Low_On_Product` — returns `true` when stock is below threshold
- **Validation Rules:**
  - `Check_Quantity_Not_Zero` — quantity must be > 0
  - `Future_Date_Collection` — blocks future dates for plastic waste collection
- **Flow Builder:**
  - `Stock Level Is Low` — auto-creates restock requests and sends email alerts

---

### 🧾 Apex Code

- `InventoryManager` *(Class)* — core inventory logic  
- `UpdateStockAfterOrder` *(Trigger)* — reduces stock on order  
- `UpdateStockAfterRestockApproval` *(Trigger)* — increases stock  
- `EmailNotificationHelper` *(Class)* — sends email alerts  
- `InventoryManagerTest` *(Test Class)* — ensures Apex test coverage  

---

### 🧪 Test Records

- `Recycling_Center:` PVC Collection  
- `Order:` ORD-0001, ORD-0003  
- `Recycled_Product:` Test Task Record, Plastic Order Record  
- `Restock_Request:` RQST-0001  
- `Plastic_Waste:` RPIPW-0001

## 📸 Screenshots

Below are visual confirmations of key records and modules in the RePlastix Innovations Salesforce app:

<details>
<summary><strong>📦 Order Records</strong></summary>
<img width="1919" height="1079" alt="Re_Plastic_Innovations_Order" src="https://github.com/user-attachments/assets/3cea0b17-d078-4404-9bea-f1fb44578f07" />
</details>

<details>
<summary><strong>🧴 Plastic Waste Records</strong></summary>
<img width="1919" height="1079" alt="Re_Plastic_Innovations_Plastic_Waste" src="https://github.com/user-attachments/assets/f3892f20-3cd3-42c3-8b23-0d844fb777b3" />
</details>

<details>
<summary><strong>🧪 Recycled Product Records</strong></summary>
<img width="1919" height="1079" alt="Re_Plastic_Innovations_Recycled_Product" src="https://github.com/user-attachments/assets/e95db5a6-f0fb-4d3b-bae8-e3030fa27425" />
</details>

<details>
<summary><strong>🏭 Recycling Center Records</strong></summary>
<img width="1919" height="1079" alt="Re_Plastic_Innovations_Recycling_Center" src="https://github.com/user-attachments/assets/2d86f7e5-2757-4b6c-a9bb-b791dba92a0b" />
</details>

<details>
<summary><strong>🔁 Restock Request Records</strong></summary>
<img width="1919" height="1079" alt="Re_Plastic_Innovations_Restock_Request" src="https://github.com/user-attachments/assets/346e8b91-1911-48b9-8423-e0e6fc888d2d" />
</details>

## 📊 Reports
A key report is included:
[RePlastix Innovations](https://github.com/user-attachments/files/21510224/RePlastix.Innovations.pdf)

## 🚀 Setup Instructions
1. Clone the repository:
   ```bash
   git clone https://github.com/AsmitaMishra24/RePlastix_Innovations.git
   ```
2. Deploy to a Salesforce Org using:
   ```bash
   sfdx force:source:deploy -p force-app
   ```
3. Assign profiles and permission sets to test users.
4. Upload sample data manually or use anonymous Apex for test records.

## 📌 **Note:**
> - All screenshots were captured from a Salesforce Developer Edition Org configured for the RePlastix Innovations project.
> - The data shown is **test data** created specifically for demonstrating functionality.
> - To replicate these records, you may use the field values and object names referenced in the screenshots and report.
> - For full setup steps, refer to the [📊 Reports](#-reports) and [🚀 Setup Instructions](#-setup-instructions) sections below.

## 👩‍💻 Developer
This project was developed by [Asmita Mishra](https://github.com/AsmitaMishra24).

## 📬 Contact
For any questions or feedback, feel free to reach out at:
- **GitHub**: [AsmitaMishra](https://github.com/AsmitaMishra24)
- **LinkedIn**: [Asmita Mishra](https://www.linkedin.com/in/asmitamishra1/)
