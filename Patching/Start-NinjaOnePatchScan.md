# Start-NinjaOnePatchScan.ps1

## Overview
This script triggers an OS Patch Scan for a specified Windows device within the NinjaOne platform. It automates the process of initiating an OS Patch scan. Note this does not apply OS patches, just initiates a scan.

## Equivalent in Ninja
![Screenshot of Ninja Patch Scan](https://github.com/gavsto/NinjaOne-API-Examples/raw/main/Patching/Screenshot_Ninja_Patch_Scan.png)

## Attribution
- **Author:** Gavin Stone (NinjaOne)
- **Attribution:** Luke Whitelock (NinjaOne) for his work on the Authentication Functions
- **Source:** [Start-NinjaOnePatchScan.ps1](https://raw.githubusercontent.com/gavsto/NinjaOne-API-Examples/refs/heads/main/Start-NinjaOnePatchScan.ps1)

## Requirements / Prerequisites
- **NinjaOne API Credentials:** 
  - `NinjaOneClientId`
  - `NinjaOneClientSecret`
- **NinjaOne Instance URL:** e.g., `eu.ninjarmm.com`

## How It Works
1. **Authentication:** The script authenticates with the NinjaOne API using the provided client ID and client secret. It obtains an access token, which is used for subsequent API requests.
2. **Initiate Patch Scan:** After successful authentication, the script sends a POST request to the NinjaOne API endpoint corresponding to the specified device, triggering a patch scan.

## Usage
1. **Set User Variables:**
   - Open the script in an appropriate editor like Visual Studio Code or PowerShell ISE.
   - Replace the placeholder values with your actual NinjaOne instance, client ID, client secret, and the device ID you wish to initiate the OS patch scan on:

     ```powershell
     $NinjaOneInstance = 'your_ninjaone_instance' # e.g., 'eu.ninjarmm.com'
     $NinjaOneClientId = 'your_client_id'
     $NinjaOneClientSecret = 'your_client_secret'
     $NinjaDeviceIDToPatchScan = 'device_id' # e.g., '117'
     ```

2. **Run the Script:**
   - Save the changes.
   - Execute the script in PowerShell:

     ```powershell
     .\Start-NinjaOnePatchScan.ps1
     ```

### Expected Output
Upon successful execution, the script will connect to the NinjaOne API and trigger an OS patch scan for the specified device.

### Troubleshooting
- **Issue:** Authentication fails with an error message.
  - **Solution:** Verify that the `NinjaOneClientId` and `NinjaOneClientSecret` are correct

- **Issue:** The script cannot connect to the NinjaOne API.
  - **Solution:** Ensure that the `NinjaOneInstance` URL is correct and accessible from your network.

- **Issue:** Patch scan does not initiate.
  - **Solution:** Confirm that the `NinjaDeviceIDToPatchScan` corresponds to a valid device ID in your NinjaOne account.

## Notes
- Ensure that your NinjaOne API credentials are kept secure and not shared.
- The script is designed for Windows devices managed within NinjaOne.
