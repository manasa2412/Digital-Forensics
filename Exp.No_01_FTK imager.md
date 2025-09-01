#  Evidence Acquisition Using AccessData FTK Imager  

---

##  Description  

Forensic Toolkit (FTK) Imager is a forensic software product made by AccessData.  
It is capable of **acquiring and analyzing computer forensic evidence**.  

Evidence can be acquired in two ways:  
- **Volatile Memory (RAM)**  
- **Non-Volatile Memory (Hard Disk)**  

The tool can be used either by:  
1. Running FTK Imager portable version from a USB (live acquisition).  
2. Installing FTK Imager on the investigator’s laptop (with a write blocker).  

---

##  Acquiring Volatile Memory  

The FTK Imager tool helps investigators collect the **complete RAM** of a computer.  

### Step 1: Open FTK Imager and Navigate to Capture Memory  
<div align="center">
  
![1 1](https://github.com/user-attachments/assets/a9698c2a-c288-40a0-b186-cfe2b9961a60)  

</div>  

### Step 2: Select Capture Memory  
<div align="center">
  
![1 2](https://github.com/user-attachments/assets/8c93c616-634c-4990-9921-5747bd7108a8)  

</div>  

Options available:  
- Include **Pagefile.sys** (used as extended volatile memory).  
- Save as **AD1 file** (FTK’s image format).  

### Step 3: Start Acquisition  
<div align="center">
  
![1 3](https://github.com/user-attachments/assets/c9814286-7386-4d53-bb30-03572858bf1b)  

</div>  

Clicking "Capture Memory" will acquire RAM and save it as `.mem`.  

---

##  Acquiring Non-Volatile Memory (Disk Image)  

FTK Imager can also acquire **disk images**.  

### Step 1: Create Disk Image  
<div align="center">
  
![1 4](https://github.com/user-attachments/assets/b0ed5fd6-f342-4029-a882-0d78779d30b1)  

</div>  

### Step 2: Select Source Type  
<div align="center">
  
![1 5](https://github.com/user-attachments/assets/dd653499-392f-4489-bc6e-3d73347da741)  

</div>  

Options:  
- **Physical Drive**  
- **Logical Drive (Partition)**  
- **Image File**  
- **Folder Contents**  
- **CD/DVD**  

### Step 3: Choose Drive to Acquire  
<div align="center">
  
![1 6](https://github.com/user-attachments/assets/1df293e4-fa4f-47f6-bac3-d2855ba2fa94)  

</div>  

### Step 4: Select Image Type Format  
<div align="center">
  
![1 7](https://github.com/user-attachments/assets/3d83896b-a04f-4b3d-abff-0311c6df8011)  

</div>  

- **RAW (dd):** No headers, widely supported.  
- **SMART:** Linux-based with compression.  
- **E01:** Proprietary EnCase format with metadata & hash.  
- **AFF:** Open forensic format (AFF4 latest).  

### Step 5: Enter Case Details  
<div align="center">
  
![1 8](https://github.com/user-attachments/assets/94246541-9345-4d84-96a5-8145a6636392)  

</div>  

### Step 6: Set Destination and Fragment Size  
<div align="center">
  
![1 9](https://github.com/user-attachments/assets/bd3d3766-a0fc-4704-8d1f-1e430ba0ae4e)  

</div>  

- Destination folder & file name  
- **Fragment Size (MB):** Set `0` for a single file  
- Enable **Verify Images** for integrity check  

### Step 7: Acquisition in Progress  
<div align="center">
  
![1 10](https://github.com/user-attachments/assets/adf81fc1-36f8-4464-ab1c-08fc7ad2e5c9)  

</div>  

### Step 8: Acquisition Complete  
<div align="center">
  
![1 11](https://github.com/user-attachments/assets/c7af5e65-5f70-4381-ac45-8b4b39ada4db)  

</div>  

A text report is generated with acquisition details.  

### Step 9: Verify Hash Values  
<div align="center">
  
![1 12](https://github.com/user-attachments/assets/1965c0b0-46a1-4dad-a653-ec9d0c5f498e)  

</div>  

Ensures integrity by comparing hash values.  

---

##  Conclusion  

- FTK Imager provides a reliable way to acquire **RAM and Disk images**.  
- Supports multiple formats: **RAW, SMART, E01, AFF**.  
- Ensures **forensic integrity** with hash verification.  
- Widely used for **incident response and forensic investigations**.  
