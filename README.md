# 📊 NSQF Excel Generator — NIELIT Ropar

<img src="img/logo.png" width="200">

![Version](https://img.shields.io/badge/version-3.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Environment](https://img.shields.io/badge/environment-Client--Side-orange.svg)

A client-side web application designed to automate the generation of official examination documents for National Skills Qualifications Framework (NSQF) courses at **NIELIT Ropar** (National Institute of Electronics & Information Technology). 

---

## 💡 What are we doing?

The **NSQF Excel Generator** is a streamlined, 4-step web tool that takes a raw "RO" (Registration/Roll-out) Excel file containing student data and automatically formats it into standardized, ready-to-print examination files. 

For every institute found in the uploaded data, the tool generates three specific Excel workbooks:
1. **Attendance Sheets** (Separated into Theory, Practical, and Typing tests depending on the course scheme).
2. **Internal Assessment Templates** (For logging internal marks).
3. **Compiled Result (HQ) Sheets** (A master sheet for final score compilation).

## 🤔 Why did we build this?

Preparing examination documentation for NSQF courses manually is incredibly tedious and prone to human error. Administrators typically have to copy-paste student names, roll numbers, and registration details from a master database into multiple different templates. 

**The core problems this solves:**
* **Time Consumption:** Manually separating students by institute and formatting their details into different sheets takes hours. This tool does it in seconds.
* **Format Consistency:** Ensures every attendance sheet and result sheet strictly follows the formatting required by NIELIT HQ.
* **Data Privacy & Security:** Educational data is highly sensitive. Because this application relies entirely on client-side JavaScript (using the user's browser), **no student data is ever uploaded to a server**. Everything is processed locally on the user's machine.

---

## ✨ Key Features

* **🛡️ 100% Local Processing:** Uses `FileReader` and SheetJS to read and write Excel files directly in the browser. Zero server uploads.
* **🏫 Multi-Institute Handling:** Automatically detects if a master Excel file contains students from multiple institutes/venues and generates a separate batch of files for each one.
* **📚 12 Pre-Configured Courses:** Fully supports 12 NSQF courses (e.g., *Essentials of AI*, *Full Stack Development*, *Data Entry*). It automatically knows the exam scheme (e.g., 2 Theory + 1 Practical vs. 1 Theory + 1 Practical + Typing) and adjusts the generated sheets accordingly.
* **⚡ Smart Auto-Fill:** Automatically extracts exam dates, practical dates, and batch timings from the uploaded RO file to save manual data entry.
* **🌗 Modern UI/UX:** Features a responsive design, drag-and-drop file uploading, an intuitive 4-step wizard, and a Light/Dark mode toggle.

---

## 🚀 How to Use (The 4-Step Workflow)

### Step 1: Select NSQF Course
Click on the specific course you are generating files for. The system will load the respective course codes, duration (e.g., 120 Hrs, 360 Hrs), and examination scheme requirements in the background.

### Step 2: Upload RO Data File
Drag and drop your raw `.xlsx` or `.xls` RO file into the drop zone. The app will immediately parse the file, identify the number of students, split them by their respective institutes, and show a preview table of the extracted data.

### Step 3: Configure Details
Verify the examination schedule. The app will attempt to auto-fill these fields from your Excel file:
* Exam Cycle (e.g., March 2026)
* Theory & Practical Exam Dates/Times
* Regional Centre Name & TP (Training Partner) Codes.
*(Note: If multiple institutes are detected, you will be prompted to enter a specific TP Code for each).*

### Step 4: Generate & Download
Review the generation summary. Click the **"⚡ Generate All Excel Files"** button. The app will compile the data and trigger an automatic download of the completed `.xlsx` files straight to your computer's `Downloads` folder.

---

## 🛠️ Technical Stack

This project is built to be as lightweight and portable as possible. It requires no backend, no databases, and no complex build steps.

* **Frontend Structure:** HTML5
* **Styling:** Vanilla CSS (Custom UI with CSS Variables, Flexbox, and CSS Grid)
* **Logic:** Vanilla JavaScript (ES6)
* **Excel Processing Library:** [SheetJS (xlsx.full.min.js)](https://sheetjs.com/) - Used for parsing the uploaded `.xlsx` files and constructing the new workbooks from arrays of arrays (`aoa_to_sheet`).
* **Fonts:** Google Fonts (*Outfit* for UI text, *DM Mono* for tabular data).

---

## 📦 Installation & Setup

Because this is a static, client-side application, installation is virtually zero.

1. Clone or download this repository.
2. Ensure you have the `index.html` file and the `img/logo.png` in their respective directories.
3. Simply double-click `index.html` to open it in any modern web browser (Chrome, Edge, Firefox, Safari).
4. *Requires an active internet connection only upon first load to fetch the Google Fonts and the SheetJS CDN.*

---

## 📂 Generated File Structure

When you hit generate, the application utilizes the following naming conventions for the downloaded files:

* `{CourseCode}_Attendance_{InstituteName}_{Cycle}.xlsx`
* `{CourseCode}_Internal_Assessment_{InstituteName}_{Cycle}.xlsx`
* `{CourseCode}_Compiled_Result_HQ_{InstituteName}.xlsx`

## 👨‍💻 Maintainers

Developed for **NIELIT Ropar** (National Institute of Electronics and Information Technology) to streamline administrative workflows for NSQF examinations.
