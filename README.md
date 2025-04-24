# 📬 Automated HR Email Sender from PDF Contacts

This Python script automates the process of extracting HR contact details from a PDF file and sending personalized job application emails with your resume attached.

---

## 🚀 Features

- ✅ **PDF Parsing** – Extracts text from PDF files using `PyPDF2`.
- 🔍 **HR Detail Extraction** – Finds email addresses and infers the corresponding HR contact’s name, job title, and company.
- 🧠 **Context-Based Data Mining** – Extracts meaningful name, title, and organization information from text surrounding each email.
- 📑 **Fallback Table Parsing** – Handles structured table-like data in the PDF as a fallback.
- 📤 **Email Automation** – Sends personalized emails to each HR contact with your resume attached.
- 🔒 **Credential-Secured SMTP** – Uses Gmail’s SMTP server to send emails securely.

---

## 🗂️ Project Structure

```bash
.
├── CompanyWise HR contact.pdf                 # Input PDF file with HR emails
├── email_sender.ipynb                         # Main Python script
└── README.md                                  # Documentation (you are here)
```

---

## 🛠️ Requirements

Install required libraries using pip:

```bash
pip install PyPDF2
```

> This script uses the built-in `smtplib`, `os`, `re`, and `email` libraries, which require no additional installation.

---

## ⚙️ How It Works

1. **Text Extraction:**  
   Reads and extracts raw text from the input PDF using `PyPDF2`.

2. **Email Detection & Context Mining:**  
   Uses regular expressions to identify email addresses and analyze nearby text for:
   - **Name**
   - **Job Title**
   - **Company**

3. **Fallback Table Mode:**  
   If structured HR data is found in tabular format, attempts to parse it.

4. **Data Cleaning:**  
   Sanitizes names and companies, filling in missing information with smart defaults derived from the email domain or structure.

5. **Email Sending:**  
   Authenticates using SMTP (Gmail) and sends personalized emails with a resume attachment.

---

## 📧 Email Template

Each HR contact will receive:

```plaintext
Subject: Job Application for AI/ML Engineer Position at <Company>

Dear <Name>,

I am writing to express my interest in the AI/ML Engineer role at <Company>. ...
[Detailed self-introduction and technical qualifications]

Best regards,  
Tanuj Kaswa  
Mobile Number: +917385538010
```

---

## 🔐 Setup & Configuration

Edit the following variables inside the `main()` function before running:

```python
pdf_path = "CompanyWise HR contact (1).pdf"
resume_path = "your_resume.pdf"
sender_email = "your_email@gmail.com"
sender_password = "your_app_specific_password"
sender_name = "Your Name"
sender_mobile = "+91XXXXXXXXXX"
```

⚠️ **Important:** Use an [App Password](https://support.google.com/accounts/answer/185833?hl=en) if 2FA is enabled for your Gmail account.

---

## ▶️ Running the Script

Run the script via terminal or your preferred IDE:

```bash
python main.py
```

You'll be prompted to confirm before emails are sent:
```
Do you want to send emails to all X HR contacts? (yes/no):
```

---

## ✅ Sample Output

```plaintext
Extracted 7 HR contacts:
  - John Doe (HR Manager at ExampleCorp): john.doe@example.com
  ...
Do you want to send emails to all 7 HR contacts? (yes/no): yes
Email sent successfully to John Doe at ExampleCorp
...
Email sending complete. Successfully sent 7 out of 7 emails.
```

---

## 🔐 How to Get a Gmail App Password

Gmail blocks access to less secure apps, but with **App Passwords**, you can safely use your account with tools like this Python script.

### 📌 Requirements:
- 2-Step Verification (2FA) **must be enabled** on your Google Account.

### ✅ Steps to Generate an App Password

1. **Go to your Google Account settings:**  
   [https://myaccount.google.com/](https://myaccount.google.com/)

2. **Click "Security" in the left menu.**

3. Under **"Signing in to Google"** section:  
   - Enable **2-Step Verification**  
   - Click **App Passwords**

4. **Verify your login**, if prompted.

5. Under **"Select app"**, choose **"Mail"**.  
   Under **"Select device"**, choose **"Other (Custom name)"** and enter a name like `HR Email Script`.

6. Click **Generate**.

7. Copy the 16-character password and use it in your script:

   ```python
   sender_password = "abcd efgh ijkl mnop"  # No spaces in actual script
   ```

8. **Keep this password safe.** You won’t see it again!

---

## 🧠 Use Cases

- Mass job application email campaigns.
- Networking outreach automation.
- Extracting and cleaning HR contacts from job fairs or hiring expos.

---

## 📎 Future Improvements

- Add GUI for better usability.
- Use AI/NLP for better context extraction.
- Integrate with job portals or CRMs.
- Schedule email sending with delay/random intervals.

---

## ⚠️ Disclaimer

Use this tool responsibly. Always respect data privacy and avoid spamming. This tool is for educational and personal job search purposes.

---

## 🧑‍💻 Author

**Tanuj Kaswa**  
Email: tanujkaswa23@gmail.com  
GitHub: [YourGitHubProfile]
