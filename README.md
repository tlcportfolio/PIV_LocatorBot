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
│   ├── Kill_Process.xaml
├── Outlook/
│   ├── Config_Setup.xaml
│   ├── Kill_Process.xaml
├── Main.xaml
├── Project.json
└── README.md
```

---

## 🔧 Configuration

All configuration values are stored in `Data/Config.xlsx`, including:
- Input/Output folder paths
- Exception handling settings
- Application credentials (via Orchestrator Assets)

---

## 🔄 Workflow Overview

### 1. **Init State**
- Reads config file and initializes applications (if needed)
- Retrieves credentials from Orchestrator

### 2. **Get Transaction Data**
- Scans `InputInvoices/` directory for `.pdf` or `.xlsx` files
- Loads filenames into the transaction queue

### 3. **Process Transaction**
- Extracts invoice data using Regex and/or Excel activities
- Performs a dummy line-item match (simulate business logic)
- Logs results to output or Transaction Log sheet

### 4. **End Process**
- Closes applications and performs clean-up

---

## 📊 Logs & Exception Handling

- Transaction-level exceptions are handled using the built-in `SetTransactionStatus.xaml`
- Business and system exceptions are logged to Orchestrator
- Uses Retry mechanism for system exceptions as defined in Config

---

## 🧪 Testing

Use the sample files provided in `Data/InputInvoices/` to test various scenarios:
- Valid invoice
- Invalid format
- Missing data

---

## 📦 Dependencies

- UiPath.System.Activities
- UiPath.Excel.Activities
- UiPath.Mail.Activities (optional)

---

## 📝 Notes

This bot is designed to be modular and scalable. It can be extended to support:
- Integration with ERP systems (via API)
- OCR-based invoice processing
- Queue-based dispatch/performer model

---

## 📬 Contact

For questions or code access, please contact:  
📧 terrylamcao@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/terrylamcao)
