## 🖥️ **Server Apps (Web apps)**  
*For apps running backend logic (e.g., PHP, ASP.NET, Java)*

---

### 🔐 **Recommended Method:**  
👉 **Authorization Code Flow**

---

### 🛠️ **Setup Steps**

1️⃣ **Register your app**  
Go to:  
**`Administration → Apps → API → Client App IDs → Add`**  
Select:  
**`Application Platform → Web`**

2️⃣ **Fill in your app details**  
- 🏷️ **Name:** Friendly name for your app  
- 🌐 **Redirect URIs:** Where NinjaOne sends users after login (e.g., `https://yourapp.com/oauth/callback`)  
- 🔒 **Grant Type:** Select **Authorization Code**  
- 📋 **Scopes:** Choose what your app can do (see [Scopes 👇](#🔍-what-are-scopes))

3️⃣ **Authenticate your users**  
Redirect them to:

```
https://{app|eu|oc|ca|us2}.ninjarmm.com/ws/oauth/authorize?
  response_type=code&
  client_id=YOUR_CLIENT_ID&
  redirect_uri=YOUR_APP_REDIRECT_URL&
  scope=YOUR_SCOPES&
  state=YOUR_STATE
```

After login/consent, NinjaOne redirects back with a `code`.

4️⃣ **Exchange the code for an access token**  
Send a POST request to:

```
https://{app|eu|oc|ca|us2}.ninjarmm.com/ws/oauth/token
```

**With the following parameters:**

```bash
grant_type=authorization_code
client_id=YOUR_CLIENT_ID
client_secret=YOUR_CLIENT_SECRET
code=AUTHORIZATION_CODE
redirect_uri=YOUR_APP_REDIRECT_URL
```

---

## ♻️ **Refresh Tokens (Optional)**  
*Keep your app logged in without asking the user again*

---

### 🔁 **How to enable it:**

1. ✅ Select the **Refresh Token** grant type during app registration  
2. ✅ Add `offline_access` to your scopes when authenticating:

```
scope=offline_access monitoring management
```

---

### 🔄 **How to use it:**

When your access token expires, request a new one using:

```
https://{app|eu|oc|ca|us2}.ninjarmm.com/ws/oauth/token
```

**With these parameters:**

```bash
grant_type=refresh_token
client_id=YOUR_CLIENT_ID
client_secret=YOUR_CLIENT_SECRET  # server apps only
refresh_token=YOUR_REFRESH_TOKEN
```

---

✅ **That’s it! Your server app is ready to securely integrate with the NinjaOne API.**