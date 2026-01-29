# 🧠 AI Burnout Monitoring System v1.0

![Workflow Architecture](AI%20Burnout%20Monitioring%20System.PNG)

## 🚀 Project Overview
In high-pressure environments, "Burnout" is often ignored until it becomes a critical issue. This project is an automated **AI-driven monitoring system** designed to detect early signs of stress and burnout from textual feedback in real-time.

Built using **n8n** and **Microsoft Azure Cognitive Services**, the system analyzes user sentiment and automatically triggers alerts for high-risk cases while maintaining a baseline log for stable trends.

## 🎥 Live Demo
Watch the system in action here:
[**Click to Watch Video Demo**](https://drive.google.com/file/d/1SmGOnvGONjAtla9FY6Ut8Djpp5R7jo7_/view?usp=drive_link)

---

## ⚙️ How It Works

The workflow follows a 4-step logic pipeline:

1.  **📥 Data Ingestion (Input Gateway):**
    * Receives raw text feedback from users via a web form/webhook.
    * Captures metadata like Name and Timestamp.

2.  **🧠 Sentiment Processing (Azure AI):**
    * The text payload is sent to **Microsoft Azure Cognitive Services**.
    * The AI model analyzes the text and returns a **Confidence Score** for Negative, Neutral, and Positive sentiment.

3.  **⚖️ Decision Logic (The Gatekeeper):**
    * A conditional logic gate checks if the **Negative Score > 70%**.
    * **True Path:** Identified as "High Risk/Burnout".
    * **False Path:** Identified as "Stable/Normal".

4.  **⚡ Automated Actions:**
    * **🔴 Critical Path:** Instantly sends an HTML-formatted email alert to the admin and logs the incident in the *Critical Database*.
    * **🟢 Baseline Path:** Silently logs the entry into the *Wellness Baseline Log* for trend analysis without triggering alerts.

---

## 🛠️ Tech Stack

* **Orchestration:** [n8n](https://n8n.io/) (Self-Hosted Workflow Automation)
* **AI Engine:** Microsoft Azure Cognitive Services (Language Service)
* **Database:** Google Sheets (Dual-tab logging for Alerts vs. Baseline)
* **Notification:** Gmail SMTP (Automated HTML Reports)

---

## 📊 Workflow Logic
| Sentiment Score | Status | Action Triggered |
| :--- | :--- | :--- |
| **> 70% Negative** | 🔥 High Risk | 🚨 Urgent Email Alert + Critical Log |
| **≤ 70% Negative** | ✅ Stable | 📝 Baseline Log (Silent) |

---

## 👨‍💻 Author
**Abdullah Zahid**
* *Cloud Automation Enthusiast & Developer*
* Specializing in Low-Code Solutions & AI Integration.

---
*Note: This project demonstrates the power of integrating Enterprise AI models with low-code orchestration tools to solve real-world human resource challenges.*
