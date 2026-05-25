# 📝 Automatic Multiple-Choice Exam Management & Generation System (IT003)

This is a course project for **IT003**, a web application designed to manage multiple-choice question banks and automatically generate, shuffle, and export exam sets in bulk.

## 🌟 Key Features

* **Multiple Input Formats**
  Supports importing question banks from various file types:

  * `.json`
  * `.xlsx` (Excel)
  * `.docx` (Word documents with intelligent Regex-based parsing)

* **Centralized Data Management with MongoDB**

  * Stores all questions in a centralized database
  * Supports both:

    * **Overwrite mode** (replace existing data)
    * **Append mode** (add new questions)
  * Automatically detects and removes duplicate questions based on content similarity

* **Automatic Exam Shuffling Algorithm**

  * Generates multiple exam versions from a single question bank
  * Uses the **Fisher-Yates Shuffle Algorithm** to randomize question order
  * Randomly shuffles answer choices (A, B, C, D) for each question

* **Fast Exporting**

  * Exports generated exams as Word documents (`.docx`)
  * Automatically compresses all exam versions into a single `.zip` file for download

* **Modern User Interface**

  * Frontend built with Tailwind CSS
  * Supports asynchronous file uploads (AJAX) without page reloads

---

# 🛠 Technologies Used

### Backend

* Python
* Flask (RESTful API)

### Database

* MongoDB

### File Processing

* `python-docx` (Word import/export)
* `pandas` (Excel processing)
* `zipfile`
* `io`

### Frontend

* HTML5
* Vanilla JavaScript
* Tailwind CSS (via CDN)

---

# 🚀 Installation & Setup Guide

## 1. System Requirements

* **Python 3.8+**
* **MongoDB** installed and running

  * Local installation or
  * MongoDB Atlas cloud service

---

## 2. Create Virtual Environment & Install Dependencies

Open Terminal/Command Prompt in the project directory and run:

```bash
# Create a virtual environment (optional but recommended)
python -m venv venv

# Activate the virtual environment

# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate

# Install required libraries
pip install flask pymongo python-docx pandas openpyxl python-dotenv
```

---

# 3. Database Configuration

The application uses a `.env` file to manage environment variables.

Make sure the project root directory contains a `.env` file with MongoDB configuration settings.

> A default `.env` file is already included in the project.
> You may modify the MongoDB URI if necessary.

---

# 4. Run the Application

Start the backend server:

```bash
python backend.py
```

Once the server starts successfully, open your browser and access:

```text
http://127.0.0.1:5000
```

(or the corresponding port displayed in the terminal).

---

# 📁 Main Project Structure

* `backend.py`

  * Contains the Flask server source code and API endpoints (Upload, Generate, etc.)

* `database.py`

  * Handles direct interaction with MongoDB (CRUD operations and duplicate prevention)

* `questions.py`

  * Defines the `Question` class
  * Handles reading/parsing files (`JSON`, `DOCX`, `XLSX`)
  * Implements exam shuffling algorithms (`mix_questions`)
  * Generates DOCX exam files

* `index.html`

  * User interface of the application

* `.env`

  * Environment configuration file

* `Bao_Cao_Do_An.md`

  * Detailed project report

---

# 👤 Author

* Nguyen Hoang Tuan

---

> **Note:**
> If the input Word file cannot be parsed correctly, ensure the question format follows the expected structure with clearly defined answer choices (A, B, C, and D).
