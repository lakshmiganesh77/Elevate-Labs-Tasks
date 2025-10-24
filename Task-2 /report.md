
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

## 1️⃣ Sample Phishing Email

**From:** Microsoft Support `<support@verify-account.xyz>`  
**To:** you@example.com  
**Subject:** Urgent: Verify your Microsoft 365 account or it will be suspended  

**Body:**
> Dear Customer,  
> We detected suspicious activity in your Microsoft account.  
> To prevent suspension, please verify your account immediately by clicking the link below and completing verification within 24 hours:  
> [Verify your account]  
>  
> Thank you,  
> Microsoft Account Team

**Visible link:** `https://account.microsoft.com/verify`  
**Actual link target:** `http://secure-microsoft.verify-account.xyz/confirm?id=12345`  
**Attachment:** None

---

## 2️⃣ Sender Email Address (Spoofing Check)

- Display name: `Microsoft Support`  
- Actual domain: `verify-account.xyz`  
- **Domain mismatch** → Display name spoofing likely.  
- Real organizations send from official domains (e.g. `@microsoft.com`).

✅ **Red flag:** Spoofed sender address.

---

## 3️⃣ Email Header Discrepancies

How to check:
```bash
# Copy full email headers and paste into an analyzer like:
- MxToolbox Email Header Analyzer
- mailheader.org
- Sendmarc Header Analyzer
```

Common signs:
- `Received:` chain shows unrelated mail servers  
- `Return-Path` ≠ `From` domain  
- SPF/DKIM/DMARC fail or mismatch  
- Duplicate / malformed header lines

✅ **Red flag:** Authentication failures and non-Microsoft servers in the header chain.

---

## 4️⃣ Suspicious Links or Attachments

- Visible URL: `https://account.microsoft.com/verify`  
- Actual URL: `http://secure-microsoft.verify-account.xyz/...`  
- Domain mismatch and fake security subdomain.

How to check safely:
- **Never click.** Hover to reveal the real URL.  
- Use tools like VirusTotal or URLVoid to scan it.

✅ **Red flag:** Phishing link targeting credential theft.

---

## 5️⃣ Urgent or Threatening Language

Found phrases:
> “Verify your account immediately”  
> “Within 24 hours”  
> “Will be suspended”

These create panic to make users act fast.

✅ **Red flag:** Emotional pressure / urgency.

---

## 6️⃣ Mismatched URLs

Example:

| Shown Text | Actual Destination |
|-------------|--------------------|
| `https://account.microsoft.com/verify` | `http://secure-microsoft.verify-account.xyz/confirm?id=12345` |

✅ **Red flag:** Mismatch between visible and real URLs.

---

## 7️⃣ Spelling or Grammar Errors

- No major mistakes here, but many phishing emails contain subtle grammar issues or generic greetings (“Dear Customer”).  
- Even well-written messages can still be fake.

✅ **Note:** Check tone, formatting, and greeting consistency.

---

## 8️⃣ Summary of Phishing Traits

| Trait | Observation | Status |
|-------|--------------|--------|
| Sender spoofing | Display name ≠ domain | ⚠️ |
| Header issues | SPF/DKIM mismatch | ⚠️ |
| Mismatched URLs | Hidden phishing link | ⚠️ |
| Urgent tone | “Verify within 24 hours” | ⚠️ |
| Grammar issues | Minor / generic greeting | ⚠️ |
| Attachments | None | ✅ |

---

## 🧩 Overall Verdict

> This email is **highly likely to be a phishing attempt.**  
> Do **not click** any links or reply. Report it to your organization’s IT or security team.

---

## 🛡️ Recommended Next Steps

1. **Report:** Mark the email as *Phishing* in your email client.  
2. **Verify:** Log into your Microsoft account directly at [https://account.microsoft.com](https://account.microsoft.com).  
3. **Reset Password:** If you clicked or entered credentials, change your password immediately.  
4. **Enable MFA:** Turn on multi-factor authentication (MFA) for added security.  
5. **Educate:** Share this example for team security awareness.

---

## 📚 Tools & References

- [MxToolbox Email Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)  
- [mailheader.org](https://mailheader.org)  
- [VirusTotal Link Scanner](https://www.virustotal.com)  
- [Microsoft Phishing Protection Tips](https://www.microsoft.com/en-us/safety/online-privacy/phishing-symptoms)  
- [Keepnet Labs Phishing Email Header Example](https://keepnetlabs.com/phishing-email-header-anatomy-example)  

---

