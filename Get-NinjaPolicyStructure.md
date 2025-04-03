# Get-NinjaPolicyStructure.ps1

## 📝 Overview

This PowerShell script connects to the NinjaOne API to retrieve and display the policy structure of your NinjaOne environment. It provides an overview of each policy, including the number of devices assigned and any devices with policy overrides (referred to as "snowflake" devices). The output is presented in an interactive HTML file and also printed to the console.

## 🏷️ Attribution

- **Author:** Gavin Stone (NinjaOne)
- **Attribution:** Luke Whitelock (NinjaOne) for contributions to the authentication functions
- **Source:** [Get-NinjaPolicyStructure.ps1](https://raw.githubusercontent.com/gavsto/NinjaOne-API-Examples/refs/heads/main/Get-NinjaPolicyStructure.ps1)

## 📋 Requirements / Prerequisites

- **NinjaOne API Credentials:** 
  - `NinjaOneInstance`: Your NinjaOne instance URL (e.g., `app.ninjarmm.com`, `us2.ninjarmm.com`, `eu.ninjarmm.com`, `ca.ninjarmm.com`, `oc.ninjarmm.com`)
  - `NinjaOneClientId`: Your NinjaOne API Client ID
  - `NinjaOneClientSecret`: Your NinjaOne API Client Secret
- **PowerShell Environment:** 
  - PowerShell 5.1 or later
- **Permissions:** 
  - Administrator privileges to execute the script
- **Internet Access:** 
  - Required to connect to the NinjaOne API

## ⚙️ How It Works

1. **Authentication:** 
   - The script authenticates with the NinjaOne API using the provided `NinjaOneInstance`, `NinjaOneClientId`, and `NinjaOneClientSecret`.
   - It obtains an access token, handling token refreshes as needed.

2. **Data Retrieval:** 
   - After successful authentication, the script queries the NinjaOne API to gather information about the policy structure.
   - It retrieves details about each policy, including assigned devices and any devices with policy overrides ("snowflake" devices).

3. **Output Generation:** 
   - The script generates an interactive HTML report detailing the policy hierarchy, device assignments, and policy overrides.
   - This report is saved to `C:\Temp\NinjaOnePolicyOutput_<timestamp>.html`.
   - The same information is also printed to the console for immediate viewing.

## 🚀 Usage

1. **Set User Variables:** 
   - Open the script in a text editor.
   - Locate the user-editable variables section and set the following:
     ```powershell
     $NinjaOneInstance = 'your_ninjaone_instance'
     $NinjaOneClientId = 'your_client_id'
     $NinjaOneClientSecret = 'your_client_secret'
     ```

2. **Run the Script:** 
   - Open PowerShell with administrative privileges.
   - Navigate to the directory containing the script.
   - Execute the script:
     ```powershell
     .\Get-NinjaPolicyStructure.ps1
     ```

3. **View the Output:** 
   - Upon execution, the script will print the policy structure to the console.
   - An interactive HTML report will be generated and saved to `C:\Temp\NinjaOnePolicyOutput_<timestamp>.html`.
   - Open this HTML file in a web browser to explore the policy structure interactively.

## 🛠️ Troubleshooting

- **Authentication Errors:** 
  - Ensure that the `NinjaOneInstance`, `NinjaOneClientId`, and `NinjaOneClientSecret` variables are set correctly.
  - Verify that your API credentials have the necessary permissions.

- **HTML Report Not Generated:** 
  - Confirm that the `C:\Temp` directory exists and is writable.
  - Check for any errors in the console output that might indicate issues during data retrieval or file creation.

- **Incomplete Data:** 
  - Ensure that your NinjaOne environment has policies and devices configured.
  - Verify that the API credentials used have access to all necessary data.

## 📝 Notes

- **Security:** 
  - Handle your API credentials with care. Avoid hardcoding them in scripts; consider using secure methods to store and retrieve them.

- **Script Maintenance:** 
  - This script is marked as a work in progress. Regularly check the source for updates or improvements.

- **Customization:** 
  - The script can be modified to change the output format or to include additional data as needed. Ensure you understand the script's functionality before making changes.

- **Support:** 
  - For assistance or to report issues, refer to the source repository or contact NinjaOne support.
