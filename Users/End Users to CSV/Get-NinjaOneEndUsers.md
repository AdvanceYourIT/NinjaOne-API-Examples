# Export All End Users from NinjaOne to CSV

**Author:** Gavin Stone (NinjaOne)  
**Attribution:** Luke Whitelock (NinjaOne) — Authentication Functions  
**Date:** 19th June 2024  
**Version:** 1.0  

## 📝 Description

This script connects to the NinjaOne API, retrieves a full list of **End Users**, enriches the data with organization names, and exports the result to a CSV file.

## What Does It Look Like?

![Screenshot of CSV](https://raw.githubusercontent.com/gavsto/NinjaOne-API-Examples/refs/heads/main/Users/End%20Users%20to%20CSV/Ninja_End_User_CSV_Export.png.png)

### Steps to Generate API Credentials:

1. Go to **Administration > Apps > API > Client App IDs** in NinjaOne.
2. Click **Add** to create a new API token.
3. Set the following:
   - **Platform:** API Services (machine-to-machine)
   - **Name:** Something recognizable (e.g. "End User Export Script")
   - **Redirect URI:** `http://localhost`
   - **Scopes:** `monitoring`, `management`
   - **Grant Types:** Client credentials only
4. Save and **copy the Client Secret** when presented.
5. Copy the **Client ID**.
6. Update the following variables in the script:

```powershell
$NinjaOneInstance = 'app.ninjarmm.com'  # Or eu.ninjarmm.com, ca.ninjarmm.com, etc.
$NinjaOneClientId = '<your-client-id>'
$NinjaOneClientSecret = '<your-client-secret>'
