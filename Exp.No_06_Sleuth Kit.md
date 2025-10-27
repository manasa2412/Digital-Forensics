# Ex.No.6 — The Sleuth Kit (TSK):

---

## Aim
To use **The Sleuth Kit (TSK)**, a collection of command-line tools, to analyze a disk image (`4Dell Latitude CPi.E01`), examine its file system, and recover digital evidence.

---

## 🛠️ Prerequisites & Installation

1. **Sleuth Kit Tools:** Download the Windows version of Sleuth Kit (`sleuthkit-4.14.0-win32.zip`) and extract it to a known location (e.g., `C:\Users\sleuthkit-4.14.0-win32`).
2. **Evidence Files:** Download the sample disk image files (`4Dell Latitude CPi.E01` and `4Dell Latitude CPi.E02`) from the Google Drive link provided in the lab manual.
3. **Case Folder:** Create a dedicated folder for your investigation, for example: `C:\Forensics_Lab`. Place the evidence files inside this folder.

---

## Procedure

### Step 1: Open Command Prompt & Navigate
- Open the Command Prompt (`cmd.exe`) **as Administrator**.
- Navigate to the `bin` directory inside your Sleuth Kit folder. This is where all the executable tools (`.exe`) are located.

```bash
C:\Windows\System32> cd C:\Users\sleuthkit-4.14.0-win32\bin
```


<p align="center">
<img width="534" height="79" alt="Screenshot 2025-10-25 084644" src="https://github.com/user-attachments/assets/587309bf-6160-46ee-b8d2-9ba54a988b9d" />
</p>


---

### Step 2: List Partitions (`mmls`)
- Use the `mmls` (list partitions) command to view the partition table of the disk image. This is critical for finding the **offset** (the starting sector) of the partition we want to analyze.
- The path to the image file (`C:\Forensics_Lab\4Dell Latitude CPi.E01`) must be in quotes.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> mmls.exe "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```

📁 **Tip:** The output shows the NTFS / exFAT (0x07) partition (Slot 002) starts at sector 63. This is our offset for the next commands.


<p align="center">
<img width="819" height="319" alt="Screenshot 2025-10-25 084720" src="https://github.com/user-attachments/assets/d954ec00-9ba4-4f0e-98ec-ff0b433588c8" />
</p>


---

### Step 3: Analyze File System (`fsstat`)
- Use the `fsstat` (file system statistics) command to get detailed information about the partition.
- We use the `-o 63` flag to specify the partition offset we just found.
- This command prints the output directly to the screen.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> fsstat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01"
```


<p align="center">
<img width="694" height="645" alt="Screenshot 2025-10-25 084902" src="https://github.com/user-attachments/assets/1567b244-f6b7-4663-846e-7c8914942ca7" />
</p>
 

---

### Step 4: List Files and Directories (`fls`)
- Use the `fls` (list files) command to recursively list all files and directories in the partition.
- We use `-r` for recursive and pipe the output `>` to a text file (`file_list.txt`) for easy review and documentation.
- This command will not show any output in the terminal.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> fls.exe -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\file_list.txt
```

📁 **Tip:** You can now open `file_list.txt` in your `C:\Forensics_Lab` folder to see all the files.

 
<p align="center">
  <img width="1120" height="43" alt="image" src="https://github.com/user-attachments/assets/639f5181-39a9-4c35-855a-471b81146948" />
</p>
 

---

### Step 5: Analyze File Metadata (`istat`)
- Use the `istat` (inode statistics) command to get detailed metadata about a specific file, such as its MAC (Modified, Accessed, Changed) times.
- From the `file_list.txt`, we identified an interesting file: `Mr. Evil.bmp`.
- Its inode number (the number before the hyphen) is `9871`.
- We redirect the output to a file for our report.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> istat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\metadata_Mr_Evil.txt
```


<p align="center">
  <img width="1886" height="338" alt="image" src="https://github.com/user-attachments/assets/726eb8d2-3ad3-4913-9631-7bb0deac00be" />
</p>


---

### Step 6: Recover a File (`icat`)
- Use the `icat` (inode cat) command to extract the contents of the file using its inode number.
- We use the same inode `9871` and redirect the output, saving it directly as a `.bmp` image.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> icat.exe -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" 9871 > C:\Forensics_Lab\RECOVERED_Mr_Evil.bmp
```


<p align="center">
  <img width="1363" height="362" alt="image" src="https://github.com/user-attachments/assets/8a302fb6-52f8-4987-b010-4490ddebb878" />
</p>
 

---

### Step 7: Create an Event Timeline (`mactime`)
- Finally, we create a full timeline of all file activity on the system.
- First, generate a "body file" using `fls`. This file lists MAC times for all files.

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> fls.exe -m / -r -o 63 "C:\Forensics_Lab\4Dell Latitude CPi.E01" > C:\Forensics_Lab\body.txt
```

- Second, use the `mactime.pl` Perl script to sort the body file into a chronological timeline, saved as a `.txt` file (which can also be opened in Excel).

```bash
C:\Users\sleuthkit-4.14.0-win32\bin> mactime.pl -b C:\Forensics_Lab\body.txt > C:\Forensics_Lab\timeline.txt
```


<p align="center">
  <img width="1655" height="160" alt="image" src="https://github.com/user-attachments/assets/bd0a0b07-4c8f-47a0-8437-6179b96fba8e" />
</p>
 

---

## ✅ Result
By following these steps, we successfully used The Sleuth Kit to analyze the `4Dell Latitude CPi.E01` disk image. We were able to:

- List the partition table (`mmls`) and identify the correct partition offset (63).
- Analyze the file system metadata (`fsstat`).
- List all files and directories, including deleted ones (`fls`).
- Inspect the detailed metadata of a target file (`istat` on inode 9871).
- Successfully recover the file `Mr. Evil.bmp` (`icat`).
- Generate a full chronological timeline of all file system activity (`mactime`).

All output files and recovered evidence are now stored in the `C:\Forensics_Lab` case folder, ready for reporting.

---
