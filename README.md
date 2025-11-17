# ServiceNow_ITSM_Project8
AI Virtual Agent – Incident Creation Assistant
# 🚀 AI Virtual Agent – Incident Creation Assistant (ServiceNow)

This project demonstrates how to build an **AI-driven Virtual Agent** in ServiceNow
that collects user inputs (Issue, Priority, Category) and creates an Incident
using a **Flow Designer Subflow**.

This approach is fully compatible with **ServiceNow PDI Lite Mode**, where:
- Record Actions do not expose output variables
- Script steps are restricted
- NLU is disabled

Despite limitations, this project shows how to build a real **AI-supported Incident Creation workflow**.

---

## 🧠 Features

### ✔ AI-style conversational flow  
### ✔ User input capture  
- Issue description  
- Priority (High, Medium, Low)  
- Category (Network, Email, Access, Hardware, etc.)

### ✔ Incident creation via Subflow  
- Uses Flow Designer → Subflow → Create Record (Incident)  
- No scripting required  
- Works in restricted PDI

### ✔ AI Summary message  
- Shows details back to the user  
- Provides clean closure message  
- Replaces incident number (unsupported in PDI)

---

Virtual Agent Topic
↓
Gather Issue Description
↓
Gather Priority
↓
Gather Category
↓
Subflow Call → Create Incident
↓
AI Summary Message


---

## 🔧 Subflow: **VA_Create_Incident_AI**

### Inputs:
- issue_description (String)  
- issue_priority (String)  
- issue_category (String)

### Action:
**Create Record → Incident**

Field mappings:
- Short description ← issue_description  
- Priority ← issue_priority  
- Category ← issue_category  

(No outputs needed; PDI does not support record outputs.)

---

## 💬 Virtual Agent Topic: AI Incident Creation Assistant

Steps:
1. Greeting  
2. Ask for issue description  
3. Ask for priority (choice input)  
4. Ask for category (choice input)  
5. Call subflow  
6. Display AI summary message

---

## 🧪 Testing

1. Open **Virtual Agent → Designer → Test**
2. Select topic: **AI Incident Creation Assistant**
3. Provide issue, priority, category  
4. Subflow creates the incident  
5. Check: `incident.list` for newly created record

---

## 🏁 Result

✔ Fully working Incident Creation flow  
✔ AI-style conversation  
✔ No scripting required  
✔ Ideal for ITSM/AI portfolio  
✔ Compatible with all PDIs  
