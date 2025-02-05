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

function sendEmail(recipient, subject, body, cc, bcc, attachments, phone, name, duty, company, email) {
  var signature = `
    <div dir="ltr" class="gmail_signature" data-smartmail="gmail_signature">
      <div dir="ltr">
        <div>If you have further questions, do not hesitate to contact me.</div>
        <div>&nbsp;</div>
        <div>tkx, krgds</div>
        <div><b>${name}</b></div>
        <div>${duty}</div> 
        <div>++++</div>
        <div>
          <img src="https://ci3.googleusercontent.com/mail-sig/AIorK4zHOubpwHZAnLlKvuKTKeOqhTM_rrD8LHOL4YDl_3ylf5kFFBvBctxuJiMIRbxXLbR3FDLzDDoj0TBl" alt="Signature Image 1">
        </div>
        <div>
          <img src="https://ci3.googleusercontent.com/mail-sig/AIorK4x9FiC0E__4uDwtQazPtvCJtivV8PWCZQg_i7sqZ4BJtKHelOJ8KkQ09NZnhPnKc_baigJBJBP2keJi" width="80" height="64" alt="Signature Image 2">
        </div>
        <div>${company}</div>
        <div>as agent to owners</div>
        <div>⚓️Marktwinkel 17</div>
        <div>49733 Haren/Ems</div>
        <div>Germany</div>
        <div><br></div>
        <div>Ph: ${phone}</div>
        <div>Email: <a href="mailto:${email}">${email}</a></div>
        <div><a href="http://www.shipsnavo.de" target="_blank">www.shipsnavo.de</a></div>
        <div><br></div>
        <div>AG Osnabrück HR A 120669</div>
        <div>Komplementär: Dopp Verwaltungs GmbH</div>
        <div>AG Osnabrück HR B 122548, GF: B.Dopp, C.Dopp, P.Dopp</div>
        <div><br></div>
        <div>We are <a href="https://sites.google.com/shipsnavo.de/bds-nm-iso/home" target="_blank">ISO 9001:2015</a> certified by RINA Services S.p.A.</div>
        <div><br></div>
        <div><b>CONFIDENTIALITY NOTICE:</b></div>
        <div>This email is intended for the named addressee only. It contains information which may be privileged, confidential, or subject to copyright and/or to the EU GDPR (see our 
        <a href="https://sites.google.com/shipsnavo.de/data-protection-notice-bdsn/home" target="_blank">Data Protection Notice</a>). 
        If you have received it in error, please notify the sender immediately.</div>
        <div>
          <img src="https://ci3.googleusercontent.com/mail-sig/AIorK4zQwMgynpd2HJ8VdoVDz2dJMmcKCqxhUZN5LrAtvObhe14j_NhabEICJPdHonKpXjpuVSZZaYR7FfH-" width="92" height="32" alt="Signature Image 3">
        </div>
      </div>
    </div>
  `;

  var htmlBody = body + "<br><br>" + signature;

  var options = {
    cc: cc || "",
    bcc: bcc || "",
    attachments: attachments || [],
    htmlBody: htmlBody
  };

  MailApp.sendEmail({
    to: recipient,
    subject: subject,
    body: body,
    htmlBody: htmlBody,
    cc: options.cc,
    bcc: options.bcc,
    attachments: options.attachments
  });
}

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
