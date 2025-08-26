# Software Requirements Specification (SRS) for Campaign Management System

---

## Table of Contents
1. [Introduction](#1-introduction)
2. [Overall Description](#2-overall-description)
3. [System Features](#3-system-features)
4. [External Interface Requirements](#4-external-interface-requirements)
5. [System Attributes](#5-system-attributes)
6. [Other Non-Functional Requirements](#6-other-non-functional-requirements)
7. [System Architecture](#7-system-architecture)
8. [Development and Testing Plan](#8-development-and-testing-plan)
9. [Roles and Responsibilities](#9-roles-and-responsibilities)
10. [Appendix](#10-appendix)

---

## 1. Introduction

### a) Purpose
This document provides a comprehensive Software Requirements Specification (SRS) for the Campaign Management System. It outlines all the functional and non-functional requirements that the system must meet, and it serves as a contract between the stakeholders and the development team. The purpose of the system is to allow developers to input campaign details and generate a ZIP file containing the assets of the campaign.

---

### b) Scope
The Campaign Management System will allow users to input campaign details including the campaign ID, language, type, asset type, client logo, title, subtitle, and abstract. Upon submission, the system will validate the inputs and generate a ZIP file containing all relevant assets. The system is designed for use by developers who manage campaigns and by testers who verify the functionality of the system.

---

### c) Definitions, Acronyms, and Abbreviations
- **EDM:** Electronic Direct Mail
- **ZIP:** A compressed file format used for storing multiple files
- **WYSIWYG:** What You See Is What You Get (HTML text editor)

---

### d) References
- W3C HTML5 specification: Provides standards for web development.
- MySQL documentation: Official documentation for MySQL database management system.
- Bootstrap framework: Front-end framework for building responsive web applications.

---

### e) Overview
The SRS document is structured into several sections:
- Section 1: Provides an overall description of the system, including the product features, environment, and constraints.
- Section 2: Details the system’s functional requirements.
- Section 3: Outlines the external interface requirements.
- Section 4: Defines the system attributes and non-functional requirements.
- Section 5: Provides system architecture details.
- Section 6: Describes the development and testing plan.
- Section 7: Lists roles and responsibilities.

---

## 2. Overall Description

### a) Product Perspective
The Campaign Management System is a web-based application that allows developers to input campaign-related data and generates a downloadable ZIP file containing all assets. The system should be modular, allowing for future updates to the campaign types, assets, or input formats.

---

### b) Product Features
- **Form Inputs:** Provides fields for entering the campaign ID, language, campaign type, asset type, logo, title, subtitle, and abstract.
- **ZIP File Generation:** After form submission, the system generates a ZIP file containing all the necessary campaign files (e.g., whitepapers, images, and abstract).
- **WYSIWYG Editor:** Allows developers to enter campaign abstracts with rich text formatting.
- **Data Validation:** Ensures all form fields are correctly filled with valid data.

---

### c) User Classes and Characteristics
- **Developers:** Responsible for entering the data into the system and generating the ZIP file.
- **Testers:** Responsible for validating the functionality of the system, ensuring that inputs are correctly validated and the ZIP file is generated without errors.

---

### d) Operating Environment
The Campaign Management System is a web-based application and should be accessible from any modern browser (Chrome, Firefox, Edge, Safari). The system must be compatible with both desktop and mobile devices. The server must support PHP and MySQL.

---

### e) Design and Implementation Constraints
- The system should be built using PHP, MySQL, and Bootstrap.
- The system must generate ZIP files using PHP’s ZipArchive class.
- The WYSIWYG editor must support rich text formatting such as bold, italics, and the insertion of images and links.
- The application must be designed for scalability and efficiency.

---

### f) Assumptions and Dependencies
- Users will have access to modern web browsers.
- The system assumes that all data input is valid unless specified otherwise (e.g., no malformed URLs or missing mandatory fields).

---

## 3. System Features

### a) Campaign ID Entry
- **Action:** The developer enters a new campaign ID.
- **Input Type:** Alphanumeric string.
- **Validation:** Ensures the ID follows a specific format (e.g., GovExec-EN-1).
- **Next Step:** The system will proceed to language selection.

---

### b) Language Selection
- **Action:** The developer selects the campaign language.
- **Input Type:** Dropdown list.
- **Validation:** Ensures a valid language is selected.
- **Next Step:** The system will proceed to campaign type selection.

---

### c) Campaign Type Selection
- **Action:** The developer selects the campaign type.
- **Input Type:** Dropdown list.
- **Validation:** Ensures a valid campaign type is selected.
- **Next Step:** The system will proceed to asset type selection.

---

### d) Asset Type Selection
- **Action:** The developer selects the asset type.
- **Input Type:** Dropdown list.
- **Validation:** Ensures a valid asset type is selected.
- **Next Step:** The system will proceed to logo name entry.

---

### e) Client Logo Name Entry
- **Action:** The developer enters the logo file name.
- **Input Type:** Text field.
- **Validation:** Ensures the logo name follows the correct format (e.g., GovExec-white-logo.png).
- **Next Step:** The system will proceed to campaign title entry.

---

### f) Campaign Title Entry
- **Action:** The developer enters the campaign title.
- **Input Type:** Text field.
- **Validation:** Ensures the title is not empty.
- **Next Step:** The system will proceed to campaign subtitle entry.

---

### g) Campaign Subtitle Entry
- **Action:** The developer enters the campaign subtitle.
- **Input Type:** Text field.
- **Next Step:** The system will proceed to abstract entry.

---

### h) Abstract Entry (HTML Text Editor)
- **Action:** The developer enters the campaign abstract using the WYSIWYG editor.
- **Input Type:** HTML text editor (e.g., CKEditor or TinyMCE).
- **Validation:** Ensures the abstract is entered and not empty.
- **Next Step:** The system will proceed to the final submission.

---

### i) Submission and ZIP Generation
- **Action:** The developer submits the form to generate the ZIP file.
- **ZIP Generation:** The system will create a ZIP file containing all campaign-related files.
- **Download:** The developer will be provided a download link for the ZIP file.

---

## 4. External Interface Requirements

### a) User Interfaces
- The system will present a web-based interface accessible from any modern browser.
- The system will feature a user-friendly interface with clearly labeled form fields.

---

### b) Hardware Interfaces
- The system requires no specific hardware interfaces.

---

### c) Software Interfaces
- The system will interface with the MySQL database to store campaign-related data.
- The system will integrate with PHP’s ZipArchive class for file compression.

---

### d) Communications Interfaces
- The system will use HTTPS for secure communication between the client and the server.

---

## 5. System Attributes

### a) Usability
- The system will have a simple, easy-to-use interface with clearly labeled fields and tooltips.

---

### b) Performance
- The system should load within 3 seconds.
- ZIP file generation should be completed in less than 10 seconds.

---

### c) Security
- All user inputs will be validated and sanitized.
- Sensitive data, such as logos and assets, will be securely stored.

---

### d) Reliability
- The system should have an uptime of 99.9%.

---

### e) Maintainability
- The system should be easily maintainable and scalable for future updates.

---

### f) Portability
- The system should be compatible with all modern web browsers.

---

## 6. Other Non-Functional Requirements

### a) Compatibility
- The system must support Chrome, Firefox, Edge, and Safari.

---

## 7. System Architecture

### a) Technologies Used
- Backend: PHP for server-side logic.
- Frontend: HTML5, CSS3, and Bootstrap for responsive design.
- Database: MySQL for storing campaign data.
- File Handling: PHP's ZipArchive for ZIP file creation.
- HTML Editor: CKEditor or TinyMCE for WYSIWYG functionality.

---

### b) Database Design (MySQL)
- **Tables:**
  - `campaigns`: Stores campaign-related data (e.g., ID, title, language).
  - `assets`: Stores associated assets (e.g., logos, PDFs).

---

### c) Front-End Design (Bootstrap)
- The frontend will use Bootstrap for responsive layout and form elements.

---

## 8. Development and Testing Plan

### a) Development Tasks
- Day 1: Set up repository, implement database schema.
- Day 2-3: Develop backend logic, input validation.
- Day 4: Integrate WYSIWYG editor.
- Day 5-6: Implement ZIP generation functionality.
- Day 7: Conduct internal testing.
- Day 8: Final testing and deployment.

---

### b) Testing Tasks
- Unit Testing: Validate individual form fields.
- Integration Testing: Test all system components working together.
- UAT: Ensure the system meets user expectations and is user-friendly.

---

### c) Timeline (8-Day Plan)
- As outlined above.

---

## 9. Roles and Responsibilities

### a) Developer Roles
- Frontend and backend development.
- Database integration.
- Implement ZIP file functionality.

---

### b) Testing Team Roles
- Perform unit and integration testing.
- Test performance and security.

---

## 10. Appendix

### a) Glossary
- **Campaign ID:** A unique identifier for campaigns.
- **ZIP File:** A compressed archive containing campaign files.
- **WYSIWYG:** A rich text editor for formatting content.