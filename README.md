# Wazuh Slack Integration  
This project documents the integration of **Wazuh** with **Slack** via **Incoming Webhooks**, enabling real-time alert notifications from the Wazuh Manager to a private Slack channel.

---

## 🎯 Objective  
To configure Slack webhook integration with the Wazuh server so that selected alerts (e.g., severity level 12+) are sent directly to a designated Slack channel for real-time visibility and team response.

---

## 🔍 Why Integrate Slack with Wazuh?  
Slack integration allows security teams to:
- Receive immediate notifications for critical alerts  
- Collaborate directly within Slack threads  
- Accelerate incident response  
- Combine SIEM visibility with communication workflows

---

## 📚 Skills Learned  
- Creating and managing Slack apps  
- Generating secure webhooks  
- Editing Wazuh configuration files for integrations  
- Sending test webhook messages  
- Controlling alert levels and formats  
- Managing Slack channel permissions and roles

---

## 🛠️ Tools Used  
<div>
  <img src="https://img.shields.io/badge/-Wazuh-0078D4?&style=for-the-badge&logo=Wazuh&logoColor=white" />
  <a href="https://api.slack.com/messaging/webhooks" target="_blank"><img src="https://img.shields.io/badge/-Slack-4A154B?&style=for-the-badge&logo=Slack&logoColor=white" />
</div>

---

## 📝 Deployment Steps

### 1. Create a Slack App and Webhook

1. Visit: [https://api.slack.com/messaging/webhooks](https://api.slack.com/messaging/webhooks)
2. Click **"Create your Slack app"**
3. Choose **"From scratch"** and fill out the details
4. Go to `Features → Incoming Webhooks` and switch **Webhooks ON**
5. Create a **private channel** in Slack for alerts:
   - Slack App → Add Channels → Create New Channel (Private)
6. Go back to your Slack App → Incoming Webhooks → Click **“Add New Webhook to Workspace”**
7. Choose the private channel
8. Copy the generated **Webhook URL**

---

### 2. Add the Webhook to Wazuh Configuration

SSH into your Wazuh server and edit the Wazuh manager config:
```bash
sudo nano /var/ossec/etc/ossec.conf
```
