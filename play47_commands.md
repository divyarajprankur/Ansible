# 🔐 Ansible Vault Complete Commands Cheat Sheet

## 🔒 Encrypt / Decrypt Files

ansible-vault encrypt file.yml
ansible-vault decrypt file.yml

## 👀 View / Edit Encrypted Files

ansible-vault view file.yml
ansible-vault edit file.yml

## 🔄 Change Vault Password

ansible-vault rekey file.yml

## ➕ Encrypt Single String

ansible-vault encrypt_string 'mypassword' --name 'db_password'

## 📄 Encrypt into New File

ansible-vault encrypt plain.yml --output encrypted.yml

## 📄 Decrypt into New File

ansible-vault decrypt encrypted.yml --output plain.yml

---

## 🔐 Using Vault Password (Runtime)

### Prompt for password

ansible-playbook play.yml --ask-vault-pass

### Use password file

ansible-vault encrypt file.yml --vault-password-file pass.txt
ansible-playbook play.yml --vault-password-file pass.txt

---

## 🧠 Vault ID Usage

### Encrypt using vault-id

ansible-vault encrypt file.yml --vault-id dev@prompt

### Encrypt string with vault-id

ansible-vault encrypt_string 'mypassword' --name 'db_password' --vault-id dev@prompt

### Run playbook with vault-id

ansible-playbook play.yml --vault-id dev@prompt

### Use vault-id with password file

ansible-playbook play.yml --vault-id [dev@dev-pass.txt](mailto:dev@dev-pass.txt)

### Multiple vault IDs

ansible-playbook play.yml 
--vault-id [dev@dev-pass.txt](mailto:dev@dev-pass.txt) 
--vault-id [prod@prod-pass.txt](mailto:prod@prod-pass.txt)

---

## 🧪 Validate Vault File

ansible-vault view file.yml

---

## 🚀 Typical Workflow

ansible-vault encrypt secrets.yml
ansible-playbook site.yml --ask-vault-pass

---

## ⚠️ Best Practices

* Never commit plain secrets
* Store password files securely
* Add password files to .gitignore
* Use vault-id for environment separation
* Rotate secrets using rekey

---

## 🎯 Quick Summary

Encrypt file → ansible-vault encrypt
Decrypt file → ansible-vault decrypt
Edit securely → ansible-vault edit
View → ansible-vault view
Change password → ansible-vault rekey
Encrypt value → encrypt_string

---

