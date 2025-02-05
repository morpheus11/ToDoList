# ToDoList
 DP-0303
 # 📩 Send Email Function - Help Guide

This function allows you to send emails with an **HTML signature** using **Google Apps Script (GAS)**. It supports **CC, BCC, attachments**, and **dynamic personal details**. 🚀

## 📜 Function Overview
The function signature is:
```javascript
sendEmail(recipient, subject, body, cc, bcc, attachments, phone, name, duty, company, email);

📌 Parameters
recipient 📧 - The primary email address of the recipient.
subject 📝 - The subject of the email.
body ✉️ - The main content of the email (plain text version).
cc 👥 - Carbon Copy (CC) recipients (optional).
bcc 🔒 - Blind Carbon Copy (BCC) recipients (optional).
attachments 📎 - Array of files to attach (optional).
phone 📞 - Sender's contact number.
name 👨‍✈️ - Sender's full name.
duty ⚓ - Sender's role (e.g., "Nautical Superintendent").
company 🏢 - Sender's company name.
email 📬 - Sender's email address.
 
🛠️ Example Usage
Use this function inside Google Apps Script:
function testSendEmail() {
    var recipient = "example@example.com";
    var subject = "Test Email with Signature";
    var body = "Hello, this is a test email.";
    var cc = "cc@example.com";
    var bcc = "bcc@example.com";
    var attachments = [DriveApp.getFileById("FILE_ID").getAs(MimeType.PDF)];

    var phone = "+7-900-1213053";
    var name = "Cpt. Oleg Falaleev";
    var duty = "Nautical Superintendent";
    var company = "BD-Shipsnavo GmbH & Co. Reederei KG";
    var email = "oleg.falaleev@shipsnavo.de";

    sendEmail(recipient, subject, body, cc, bcc, attachments, phone, name, duty, company, email);
}
📨 Email Signature
The function automatically includes this professional HTML signature at the end of each email:

🧑‍✈️ Sender's Name & Duty
🏢 Company Details
📞 Contact Information
📧 Sender's Email
🌍 Website Link
⚠️ Confidentiality Notice
🖼️ Three images as part of the signature

✅ Features
📧 Supports HTML email format.
📎 Allows attachments.
👥 Includes CC & BCC recipients.
🔄 Uses dynamic parameters for customization.
🎨 Automatically appends a professional email signature.

⚠️ Notes
Ensure that Google Apps Script has the necessary permissions to send emails.
The email signature must be in HTML format for proper rendering.
Attachments must be retrieved using DriveApp.getFileById("FILE_ID").

📞 Need Help?
If you have any questions, feel free to contact ${name} at ${email} 📩