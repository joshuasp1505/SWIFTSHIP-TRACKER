# 📦 SwiftShip Tracker

**A Salesforce-based parcel management and tracking solution powered by Flow, Prompt Builder and Agentforce AI.**

![Platform](https://img.shields.io/badge/Platform-Salesforce-00A1E0?logo=salesforce&logoColor=white)
![Org](https://img.shields.io/badge/Org-Developer%20Edition-blue)
![AI](https://img.shields.io/badge/AI-Agentforce-purple)
![Automation](https://img.shields.io/badge/Automation-Salesforce%20Flow-orange)

---

## 🔗 Project Links

| Resource | Link |
|----------|------|
| 📁 GitHub Repository | [SWIFTSHIP-TRACKER](https://github.com/joshuasp1505/SWIFTSHIP-TRACKER.git) |
| 🎥 Demo Video | [Watch on Google Drive](https://drive.google.com/file/d/1OBq7mScRmpxzCEHmXc9yYp09Cq8jB4yz/view?usp=sharing) |
| 📄 Project Documentation | *SwiftShip Tracker* (project document PDF in this repository) |

---

## 📖 Overview

SwiftShip Tracker centralizes parcel, sender, receiver and delivery information in Salesforce so that booking, tracking, delivery updates and customer communication can be managed from one system.

Customers can ask the **Agentforce AI agent** about their parcel in plain language (for example, *"parcel details about p002"*) and receive the Parcel ID, status, weight and estimated delivery date instantly, without waiting for manual support.

---

## ❗ Problem Statement

- Customers often contact support or use multiple applications to book and track parcels.
- Delivery agents need manual handling to update parcel status.
- Administrators lack one centralized view to monitor parcel operations.

SwiftShip Tracker addresses these problems with a unified data model, automated Flows and a conversational AI tracking agent.

---

## 🎯 Objectives

- Centralize parcel and customer information in Salesforce.
- Simplify parcel booking and delivery tracking.
- Provide clear shipment status and estimated delivery information.
- Automate parcel updates through Salesforce Flow.
- Provide AI-assisted parcel tracking through Agentforce.
- Protect data using role-based and field-level access.

---

## ✨ Key Features

- **Centralized data model** for Parcel, Delivery, Sender and Receiver records.
- **Parcel status tracking** with a status picklist, weight and estimated delivery date.
- **Flow automation** that retrieves parcel details and supports status update and confirmation actions.
- **Conversational tracking** using Agentforce with a Parcel Tracker subagent and a Parcel Details action.
- **Prompt Builder** to retrieve and present Parcel ID, Status, Weight and Estimated Delivery Date.
- **Grounded AI responses** based on real Salesforce data.
- **Permission sets** controlling access to objects and to the agent.

---

## 🏗️ Architecture

### User Journey

```
Parcel Booking → Record Creation → Dispatch & Shipment → In-Transit Tracking
→ Out for Delivery → Delivery Confirmation → Customer Notification → Feedback / Support
```

### AI Tracking Flow

```
Customer Query → Agentforce AI → Prompt Builder → Flow → Parcel Record
→ Status / Weight / Estimated Delivery → Conversational Response
```

---

## 🗄️ Data Model

| Object | Purpose |
|--------|---------|
| `Parcel__c` | Stores parcel and shipment information |
| `Delivery__c` | Stores delivery and delivery-status information |
| `Sender__c` | Stores sender details |
| `Receiver__c` | Stores receiver details |

**Parcel fields:** Parcel ID (Auto Number), Parcel Name (Text), Sender (Lookup), Status (Picklist), Weight (Number), Estimated Delivery (Date).

---

## 🛠️ Tech Stack

| Area | Technology |
|------|------------|
| Platform | Salesforce Developer Edition Org (Lightning Experience) |
| Data | Custom Objects and Relationships |
| Automation | Salesforce Flow |
| AI | Agentforce, Agentforce Builder, Prompt Builder |
| Security | Permission Sets, Role-based and Field-level Access |

---

## ⚙️ Setup Instructions

1. Sign up for a free **Salesforce Developer Edition** org.
2. Enable **Agentforce** and **Einstein Generative AI** in Setup.
3. Create the custom objects `Parcel__c`, `Delivery__c`, `Sender__c` and `Receiver__c` with the fields described above.
4. Create sample parcel records (for example P001, P002).
5. Build and **activate** the **SwiftShip Tracker** autolaunched Flow. It takes a Parcel ID as input, uses *Get Records* to fetch the parcel and assigns the output values.
6. In **Agentforce Builder**, create the **Parcel Tracker** subagent and link the **Parcel Details** action to the Flow.
7. Configure **Prompt Builder** to return Parcel ID, Status, Weight and Estimated Delivery Date.
8. Create a permission set that grants access to the four objects and assign it to the users who will use the agent (the SwiftShip permission set).
9. Open the agent in **Agentforce Builder → Preview** and start testing.

---

## ▶️ How to Use

1. Open **Agentforce Builder** and select the SwiftShip Tracker agent.
2. In the preview panel, type a query such as:

   ```
   parcel details about p002
   ```

3. The agent routes to the **Parcel Tracker** subagent, runs the **Parcel Details** action, and replies with the parcel information.
4. Confirm the response in the **Summary / Trace** panel, where the output is marked **Grounded**.
5. Open the Parcel record in Salesforce to verify the data matches.

---

## 📸 Screenshots

> All screenshots are stored in the [`images/`](images/) folder.

### 1. Salesforce Setup

<p align="center">
  <img src="images/01-salesforce-setup.png" alt="Salesforce Setup home screen" width="850">
  <br>
  <em>Salesforce Developer Edition org (Lightning Experience).</em>
</p>

### 2. Data Model

<p align="center">
  <img src="images/02-parcel-data-model.png" alt="Parcel object fields and relationships" width="850">
  <br>
  <em>Parcel object with Parcel ID, Name, Sender, Status, Weight and Estimated Delivery.</em>
</p>

### 3. Flow Automation

<p align="center">
  <img src="images/03-flow-builder.png" alt="Flow Builder showing the parcel flow" width="850">
  <br>
  <em>Autolaunched Flow: Get Parcel Records, Parcel Updates action, Assignment Outputs.</em>
</p>

### 4. Agentforce Builder

<p align="center">
  <img src="images/04-agentforce-builder.png" alt="Agentforce Builder with Parcel Tracker subagent" width="850">
  <br>
  <em>Parcel Tracker subagent with the Parcel Details action.</em>
</p>

### 5. Security

<p align="center">
  <img src="images/05-permission-sets.png" alt="Permission Sets list" width="850">
  <br>
  <em>Permission sets controlling access to objects and the agent.</em>
</p>

### 6. Agent Testing

<p align="center">
  <img src="images/06-agentforce-testing.png" alt="Agentforce preview returning parcel details" width="850">
  <br>
  <em>Test query returning parcel details with the reasoning trace.</em>
</p>

### 7. Final Demo

<p align="center">
  <img src="images/07-agentforce-final-demo.png" alt="Final Agentforce conversation" width="850">
  <br>
  <em>Final conversation showing grounded parcel information.</em>
</p>

---

## ✅ Testing

| Test | Expected Result |
|------|-----------------|
| Open Parcel Tracking Agent | Agent is available and configured |
| Check assigned topic | Parcel-related topic and SwiftShip Tracker action are linked |
| Check Flow | SwiftShip Tracker Flow is activated |
| Track parcel | Parcel details are returned for the supplied Parcel ID |
| Update delivery status | Status is updated and a confirmation is returned |
| Validate Salesforce record | Parcel record reflects the expected change |

---

## ⚠️ Limitations

- Implemented and tested in a Salesforce Developer Org only.
- Production UAT, sandbox deployment and enterprise CI/CD are outside the project scope.
- Agentforce responses depend on correct prompts, topics and available Salesforce data.
- External logistics integrations can increase implementation complexity.

---

## 🚀 Future Scope

- Extend Agentforce to handle more parcel-management queries.
- Improve real-time delivery tracking.
- Expand Experience Cloud customer self-service features.
- Add reports and dashboards with delivery-performance analytics.
- Integrate external logistics systems.
- Improve AI prompts and conversational experience.
- Introduce sandbox and CI/CD deployment.
- Automate additional parcel operations and customer notifications.

---

## 👥 Team

**Team ID:** SWTID-2026-1155
**College:** Arasu Engineering College

| Name | Role |
|------|------|
| Joshua S P | Team Leader |
| Agsha A | Team Member |
| Arulnathan K | Team Member |
| Bagavath G V | Team Member |
| Fadil A | Team Member |

**Contact:** spjoshua2006@gmail.com

---

## 📅 Submission

Submitted on **3rd October 2026**.

---

<p align="center">Built with ❤️ on Salesforce</p>
