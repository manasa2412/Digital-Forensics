# Exp.No_02_Recover Deleted or Damaged Files Using TestDisk 
 

---

##  Aim  
● To use TestDisk step by step to recover a missing partition and repair a corrupted one.  

---

##  Procedure Steps  

### Step 1: Log Creation  
● TestDisk starts with an option to create a log file.  
● All hard drives should be detected and listed with the correct size.  

<div align="center">  
<img width="1920" height="1080" alt="2-1" src="https://github.com/user-attachments/assets/8780776e-7d9e-4f2d-8ca4-a8b4c21fa372" />  
</div>  

---

### Step 2: Partition Table Type Selection  
● TestDisk displays the partition table types. Usually, the **default value** is correct (auto-detected).  
● Press **Enter** to proceed.  

<div align="center">  
<img width="1920" height="1080" alt="2-2" src="https://github.com/user-attachments/assets/ad03de73-9464-4492-ab69-0e7229125bd2" />  
</div>  

---

### Step 3: Analyse Current Partition Structure  
● Use the default menu **Analyse** to check partition structure and search for lost partitions.  
● Corrupted or invalid partitions will be shown here.  

<div align="center">  
<img width="1920" height="1080" alt="2-3" src="https://github.com/user-attachments/assets/34d51af4-0268-44b0-a0fb-05af2edc8947" />  
</div>  

---

### Step 4: Quick Search for Partitions  
● TestDisk performs a quick scan and lists partitions found (including missing ones).  
● Highlight the partition and press **p** to list files. Files shown in red are deleted entries.  

<div align="center">  
<img width="1920" height="1080" alt="2-4" src="https://github.com/user-attachments/assets/87b4418f-178d-49a3-809f-cbdac854f9c6" />  
</div>  

---

### Step 5: Deeper Search (If Needed)  
● If a partition is still missing, run **Deeper Search**.  
● This checks backup boot sectors (FAT32, NTFS, ext2/ext3).  

<div align="center">  
<img width="1920" height="1080" alt="2-5" src="https://github.com/user-attachments/assets/b14a2181-21a8-4e01-89bc-eea0c9d35e0e" />  
</div>  

---

### Step 6: Partition Selection & Recovery  
- Navigate partitions found.  
- Use **p** to list files for verification.  
- Change status:  
  - `P` → Primary  
  - `*` → Bootable  
  - `L` → Logical  
  - `D` → Deleted (won’t recover)  

Once correct partitions are set, confirm with **Enter**.  

<div align="center">  
<img width="1920" height="1080" alt="2-6" src="https://github.com/user-attachments/assets/e8b4e946-4a69-4e7a-a84e-6e81d11f3d01" />  
</div>  

---

### Step 7: Partition Table & NTFS Boot Sector Recovery  
- Write the new partition structure → press **Write**, confirm with `y`.  
- If boot sector is damaged, copy from backup using **Backup BS**.  
- After successful recovery, reboot the system.  

<div align="center">  
<img width="1920" height="1080" alt="2-7" src="https://github.com/user-attachments/assets/363411fb-3e10-4567-ad5b-ba186cdc4f19" />  
</div>  

---

##  Conclusion  
- TestDisk can recover **lost/missing partitions** and **repair corrupted ones**.  
- Supports **Quick Search** and **Deeper Search** for thorough analysis.  
- Allows **partition recovery, boot sector repair, and file system integrity restoration**.  
- A powerful open-source tool for forensic and recovery tasks.  
