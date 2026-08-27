# Networkwalks-B082-Week3-Password-Cracking-project





#Task 1 🔐 John the Ripper – PDF Password Recovery Using Johnny GUI

## 📌 Project Overview

This project demonstrates an authorized PDF password-recovery lab on Windows using John the Ripper (Jumbo) through its graphical interface, Johnny.

The objective is to understand how password-protected PDF files can be tested for password recovery using an extracted PDF hash and the Johnny GUI.

For this project, an online PDF hash extraction tool was used to convert the password-protected PDF into a hash that could be processed by John the Ripper.

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Windows | Operating system for the lab |
| John the Ripper Jumbo | Password-recovery engine |
| Johnny | GUI front-end for John the Ripper |
| Online PDF Hash Extractor | Converts protected PDF into a crackable hash |
| Password-protected PDF | Lab target file |

---

## 🔄 Project Workflow

```mermaid
flowchart TD
    A[Password-Protected PDF] --> B[Online PDF Hash Extractor]
    B --> C["PDF Hash ($pdf$...)"]
    C --> D[Save Hash as pdf_hash.txt]
    D --> E[Open in Johnny GUI]
    E --> F[Open Password File]
    F --> G[Start New Attack]
    G --> H[Password Recovery]
    H --> I[Open PDF with Recovered Password]

    style A fill:#f8d7da,stroke:#333
    style I fill:#d4edda,stroke:#333
```

---

## 📄 Step 1 – Prepare the PDF

The laboratory file used for this project was:


