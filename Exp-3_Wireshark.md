**Ex.No.3 Wireshark – Network Packet Capture and Analysis Tool**


Procedure: Capturing Plaintext Passwords


**Step 1: Start Capturing Packets**

● First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").

● Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

<img width="1912" height="773" alt="3-1" src="https://github.com/user-attachments/assets/5bea46ee-b8a9-45c4-9d5c-65e2dd49b18b" />





● Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic 

passing through that interface.

<img width="1897" height="977" alt="3-2" src="https://github.com/user-attachments/assets/313fb1be-5425-48b0-9504-22a80cae4eba" />



**Step 2: Generate Login Traffic**

● Open a web browser and navigate to http://testphp.vulnweb.com/login.php.

● Enter any dummy credentials. For this example, we'll use:

● Username: manasa

● Password: manasa@2005

● Click the login button. The login will fail, but the data has already been sent across the network.


<img width="1302" height="961" alt="3-3" src="https://github.com/user-attachments/assets/f164a6d1-c03e-4f9b-87fd-a26f37f7b61b" />


**step 3: Stop Capture and Filter Traffic**

● Return to Wireshark and click the Stop button (the red square).

● In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look 
for an HTTP POST request.

● Apply the following filter to find the exact packet and press Enter:


<img width="1919" height="574" alt="3-4" src="https://github.com/user-attachments/assets/cc315447-6524-40ee-92b3-f3e55b4fa751" />


**step 4: Inspect the Packet to Find Credentials**

● In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

● In the Packet Details pane below the list, expand the following sections:

● Hypertext Transfer Protocol

● HTML Form URL Encoded

● Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.

<img width="1862" height="915" alt="3-5" src="https://github.com/user-attachments/assets/8b41f631-fd84-4037-bd46-07ce3fa25d1c" />


**Result**

The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the
plaintext data that was transmitted over the network:
This result confirms the inherent security flaw of the HTTP protocol. Any sensitive data sent over HTTP is transmitted openly, making it 
trivial to intercept.





















