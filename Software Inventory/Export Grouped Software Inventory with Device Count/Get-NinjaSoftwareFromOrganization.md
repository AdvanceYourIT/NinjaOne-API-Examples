# 🛠️ Get-NinjaSoftwareFromOrganization.ps1

## 📝 Overview
This script retrieves software and device data for a specified organization from NinjaOne. It groups the software by name, publisher, and product code, aggregates associated device IDs and names, and then sorts the groups by device count in descending order. Finally, the script exports the results to a timestamped CSV file in the designated output folder.

## What does the output look like?
![Screenshot of CSV](https://raw.githubusercontent.com/gavsto/NinjaOne-API-Examples/refs/heads/main/Software%20Inventory/Export%20Grouped%20Software%20Inventory%20with%20Device%20Count/Screenshot_Ninja_Export_Software.png)

## 🙏 Attribution
- **Author:** Gavin Stone (NinjaOne)
- **Attribution:** Luke Whitelock (NinjaOne) for his work on the Authentication Functions

## ⚙️ Requirements / Prerequisites
- **NinjaOne Instance:** Replace `$NinjaOneInstance` with your region instance (e.g., `app.ninjarmm.com`, `us2.ninjarmm.com`, etc.).
- **NinjaOne API Credentials:** Set `$NinjaOneClientId` and `$NinjaOneClientSecret` with your NinjaOne API credentials.
- **NinjaOne Organization:** Set `$UserInputtedOrg`: The name of the organization you want to retrieve data for.
- **CSV Folder to Save To:** Set `$CSVOutputFolder`: The folder path where the CSV file will be saved.

## 🔍 How It Works
1. **Authentication:** The script authenticates with the NinjaOne API using the provided client ID and client secret.
2. **Organization Lookup:** It retrieves all organizations from NinjaOne to map the specified organization name to its corresponding ID.
3. **Data Retrieval:** Using the organization ID, the script fetches all devices and their associated software data.
4. **Data Processing:** The software data is grouped by software name, publisher, and product code. For each group, associated device IDs and names are aggregated.
5. **Sorting:** The grouped data is sorted in descending order based on the number of devices associated with each software group.
6. **Exporting Data:** The final data is exported to a CSV file with a timestamped filename in the specified output folder.

## 🖥️ Usage
1. **Run the Script:**
   Execute the script in your PowerShell environment. For example:

   ```powershell
   .\Get-NinjaSoftwareFromOrganization.ps1
