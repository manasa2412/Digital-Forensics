# Ex.No.4 MHA (Mail Header Analyzer)

## Aim :

● The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.

## Procedure :

**Step 1: Get the Email Header**

● First, you need to copy the full, raw header from the email.

● Gmail: Open the email, click the three dots (⋮), and select Show original.

● Select all the text in the header and copy it

**Step 2: Use a Mail Header Analyzer (MHA)**

● The easiest way to analyze the header is with an online tool.

● Navigate to a site like MXToolbox Email Header Analyzer.

● Paste the entire header you copied into the analysis box.


Click the "Analyze" button to get a parsed, easy-to-read report.


<img width="1899" height="516" alt="4-4" src="https://github.com/user-attachments/assets/81eac3fb-ab2a-49d4-bb39-e31e50a39ba3" />

**Step 3: Analyze The Report**

● This is the most critical step. In the analyzer's report, look for the SPF, DKIM, and DMARC results.

## Review the Overall Delivery Summary

● First, look at the high-level summary to get an immediate sense of the email's status.

● Check DMARC Compliance: The report shows the email is DMARC Compliant. This is the most important overall result.

● Check SPF Status: Both SPF Authenticated and SPF Alignment passed. This means the sending server was authorized.

● Check DKIM Status: DKIM Alignment passed, but DKIM Authenticated failed (❌). This is a critical finding and indicates a problem with the 

email's digital signature.

<img width="1842" height="742" alt="4-5" src="https://github.com/user-attachments/assets/3f315de3-720a-499c-9682-4f325a12bbc0" />

## Investigate the SPF Record and Email Path

● Next, verify why the SPF check passed.

● Examine the SPF Record: The SPF record for the domain is v=spf1 include:mailgun.org ~all. This record explicitly authorizes servers from

Mailgun to send emails on its behalf.

● Trace the Relay Information: The delivery path shows the email was sent from m241-136.mailgun.net.

● Conclusion: Since the email came from a Mailgun server, which is authorized in the SPF record, the SPF check passed.

<img width="1832" height="804" alt="4-6" src="https://github.com/user-attachments/assets/6fbda3a5-07b0-41e2-8c4c-ad76a183692b" />




