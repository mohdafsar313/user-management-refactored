# CHANGES.md

## 📌 Overview

This document outlines the changes made to improve the original legacy User Management API in terms of **code structure, security, maintainability, and best practices**, as part of the Code Refactoring Challenge.

---

## 🔍 Major Issues Identified

1. Tightly coupled logic in one file (`app.py`)
2. SQL Injection vulnerabilities using f-strings
3. Plaintext passwords stored in DB
4. No input validation
5. No error handling or proper HTTP responses
6. Inconsistent JSON response formats
7. Lack of modular structure

---

## ✅ Changes Made

### 🧱 Project Structure

- Modularized into:
  - `app/` with `routes.py`, `services.py`, etc.
  - `app.py` now uses a Flask app factory
- Blueprints for routing

### 🔐 Security

- Parameterized queries to prevent SQL Injection
- Hashed passwords using `werkzeug.security`
- Secure password validation with `check_password_hash`

### 🛡 Input Validation & Error Handling

- Input checks for `name`, `email`, `password`
- Returned appropriate HTTP codes (200, 201, 400, 404)
- JSON error messages for invalid cases

### ♻️ Code Reuse

- Central DB connection function
- Separated business logic from routes

---


## 🤖 AI Tools Used

- **ChatGPT** for:
  - Designing file structure
  - Writing modular route + service code
  - Documenting `CHANGES.md`
- All code was reviewed and customized manually

---

## 📝 Summary

The application is now **secure, modular, maintainable**, and **returns consistent JSON responses**. Core functionality is preserved and tested via Postman.
