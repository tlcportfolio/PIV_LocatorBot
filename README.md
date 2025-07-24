# 📦 UiPath Bot – PIV_LocatorBot

PIV Locator Bot is used to extract data from Outlook to an excel file then process it through the EUA portal. It then finally send the corresponding email after determine the distance from the base location to qualified individuals. 

---

## 📁 Project Structure
This project follows the customized stage structure, which can continue from the last stage check-point in case of the bot crash in the middle of the run.

```
📂 PIV_LocatorBot/
├── Data/
│   ├── CMS_Email_Lookup.xlsx
│   ├── CMS_State_Country_Lookup.xaml
│   ├── CMSLocatorV3.xlsx
│   ├── Config.xaml
│   └── Emails.xaml
├── EUA/
│   ├── EUA_Login.xaml
│   ├── EUA_Navigation.xaml
│   └── EUA_Processing.xaml
├── Finalize/
│   ├── Clean_MainProcess.xaml
│   ├── NotifyUser_Error.xaml
│   └── SendEmails.xaml
├── Initialize/
│   ├── Config_Setup.xaml
│   └── Kill_Process.xaml
├── Outlook/
│   ├── Outlook_GetEmailData.xaml
│   ├── Outlook_SendPIVEmail.xaml
│   └── SendEmails.xaml
├── Process/
│   ├── StageConfirmation.xaml
├── Project.json
└── README.md

---
## 🔧 Configuration
All configuration values are stored in `Data/Config.xlsx`, including:
- Input/Output folder paths
- Exception handling settings

## 🔄 Workflow Overview
### 1. **Init State**
- Reads config file and initializes application

### 2. **Get E-QIP Email Info**

### 3. **Send PIV Email**

### 4. **Send Status Email**
- Closes applications and performs clean-up

---

## 📊 Logs & Exception Handling
- Business and system exceptions are logged to local folder.
- Log is customized per individual xaml.
- Uses Retry mechanism for system exceptions as defined in Config.

## 📦 Dependencies
- Microsoft 365 - v2.2.7
- UiPath.System.Activities - v22.4.1
- UiPath.Excel.Activities - v2.20.2
- UiPath.Mail.Activities - v1.18.2
- UiPath.UiAutomation.Activities - v22.10.3

## 📝 Notes
This bot is designed to be modular and scalable. It can be extended to support:
---

## 📬 Contact

For questions or code access, please contact:  
📧 terrylamcao@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/terrylamcao)
