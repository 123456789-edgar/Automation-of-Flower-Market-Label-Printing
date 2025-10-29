# 🌸 Automation of Flower Market Label Printing

### Project Overview
This project aims to **automate the flower market labeling process** by transitioning from **manual BarTender template printing** to a **fully integrated SAP Crystal Report design**, allowing **direct barcode and label printing from SAP**.  
By eliminating manual data transfer between systems, this automation enhances **accuracy, efficiency, and consistency** in label generation.

---

## 🧩 Background Information

### The BarTender Labeling Process
**BarTender** is a labeling software widely used across industries such as packaging, manufacturing, and retail to print **product identification labels or stickers**.  
Typically, a label printer machine prints these stickers, which are then affixed to individual items, providing each with a **unique identifier**.

In many production or packaging facilities (e.g., carton or flower manufacturing industries), boxes are prepared for specific clients. Inside these boxes, unique products (like flowers) are packed.  
However, **distinguishing one product box from another** becomes challenging—especially when boxes are already packed and sleeved. This is where **label printing** plays a critical role.

---

### The Current (Manual) Workflow
In most enterprises, the **labeling process is done manually**. Operators manually extract information from business management software (such as **SAP**, **NetSuite**, or **Microsoft Dynamics 365 Business Central**) and then **re-enter** these details into BarTender to generate labels.

This approach is:
- **Error-prone** (due to manual data entry),
- **Time-consuming**, and
- **Difficult to standardize or scale**.

---

## 🧾 Data Source: SAP Business One

Within **SAP Business One**, most of the labeling data already exists in the **Sales Order screen**.  
This screen captures **client-specific information** required to generate the final product label.

### Example of Key Data Fields:
| Field | Description |
|:------|:-------------|
| Customer Name | Identifies the client or destination |
| Variety Name | Type of flower or product variant |
| Length of Variety | Size or stem length of the flower |
| Pack Rate | Quantity or unit packaging rate |
| Line Code | Product identification or internal code |
| Delivery Date | Scheduled date for dispatch |
| Drop-off Point | Final destination or delivery site |

Currently, these same details are **manually entered** into BarTender to generate labels — as illustrated in the following (manual) sample label:
 
> *<img width="1365" height="686" alt="image" src="https://github.com/user-attachments/assets/ef8632ed-b1f9-45ac-bb04-a2d2a1558a09" />*

---

## ⚙️ The Automation Concept

To eliminate manual entry, this project proposes an **end-to-end automation pipeline** that directly integrates **SAP Crystal Report** with the **SQL backend database**.  
This setup allows the label to be **generated and printed automatically** from SAP, using standardized data from the Sales Order.

### 🔗 Integration Overview
1. **Data Source:** SAP Business One Sales Order Table (`@AK_GRPL_C0` and related tables).  
2. **Processing Engine:** SQL queries and stored procedures extract relevant label data.  
3. **Report Design:** SAP Crystal Report replaces manual BarTender templates.  
4. **Output:** Label and barcode automatically printed from SAP with consistent formatting.

> _Example of the Automated SAP Label Output:_  
> *<img width="1365" height="643" alt="image" src="https://github.com/user-attachments/assets/bcec85b1-9c71-431d-b36c-7936ad1c5039" />
*

---

## 🧠 Key Benefits

| Benefit | Description |
|:---------|:-------------|
| **Automation** | Eliminates manual data entry between SAP and BarTender |
| **Accuracy** | Reduces labeling errors caused by human input |
| **Standardization** | Ensures consistent label layouts and formats |
| **Time Efficiency** | Significantly speeds up the labeling workflow |
| **Scalability** | Can be extended to multiple production lines or product categories |

---

## 🧰 Technologies Used

- **SAP Business One**
- **SAP Crystal Reports**
- **Microsoft SQL Server (Backend)**
- **BarTender (Legacy Reference)**
- **Windows Server Environment**

---

## 📊 System Workflow Summary

```mermaid
flowchart LR
    A[SAP Sales Order Data] --> B[SQL Query Extraction]
    B --> C[SAP Crystal Report Template]
    C --> D[Printer Output (Label)]
    D --> E[Box/Product Labeling]
