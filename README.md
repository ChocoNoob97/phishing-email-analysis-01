# phishing-email-analysis-01
First GH project worked with Copilot tackling incident thinking, communication clarity, security curiosity and structure under pressure. 

# Phishing Email Analysis – Case 01

This project documents my analysis of a simulated phishing email as part of my cybersecurity learning journey. The goal is to demonstrate incident-style thinking, clear communication, and the ability to break down technical findings into actionable guidance—skills essential for SOC and security support roles.

---

## 🧵 Summary

A suspicious email was reported by a user claiming their account was being locked. The message contained urgency, a fake Microsoft login link, and mismatched sender information. This analysis walks through the indicators of compromise (IOCs), header review, and recommended remediation steps.

---

## 🔍 Key Indicators of Phishing

### **1. Suspicious Sender Address**
- Display name: “Microsoft Account Security”
- Actual sender: `security-alerts@micros0ft-support.com`
- Domain uses a zero instead of an “o” → classic typosquatting

### **2. Urgency & Fear Tactics**
- Subject: “Your account will be locked in 24 hours”
- Body includes: “Immediate action required”

### **3. Malicious Link**
- Button text: “Verify Now”
- Hover URL: `http://login-microsoftauth.secure-verify-user.com`
- Domain does not belong to Microsoft

### **4. Generic Greeting**
- “Dear User” instead of the recipient’s name

---

## 📨 Email Header Review (Key Fields)

### **Return-Path**
`<security-alerts@micros0ft-support.com>`  
Does not match Microsoft’s legitimate domains.

### **Received From**
IP resolves to a hosting provider in another country, not Microsoft infrastructure.

### **SPF/DKIM/DMARC**
- SPF: Fail  
- DKIM: None  
- DMARC: Fail  

These failures strongly indicate spoofing.

---

## 🛡️ Recommended Actions

### **For the User**
- Do NOT click the link  
- Delete the email  
- Reset password if link was clicked  
- Enable MFA (if not already enabled)

### **For IT/Security**
- Search logs for clicks on the malicious domain  
- Check for unusual sign-in attempts  
- Review inbox rules for unauthorized forwarding  
- Block the sender domain at the email gateway  
- Add the domain to threat intel lists

---

## 🗂️ Timeline (Incident-Style)

| Time | Event |
|------|--------|
| 10:14 AM | User reports suspicious email |
| 10:17 AM | Initial triage completed |
| 10:20 AM | Header analysis performed |
| 10:25 AM | Malicious domain confirmed |
| 10:30 AM | User notified + remediation steps provided |
| 10:45 AM | Logs reviewed for related activity |

---

## 🧠 What I Learned

- How to identify typosquatting domains  
- How to interpret SPF/DKIM/DMARC results  
- How to structure an incident-style write-up  
- How to communicate findings clearly to non-technical users  

---

## 📚 Tools Used

- MXToolbox  
- VirusTotal  
- WHOIS lookup  
- Browser dev tools (URL inspection)  

---

## 🚀 Next Steps

I plan to add:
- Additional phishing case studies  
- A small script to extract header fields  
- A comparison of legitimate vs. spoofed Microsoft login pages  

