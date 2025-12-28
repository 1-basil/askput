# askput

**askput** is a simple yet powerful Python library for **safe, validated, and interactive console input**.

It helps developers avoid repetitive input-validation logic and build **clean CLI workflows** with minimal code.

---

## ✨ Why askput?

Python’s built-in `input()`:
- returns only strings
- has no validation
- leads to repetitive `try/except` blocks

**askput solves this cleanly.**

---

## 🚀 Features

- Safe integer and float input with bounds
- String length validation
- Email validation
- Secure password input
- Strong password rules
- Yes/No confirmations
- Phrase-based confirmation (dangerous actions)
- Choice / menu selection
- Pattern (regex) based input
- Multiple values input
- Fully tested with `pytest`
- Zero external dependencies

---

## 📦 Installation

```bash
pip install askput


from askput import ask

age = ask.int("Enter age", min=18)
price = ask.float("Enter price", min=0)
name = ask.string("Enter name", min_len=2)
email = ask.email("Enter email")

print(age, price, name, email)


from askput import ask

age = ask.int("Enter age", min=18)
price = ask.float("Enter price", min=0)
name = ask.string("Enter name", min_len=2)
email = ask.email("Enter email")

print(age, price, name, email)


password = ask.password("Enter password")
strong_password = ask.password_strong("Create strong password")

confirm = ask.confirm("Continue?")
delete = ask.confirm_phrase("Type DELETE to continue", "DELETE")


role = ask.choice(
    "Select role",
    ["Admin", "User", "Guest"]
)

print("Selected:", role)


code = ask.pattern("Enter code", r"^[A-Z]{3}\d{3}$")
tags = ask.multi("Enter tags (comma separated)")

print(code, tags)


from askput import ask

role = ask.choice("Role", ["Admin", "User"])
age = ask.int("Age", min=18)
password = ask.password_strong("Password")
confirm = ask.confirm("Submit form?")

if confirm:
    print("Form submitted")


askput is fully tested using pytest.

pytest


All tests must pass before every release.
