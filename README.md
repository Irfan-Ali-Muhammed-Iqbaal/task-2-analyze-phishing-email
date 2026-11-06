# Task 2: Analyze a Phishing Email Sample

## 📝 What I Did
For this task, I analyzed a raw phishing email sample to identify indicators of compromise (IoCs) and social engineering tactics. I reviewed the email headers for authentication failures and examined the email body for spoofing, deceptive links, and psychological manipulation techniques.

## 🕵️‍♂️ Phishing Indicators Found (Analysis)
Upon analyzing the `phishing_sample.txt` file, I identified the following red flags:

1. **Sender Spoofing & Typosquatting:** The display name says "PayPal Security", but the actual email address is `security@paypa1-alert.com`. The attacker used a "1" instead of an "l" (typosquatting) to trick the eye.
2. **Header Discrepancies & SPF Failure:** The `Return-Path` (`bounce@fraudsters.net`) does not match the `From` address. Furthermore, the `Authentication-Results` show an `spf=fail`, meaning the server sending the email is not authorized by the domain owner.
3. **Urgent & Threatening Language:** The subject uses "URGENT:" and the body threatens that the account will be "permanently closed" within 24 hours. This creates artificial panic to force a quick, irrational reaction.
4. **Generic Greeting:** Instead of addressing me by my name, it uses a generic "Dear Customer," which is common in mass-phishing campaigns.
5. **Mismatched / Malicious URL:** The email instructs the user to click a link that visually attempts to look like PayPal. However, reading the URL structure (`http://www.paypal.com.secure-login-update.net/login`) reveals the true domain is actually `secure-login-update.net`, a completely unrelated and fraudulent site.
6. **Spelling/Grammar Inconsistencies:** The sign-off reads "Pay Pal" with an unnatural space, rather than the official "PayPal" branding.

---

## 🎤 Interview Questions & Answers

**1. What is phishing?**
Phishing is a type of social engineering attack where a malicious actor sends a fraudulent message designed to trick a person into revealing sensitive information, deploying malicious software, or transferring money.

**2. How to identify a phishing email?**
You can identify them by looking for generic greetings, a sense of unwarranted urgency or fear, spoofed or mismatched sender addresses, suspicious attachments, and embedded URLs that do not match the organization's official domain.

**3. What is email spoofing?**
Email spoofing is the forgery of an email header so that the message appears to have originated from someone or somewhere other than the actual source. Attackers use it to build false trust.

**4. Why are phishing emails dangerous?**
They bypass technical security perimeters by directly targeting human psychology. They can result in severe consequences like identity theft, financial loss, compromised corporate networks, and ransomware deployment.

**5. How can you verify the sender’s authenticity?**
You can verify authenticity by inspecting the raw email headers to check if SPF, DKIM, and DMARC authentication protocols passed. You should also manually verify the domain and contact the organization via their official, public phone number or website (without clicking email links).

**6. What tools can analyze email headers?**
Tools like Google Admin Toolbox Messageheader, MXToolBox Email Header Analyzer, or simply viewing the "Original Message" / "Raw Source" within an email client (like Outlook or Gmail) to manually parse the routing data.

**7. What actions should be taken on suspected phishing emails?**
Do not click any links, do not download attachments, and do not reply. Report the email using your email client's "Report Phishing" button, notify your IT/Security department if in a corporate environment, and then delete the email.

**8. How do attackers use social engineering in phishing?**
Attackers manipulate human emotions—primarily fear, urgency, greed, or curiosity. By threatening account closure or promising a fake reward, they trigger a panicked or impulsive response, causing the victim to bypass their normal critical thinking.
