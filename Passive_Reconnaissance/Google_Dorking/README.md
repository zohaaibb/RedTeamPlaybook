# 🔍 Google Dorking

## 📌 What is Google Dorking?

Google Dorking (also known as Google Hacking) is the technique of using advanced Google search operators to uncover sensitive data unintentionally exposed online. This includes files, credentials, directories, login pages, and more.

These queries rely on indexing done by Google, so no interaction with the target server is needed—making it a powerful passive reconnaissance method.

---

## 🔧 Why Use Google Dorks?

- To find hidden or exposed files (e.g., PDFs, DOCs, config files)
- To locate login panels or admin interfaces
- To uncover vulnerable web applications
- To discover internal documents or directory listings
- To gather information without touching the target server

---

## 🔍 Common Google Dork Operators

| Operator       | Description                                   |
|----------------|-----------------------------------------------|
| `site:`        | Search within a specific domain               |
| `filetype:`    | Search for specific file types                |
| `intitle:`     | Match text in the page title                  |
| `inurl:`       | Match text in the URL                         |
| `intext:`      | Match text in the body of the page            |
| `link:`        | Pages that link to a specific site            |

---

## 💻 Example Dorks


# Find PDF files on a site
site:example.com filetype:pdf

# Discover exposed login pages
inurl:login site:example.com

# View open directories
intitle:"index of" site:example.com

# Find configuration files
ext:xml OR ext:conf OR ext:cnf OR ext:ini site:example.com

# Search for SQL errors
intext:"sql syntax near" OR "unexpected end of SQL command"

## 🧠 What is the Google Hacking Database (GHDB)?

The **Google Hacking Database (GHDB)** is a project by Offensive Security that collects **pre-built, powerful Google Dorks** categorized by purpose. It's an essential tool for anyone doing reconnaissance or vulnerability discovery using search engines.

You can explore GHDB here:  
🔗 [Google Hacking Database - Exploit-DB](https://www.exploit-db.com/google-hacking-database)

### GHDB Categories:
- Files containing passwords
- Sensitive directories
- Vulnerable servers
- Login pages
- Error messages
- SQL errors

⚠️ Note
Google Dorking is powerful and completely legal only if used ethically. Do not attempt to exploit or access any data without proper authorization. This technique should be used for awareness, bug bounty, or authorized assessments.

