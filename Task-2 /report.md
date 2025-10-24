
# 🕵️‍♂️ Phishing Email Analysis Walkthrough

This README documents a full phishing email analysis process using a public sample email.  
Each step follows the agenda below:

1. Obtain a sample phishing email  
2. Examine sender’s email address for spoofing  
3. Check email headers for discrepancies  
4. Identify suspicious links or attachments  
5. Look for urgent or threatening language  
6. Note any mismatched URLs  
7. Verify presence of spelling or grammar errors  
8. Summarize phishing traits found

---

# 🕵️‍♂️ Phishing Email Analysis Walkthrough

This README guides you through a hands-on phishing email analysis using a realistic public sample.  
Follow each documented step to practice detection and learn key traits.

---

## 📝 Sample Phishing Email

**From:** Microsoft Security Notifications `<alert@microsoft-support.com>`  
**To:** [you@example.com](mailto:you@example.com)  
**Subject:** [Action Required] Unusual sign-in activity detected on your Microsoft account

**Body:**
> Hello [Your Name],
>
> Our automated security systems detected unusual sign-in activity on your Microsoft 365 account from a new device or location.
>  
> For your protection, we've temporarily restricted your account. Please review the recent activity and confirm your identity to restore full access.  
>  
> [Review Recent Activity]  
>
> **Action required within 48 hours to avoid permanent account restriction.**  
>
> Learn how to keep your account safe at [Microsoft Security Tips]
>
> Sincerely,  
> Microsoft Account Protection Team

**Visible link:**  
`https://account.microsoft.com/recent-activity`  

**Actual link target:**  
`https://secure.microsoft-support.com/account-verification?id=6539821`  

**Attachment:**  
`Security_Notice.pdf` (malicious, do not open)

---

## 1️⃣ Sender Email Address (Spoofing Check)

- Display name: `Microsoft Security Notifications`
- Actual sender domain: `microsoft-support.com` *(not the true Microsoft domain!)*  
- Real organizations use official domains (e.g., `@microsoft.com`).

✅ **Red flag:** Spoofed email address, misleading display name.

---

## 2️⃣ Email Header Discrepancies

How to check:
- Open the email and locate "Show original" / "View headers" in your mail client.
- Copy the full header text.
- Paste into:
    - [MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)
    - [mailheader.org](https://mailheader.org)

Check for:
- `Received:` lines show routing via unrelated mail servers
- `Return-Path` ≠ `From` domain
- SPF/DKIM/DMARC failures and mismatch
- Sender IP location doesn't match official org

✅ **Red flag:** Authentication failures, routing inconsistencies.

---

## 3️⃣ Suspicious Links or Attachments

- **Shown URL:** `https://account.microsoft.com/recent-activity`
- **Actual URL:** `https://secure.microsoft-support.com/account-verification?id=6539821`
- **Attachment:** `Security_Notice.pdf` (potentially malicious!)

Checking tips:
- Hover links, never click—do real and shown addresses match?
- Use [VirusTotal](https://virustotal.com) or [URLVoid](https://www.urlvoid.com/) to scan suspicious domains and files.

✅ **Red flag:** Mismatched URL and malicious attachment.

---

## 4️⃣ Urgent or Threatening Language

Phrases include:
- “Unusual sign-in activity”
- “Temporarily restricted”
- “Action required within 48 hours”
- “Permanent account restriction”

✅ **Red flag:** Emotional pressure and urgency to act quickly.

---

## 5️⃣ Mismatched URLs

| Shown Text                                   | Real Destination                                                  |
|----------------------------------------------|-------------------------------------------------------------------|
| `https://account.microsoft.com/recent-activity` | `https://secure.microsoft-support.com/account-verification?id=6539821` |

✅ **Red flag:** Legitimate-looking text linked to a phishing page.

---

## 6️⃣ Spelling or Grammar Errors

- No obvious spelling mistakes (well-crafted attacks exist!).
- Slightly generic greeting ("Hello [Your Name]").
- Watch for awkward phrasing or formatting issues.

✅ **Note:** Not all phishing emails have errors—check tone and details.

---

## 7️⃣ Summary of Phishing Traits

| Trait              | Observation                                               | Status |
|--------------------|-----------------------------------------------------------|--------|
| Sender spoofing    | Display name and domain misleading                        | ⚠️     |
| Header issues      | SPF/DKIM/DMARC fail, server mismatches                    | ⚠️     |
| Mismatched URLs    | Visible vs destination domain mismatched                  | ⚠️     |
| Urgent tone        | Time pressure, threat of account loss                     | ⚠️     |
| Grammar issues     | Slightly generic, often present                           | ⚠️     |
| Attachments        | Unsolicited PDF, likely harmful                           | ⚠️     |

---

## 🧩 Overall Verdict

> This email is **highly likely to be a phishing attempt** intended to steal credentials and possibly infect with malware.  
> **Do not click** any links or open the attachment.  
> Report it to your IT/security team.

---

## 🛡️ Recommended Next Steps

1. **Report:** Use your email client’s *Report Phishing* feature.
2. **Verify:** Only log in via [https://account.microsoft.com](https://account.microsoft.com).
3. **Reset Password:** Change your Microsoft password if affected.
4. **Enable MFA:** Multi-factor authentication increases security.
5. **Educate Others:** Share these steps for cybersecurity awareness.

---

## 📚 Tools & References

- [MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)
- [mailheader.org](https://mailheader.org)
- [VirusTotal Link Scanner](https://www.virustotal.com)
- [Microsoft Phishing Protection Tips](https://www.microsoft.com/en-us/safety/online-privacy/phishing-symptoms)
- [NCSC UK - Phishing Guidance](https://www.ncsc.gov.uk/collection/phishing)

---

