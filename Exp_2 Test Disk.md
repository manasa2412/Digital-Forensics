**Ex.No.2 TestDisk: Open-Source Data Recovery Tool**

**Aim :**

To use TestDisk step by step to recover a missing partition and repair a corrupted one.

**🛠️ Installation**

Linux (Debian/Ubuntu): sudo apt-get install testdisk

macOS (Homebrew): brew install testdisk

Windows: Download the executable from the official CGSecurity website.

Procedure

**1️⃣ Create a Log File**
   
● Launch TestDisk from your terminal or command prompt using sudo testdisk (or testdisk_win.exe on Windows).

● Select the [Create] option to generate a log file of the recovery session. This is helpful for future reference or troubleshooting.

<img width="1920" height="1080" alt="2-1" src="https://github.com/user-attachments/assets/0096d768-900f-4904-8337-b7ece8c97704" />




**2️⃣ Select the Drive to Analyze****
   
● TestDisk will display a list of all detected storage devices.

● Use the Up/Down arrow keys to highlight the drive that contains your lost data.


<img width="1920" height="1080" alt="2-2" src="https://github.com/user-attachments/assets/baa393b6-0876-4b50-a8ef-d0e69c0b3e26" />

● Select [Proceed] to move to the next step.

**3️⃣ Choose the Partition Table Type**

● TestDisk will automatically suggest the most likely partition table type (e.g., Intel/PC, EFI GPT).

● The default value is usually correct. Confirm the selection by pressing Enter.


<img width="1920" height="1080" alt="2-3" src="https://github.com/user-attachments/assets/82988911-e66b-4f4f-942c-2470ff26996a" />






**4️⃣ Analyze Current Partition Structure**
   
● From the main menu, choose [Analyse] and press Enter.

<img width="1920" height="1080" alt="2-4" src="https://github.com/user-attachments/assets/f1d28908-c588-4519-9dd0-bbaf0b37cbaf" />







● This will display the current partition table and check for errors or missing partitions.




**5️⃣ Perform a Quick Search**

   
●After the analysis, you will be prompted to perform a [Quick Search].


<img width="1920" height="1080" alt="2-5" src="https://github.com/user-attachments/assets/aa45ebe6-0f2d-4bb3-abbd-fbb17afa84b8" />









● Select it and press Enter to scan the drive for lost partitions.

● Once a partition is found, you can press p to list its files. Deleted files and folders often appear in red.

● Press q to return to the search results.

**6️⃣. Perform a Deeper Search**
   
● If the Quick Search fails to find your lost partitions, select [Deeper Search].

<img width="1920" height="1080" alt="2-6" src="https://github.com/user-attachments/assets/e8ecf9a1-e4da-47d7-bd52-69478a5cef53" />





● This process can take a long time, as it scans the entire drive, block by block, to find remnants of partition structures.

● Again, use p to preview files and confirm if a found partition is the one you are looking for.

**7️⃣. Modify Partition Status**

● After finding the correct partitions, use the Left/Right arrow keys to set their status.

● Use Left/Right arrow keys to change status:

P: Primary

 *: Bootable

L: Logical

D: Deleted


<img width="1920" height="1080" alt="2-5" src="https://github.com/user-attachments/assets/77c95387-8781-4997-b98e-29c47c927a72" />









● Ensure that the partitions you want to recover are marked as Primary or Logical (and not deleted).

**8️⃣. Write the Partition Table**
   
● Once you are confident the partition structure is correct, select [Write] from the menu.



<img width="1920" height="1080" alt="2-6" src="https://github.com/user-attachments/assets/c3241de7-79d0-4ace-8dec-bbfbf753774b" />







● Confirm the operation by pressing y (for yes). This will write the new partition table to your disk.


<img width="1920" height="1080" alt="2-7" src="https://github.com/user-attachments/assets/98f39ee3-a06c-4f95-981c-576a7822dc73" />







WARNING: This is a permanent change. Double-check your selections before writing.

**9️⃣. Recover File**

● If you just need to recover a few files without fixing the partition table, you can do so from the file list (after pressing p).

● Navigate to the folder containing your desired files.

● Use the colon : key to select the files you want to recover.

● Press the uppercase C key to copy the selected file(s).

● Navigate to a safe destination on a different storage device and press uppercase C again to paste.

**🔟. Exit and Restart**

● Once your task is complete, select [Quit] to exit the program.

● If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.


















