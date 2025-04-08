## 🤖 **Machine-to-Machine Apps**  
*For scripts, tools, and services that run without user interaction*  
**Examples:** PowerShell scripts, Python scripts, cron jobs, CLI tools, backend integrations

---

### 🔐 **Recommended Method:**  
👉 **Client Credentials Flow**

---

### 🛠️ **Setup Steps**

1️⃣ **Register your app**  
Go to:  
**`Administration → Apps → API → Client App IDs → Add`**  
Select:  
**`Application Platform → API Services (machine-to-machine)`**

2️⃣ **Fill in your app details**  
- 🏷️ **Name:** Friendly name for your app  
- 🌐 **Redirect URIs:** Not used — just enter a placeholder like `https://127.0.0.1`
- 📋 **Scopes:** Select which parts of the API your app can access (see below 👇)  
- 🔒 **Grant Type:** Make sure **Client Credentials** is selected  


---

### 🔍 **What are scopes?**  
Scopes control what your app is allowed to do.

| 🔑 Scope       | 🧠 Description                                                                 |
|----------------|---------------------------------------------------------------------------------|
| 📊 **Monitoring** | View-only access to devices and organization info                            |
| 🛠️ **Management** | Full access to manage orgs and devices (e.g., add devices, run scripts)       |
| 🎮 **Control**    | Enable remote access to devices via the API                                   |

---

### 🎯 **Get your access token**

Make a POST request to:

```
https://{app|eu|oc|ca|us2}.ninjarmm.com/ws/oauth/token
```

**With the following parameters:**

```bash
grant_type=client_credentials
client_id=YOUR_CLIENT_ID
client_secret=YOUR_CLIENT_SECRET
scope=YOUR_SCOPES  # optional
```

---

✅ **That's it! You're ready to start making authenticated API requests.**