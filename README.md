
# Brute-Force WiFi Password Tester for Windows

## Overview

The Brute-Force WiFi Password Tester for Windows is a PowerShell script meticulously engineered for testing WiFi password security. Designed for ethical hackers, network administrators, and cybersecurity enthusiasts, this script systematically tests WiFi passwords by leveraging customizable parameters, SSID-based password generation, and integrated password lists. While powerful, it is limited by its sequential testing nature and reliance on Windows systems, making it less efficient than professional-grade penetration testing tools.

This tool must only be used for authorized and ethical purposes, ensuring compliance with all applicable laws.

## Demonstration

Here is a demo video showcasing the script in action:

![Demo Video](demo/demo.mp4)


### Version

- **1.0**

### Tested On

- Windows 10 LTSC

### Requirements

- Windows
- Admin Rights
- Wireless Adapter
- PowerShell
- Some time

## Features

- **Brute-Force Password Testing**:
  - Systematically generates and tests WiFi passwords against detected networks.
- **SSID-Based Password Generation**:
  - Dynamically generates passwords based on detected SSIDs to simulate real-world scenarios.
- **Common Passwords**:
  - Automatically tests a predefined set of commonly used passwords.
- **Custom Password List Support**:
  - Add your custom password lists via the `lists` folder for extended testing.
- **Customizable Parameters**:
  - Users can configure password length, testing limits, separators, and more.
- **Timeout Management**:
  - Adjustable timeouts for WiFi network scanning and connection attempts.
- **Separator Variability**:
  - Supports passwords with special characters (e.g., `-`, `_`, `.`, `@`, `#`, `$`, `!`).
- **Logging**:
  - Creates detailed logs of successful and failed connection attempts for analysis.
- **Network Interface Detection**:
  - Automatically detects the appropriate wireless adapter for operations.

## Limitations

- This tool is designed for Windows environments and lacks the efficiency of professional penetration testing tools.
- Passwords are tested sequentially, making the process slower compared to parallel testing frameworks.

## Script Configuration

The script uses a `$CONFIG` block for customization. Here is a detailed overview of the parameters:

| Parameter           | Description                                                                   | Default Value                         |
| ------------------- | ----------------------------------------------------------------------------- | ------------------------------------- |
| `PasswordLength`    | Specifies the length of passwords to generate and test.                       | `8`                                   |
| `MaxPasswords`      | Defines the maximum number of passwords to attempt during a session.          | `100000`                              |
| `Interface`         | Holds the name of the active wireless adapter.                                | `null`                                |
| `InterfaceGUID`     | Stores the GUID of the wireless adapter.                                      | `null`                                |
| `ScanTimeout`       | Duration (in seconds) allocated for scanning WiFi networks.                   | `10`                                  |
| `ConnectionTimeout` | Time (in seconds) allowed for each connection attempt.                        | `3`                                   |
| `Separators`        | Array of special characters to include in password generation.                | `("-", "_", ".", "@", "#", "$", "!")` |
| `LogDirectory`      | Directory for saving logs. Defaults to the script root or system temp folder. | Script root or temp path              |

## Usage Instructions

### 1. Prerequisites

Before running the script, ensure:

- You have administrative rights.
- A functional wireless adapter is connected and operational.
- PowerShell script execution is enabled (`Set-ExecutionPolicy Unrestricted`).

### 2. Running the Script

Follow these steps to execute the script:

1. Launch PowerShell as an administrator.
2. Navigate to the script’s directory.
3. Execute the script with:
   ```powershell
   .\BruteforceWiFiPasswordTester.ps1
   ```

### 3. Using the Common Password File

The `common-password.txt` file is included as part of the script's resources. It contains a list of commonly used passwords. To use this file:

- Ensure the file is located in the script directory.
- The script will automatically prioritize these passwords during brute-force attempts before proceeding to custom-generated or list-based passwords.

### 4. Adding Custom Password Lists

To extend functionality with additional passwords:

- Place your custom password files in the `lists` folder.
- Files must be in plain text format, with each password on a new line.
- During execution, the script will iterate through all files in the `lists` folder and include them in the testing process after exhausting the `common-password.txt` file.

### 5. Customizing Parameters

Update the `$CONFIG` block in the script to:

- Adjust password lengths and the number of attempts.
- Set scan and connection timeouts.
- Specify a directory for log files.

### 6. Logs

The script generates logs for:

- **Successful Connections**: Logs details of passwords that successfully connect to networks.
- **Failed Attempts**: Records passwords and error messages for unsuccessful attempts.

Logs are stored in the `LogDirectory`. If undefined, the default is the script root or the system temp directory.

## Ethical Use and Warnings

- **Legal Compliance**: Use only with explicit permission from the network owner. Unauthorized use is illegal and punishable by law.
- **Educational and Security Testing Only**: Designed to demonstrate the importance of strong WiFi passwords and aid in authorized security audits.

## Troubleshooting

### Common Issues and Fixes

- **Wireless Adapter Not Recognized**:
  - Ensure the adapter is enabled and supported by your system.
  - Update drivers to the latest version.
- **Script Blocked by Execution Policy**:
  - Set the PowerShell execution policy using:
    ```powershell
    Set-ExecutionPolicy Unrestricted
    ```
- **Insufficient Permissions**:
  - Always run PowerShell as an administrator.

## Contributions

Contributions are welcome! Submit feature requests, improvements, or bug fixes while adhering to ethical hacking principles.

## Disclaimer

This tool is strictly for authorized network security testing and educational purposes. Misuse is prohibited, and the author disclaims all liability for illegal or unethical use.

---

### Tags

`WiFi Tester` `Wlan Tester` `Brute Force Passwords` `SSID Password Testing` `Windows WiFi Cracking` `Cybersecurity Tool` `PowerShell WiFi Script` `WiFi Security Audit` `Password List`