My Locked PDF1.pdf|[My-Locked-PDF1.pdf](https://github.com/user-attachments/files/31525342/My-Locked-PDF1.pdf)

The PDF was password-protected so that the password-recovery process could be demonstrated in an authorized environment.

---

## 🌐 Step 2 – Extract the PDF Hash

Instead of extracting the hash through the command line, an online PDF hash extraction tool was used.

```mermaid
flowchart LR
    A[Open Hash Extractor Website] --> B[Click Browse]
    B --> C[Select My Locked PDF1.pdf]
    C --> D[Upload PDF]
    D --> E[Wait for Extraction]
    E --> F[Copy Generated Hash]
    F --> G[Save Hash Locally]
```

The extracted hash begins with a PDF-related identifier similar to:

```
$pdf$...
```

The complete hash is unique to the protected PDF.

---

## 💾 Step 3 – Save the Extracted Hash

Create a text file named:

```
pdf_hash.txt
```

The extracted PDF hash is stored inside this file.

Example (illustrative only):

```
$pdf$4*4*128*...
```



---

## 🪟 Step 4 – Open Johnny GUI

After installing John the Ripper Jumbo, open the Johnny graphical interface.

Johnny provides a graphical interface for controlling John the Ripper without requiring the user to perform the main password-recovery process through Command Prompt.

**Johnny Configuration**

Open the Johnny settings and configure the John the Ripper executable if required. The executable is located inside the John the Ripper installation directory.

Example path:

```
C:\JTR\john-1.9.0-jumbo-1-win64\run\john.exe
```

Johnny should then recognize the John the Ripper installation.

---

## 🔑 Step 5 – Load the PDF Hash in Johnny

```mermaid
flowchart TD
    A[Launch Johnny] --> B[Select 'Open Password File']
    B --> C[Browse to pdf_hash.txt]
    C --> D[Select the File]
    D --> E[Open it in Johnny]
    E --> F[Verify Hash Appears in Password Table]
```

The loaded entry should be recognized as a PDF-related hash format.

---

## 🚀 Step 6 – Start the Password-Recovery Attack

```mermaid
flowchart TD
    A[Select 'Start New Attack'] --> B[Choose Recovery Method]
    B --> C[Configure Attack Settings]
    C --> D[Start the Attack]
    D --> E[Johnny Tests Password Candidates]
```

Recovery time depends on several factors:

```mermaid
mindmap
  root((Recovery Time Factors))
    Password Length
    Password Complexity
    Attack Method
    Candidate Password List
    Computer Performance
```

---

## ✅ Step 7 – Check the Recovered Password

After the password is successfully recovered, Johnny displays the recovered password in its interface.

The recovered password can then be used to open:

```
My Locked PDF1.pdf
```

This confirms that the password-recovery process was successful.

---

## 🖼️ Evidence From the Lab

The following screenshots can be included as evidence for the project.

| # | Description | Suggested Filename |
|---|---|---|
| 1 | PDF being selected in the online hash extraction tool | `<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 05 55 AM" src="https://github.com/user-attachments/assets/fcad4ccf-d9d9-42b7-9934-4b0330e323e5" />
` |
| 2 | Generated PDF hash shown in the extraction tool | `<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 06 11 AM" src="https://github.com/user-attachments/assets/e5922818-45ea-4cd9-acb8-4cbc0e2477a9" />
` |
| 3 | Johnny running and configured with John the Ripper | `<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 04 24 AM" src="https://github.com/user-attachments/assets/fa8bdf4e-5551-445a-b1a4-a12abef7cbe5" />
` |
| 4 | `pdf_hash.txt` loaded into Johnny's password table | `<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 05 38 AM" src="https://github.com/user-attachments/assets/0fa17ba9-b210-4373-bf74-a98b4856fc01" />
` |
| 5 | Start New Attack configuration in Johnny and Johnny displaying the successfully recovered password |`<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 04 24 AM" src="https://github.com/user-attachments/assets/1141893b-00bd-46bd-b492-16cf8bb7c14b" />
` |
| 6 | Recovered password successfully opening the PDF | https://github.com/user-attachments/assets/ddf66d81-99e7-47fa-830c-bc7acc82e0eb


---


---

## 🔍 How the Process Works

John the Ripper does not directly need the original PDF contents during the password-testing stage.

```mermaid
flowchart TD
    A[PDF] --> B[Extract Password-Verification Data]
    B --> C[PDF Hash]
    C --> D[pdf_hash.txt]
    D --> E[Johnny GUI]
    E --> F[Test Password Candidates]
    F --> G[Password Match]
    G --> H[Recovered Password]
    H --> I[Open Protected PDF]
```

The extracted hash contains information that allows John the Ripper to verify password candidates against the protected PDF.

---




# 🔹 TASK 2 – PDF Password Recovery (NetworkWalks Tools)

## 🎯 Objective

Task 2 demonstrates PDF password recovery using the **NetworkWalks online tools** instead of John the Ripper / Johnny.

The task consists of two main stages:

1. Extract the PDF hash using the **NetworkWalks Hash Calculator**
2. Perform a dictionary attack using the **NetworkWalks Password Cracker**

---

## 🛠️ Task 2 – Tools Used

- NetworkWalks Project Task Lab
- NetworkWalks Hash Calculator
- NetworkWalks Password Cracker
- Password-protected PDF
- Built-in dictionary / wordlist

---

## 🔄 Task 2 Workflow

```mermaid
flowchart TD
    A[My Locked PDF1.pdf] --> B[NetworkWalks Hash Calculator]
    B --> C["Extract $pdf$ Hash"]
    C --> D[Copy PDF Hash]
    D --> E[NetworkWalks Password Cracker]
    E --> F[Built-in Dictionary]
    F --> G[Dictionary Attack]
    G --> H[Password Match]
    H --> I[Password Recovered]
    I --> J[Open My Locked PDF1.pdf]

    style A fill:#f8d7da,stroke:#333
    style J fill:#d4edda,stroke:#333
```

---

## 🌐 Task 2 – Step 1: NetworkWalks Project Task

The NetworkWalks project page provides the laboratory material for the password-cracking exercise, including the downloadable protected PDF `My Locked PDF1`.

![NetworkWalks Project Task](screenshots/task2-networkwalks-project.png)

<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 21 33 AM" src="https://github.com/user-attachments/assets/9a1651c6-2872-4647-b891-3dcdd67388c6" />


---

## 🔑 Task 2 – Step 2: Open Hash Calculator

The **NetworkWalks Hash Calculator** contains different sections, including Text, File, and PDF. The **PDF** section is used for the password-protected PDF.

![NetworkWalks Hash Calculator]

<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 24 09 AM" src="https://github.com/user-attachments/assets/b6505710-15ba-4b62-b7eb-0eaa3d87f4e8" />


---

## 📄 Task 2 – Step 3: Select the PDF

The protected PDF `My Locked PDF1.pdf` is selected in the PDF section of the Hash Calculator. The tool processes the PDF and extracts a crackable PDF hash.

---

## 🔐 Task 2 – Step 4: Extract the PDF Hash

After processing the PDF, the Hash Calculator displays a PDF hash beginning with `$pdf$...`. The calculator provides options to copy or download the extracted hash.


<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 24 09 AM" src="https://github.com/user-attachments/assets/aee0547d-e721-43e1-a5c1-8eeb54b5dafa" />


<img width="1669" height="810" alt="Screenshot 2026-08-27 at 11 19 05 PM" src="https://github.com/user-attachments/assets/f6dddc78-265a-4b94-b7d4-f6e99a4690a9" />


<img width="1033" height="616" alt="Screenshot 2026-08-27 at 11 18 11 PM" src="https://github.com/user-attachments/assets/f890363e-1187-49e1-9dbc-75fd64051644" />


<img width="1672" height="974" alt="Screenshot 2026-08-27 at 11 04 44 PM" src="https://github.com/user-attachments/assets/825da8ae-4458-4ed3-96df-b32853851837" />

---

## 🔄 Task 2 – Step 5: Open NetworkWalks Password Cracker

The next stage uses the **NetworkWalks Password Cracker**, a separate tool designed for a **dictionary attack**, where password candidates from a wordlist are tested against the PDF hash.

![NetworkWalks Password Cracker](screenshots/task2-password-cracker.png)


<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 25 33 AM" src="https://github.com/user-attachments/assets/69777113-1eff-4361-a232-44e5fe88fda1" />

---

## 📋 Task 2 – Step 6: Enter the PDF Hash

The extracted `$pdf$` hash from the Hash Calculator is copied and entered into the `PDF HASH ($PDF$...)` field of the NetworkWalks Password Cracker.

<img width="1672" height="974" alt="Screenshot 2026-08-27 at 11 05 46 PM" src="https://github.com/user-attachments/assets/35c5a7f6-588b-4d35-b34d-c198b761470f" />

---

## 📚 Task 2 – Step 7: Select the Dictionary

The NetworkWalks Password Cracker provides a built-in password list — `Built-in list (100 passwords)`. The active wordlist is used for the dictionary attack.

---

## 🚀 Task 2 – Step 8: Run the Dictionary Attack

```mermaid
flowchart TD
    A[Dictionary] --> B[Password Candidate]
    B --> C{PDF Hash Verification}
    C -->|❌ No Match| D[Next Candidate]
    D --> B
    C -->|✅ Match| E[Password Recovered]

    style E fill:#d4edda,stroke:#333
```

---

## ✅ Task 2 – Step 9: Password Recovered

The NetworkWalks Password Cracker reports a successful password recovery.

<img width="1197" height="842" alt="Screenshot 2026-08-27 at 11 27 23 AM" src="https://github.com/user-attachments/assets/5eebe34f-050f-4629-a2c6-93127da10166" />


---

## 📄 Task 2 – Step 10: Open the PDF

The recovered password can then be used to open `My Locked PDF1.pdf`. If the password is correct, the protected PDF can be unlocked.

<img width="1672" height="989" alt="Screenshot 2026-08-27 at 11 14 23 PM" src="https://github.com/user-attachments/assets/fb8de0d5-3ac2-4d7b-b373-2a27e3bb4359" />


---

# 🔹 TASK 3 – Authorized Web Portal Security Testing

## 🎯 Objective

Task 3 documents an authorized security-testing exercise performed against:

```
medirozahospital.com
```

The task uses Burp Suite for authentication security testing. After successful login during the authorized project exercise, three password-protected PDF reports were available inside the portal.

The PDF password-protection portion was then tested using the NetworkWalks Hash Calculator and NetworkWalks Password Cracker.



---

## 🛠️ Task 3 – Tools Used

| Tool | Purpose |
|---|---|
| Burp Suite | Authentication security testing |
| medirozahospital.com | Authorized target portal |
| NetworkWalks Hash Calculator | Extracts PDF password-verification hash |
| NetworkWalks Password Cracker | Dictionary attack against extracted hash |
| Password-protected PDF reports | Test artifacts retrieved after login |

---

## 🔄 Task 3 Workflow

```mermaid
flowchart TD
    A[medirozahospital.com] --> B[Burp Suite]
    B --> C[Authentication Security Testing]
    C --> D[Successful Authorized Login]
    D --> E[PDF Reports]
    E --> E1[patient_report_001.pdf]
    E --> E2[patient_report_002.pdf]
    E --> E3[patient_report_003.pdf]
    E1 --> F[NetworkWalks Hash Calculator]
    E2 --> F
    E3 --> F
    F --> G[PDF Hashes]
    G --> H[NetworkWalks Password Cracker]
    H --> I[PDF Password Recovery]

    style A fill:#f8d7da,stroke:#333
    style I fill:#d4edda,stroke:#333
```

---

## 🌐 Step 1 – Access the Portal

The portal was accessed as part of the authorized security-testing exercise. Burp Suite was used to observe the authentication workflow.

---

## 🧪 Step 2 – Authentication Testing with Burp Suite

Burp Suite was used during the authorized assessment to observe and test the authentication workflow. The testing resulted in a successful login within the project environment.

```mermaid
flowchart LR
    A[Launch Burp Suite] --> B[Intercept Login Traffic]
    B --> C[Observe Authentication Workflow]
    C --> D[Successful Login]
```

---

## 📂 Step 3 – PDF Reports

After successful authorized access, the following password-protected PDF reports were available:

| Report File |
|---|
| patient_report_001.pdf |(https://github.com/user-attachments/files/31525295/patient_report_003.pdf)
| patient_report_002.pdf |(https://github.com/user-attachments/files/31525285/patient_report_002.pdf)
| patient_report_003.pdf |(https://github.com/user-attachments/files/31525283/patient_report_001.pdf)

These files are documented as project/test artifacts.


---

## 🔑 Step 4 – Extract PDF Hashes

```mermaid
flowchart TD
    A[patient_report_001.pdf] --> D[NetworkWalks Hash Calculator]
    B[patient_report_002.pdf] --> D
    C[patient_report_003.pdf] --> D
    D --> E[Extracted PDF Hashes]
```

The password-protected PDF reports were processed using the NetworkWalks Hash Calculator. The purpose of this step was to extract the PDF password-verification data required for password auditing. The extracted hashes were then used with the NetworkWalks Password Cracker.

---

## 🔐 Step 5 – Test PDF Password Protection

The extracted PDF hashes were supplied to the NetworkWalks Password Cracker for dictionary-based password testing.

```mermaid
flowchart TD
    A[Extracted PDF Hashes] --> B[NetworkWalks Password Cracker]
    B --> C[Dictionary-Based Testing]
    C --> D[patient_report_001.pdf result]
    C --> E[patient_report_002.pdf result]
    C --> F[patient_report_003.pdf result]
```

The three test artifacts were:

- `[patient_report_001.pdf]`
- `patient_report_002.pdf`
- `patient_report_003.pdf `

The complete activity is documented in:



## videos/task3-complete-demo.mp4

[https://github.com/user-attachments/asset](https://github.com/user-attachments/assets/d08daf17-eccd-4f47-b49e-c80710d39758)

---

## ✅ Step 6 – Results
The results of the authorized exercise are demonstrated in the complete Task 3 video.
