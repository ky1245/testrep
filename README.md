# OpenTrack - Open Source Project Simulator

## Overview

OpenTrack is a Python-based project that simulates a simple open source project management system.
It allows users to manage contributors, track issues, analyze data, and generate reports.

This project was developed as an individual assignment to practice core programming concepts.

---

## Features

### 1. Project Information

* Stores project metadata using a tuple
* Demonstrates tuple immutability
* Displays project details

### 2. Contributor Management

* Collects contributor information from user input
* Stores data using a list of dictionaries
* Sorts contributor names
* Adds status information dynamically

### 3. Issue Tracking System

* Allows users to input issue data
* Tracks issue status (Open, Closed, etc.)
* Updates issue priority
* Counts open issues

### 4. Data Analysis

* Counts issues by priority
* Groups issues by status
* Identifies top reporter

### 5. Set Operations

* Extracts unique reporters and tech stack
* Performs union, intersection, and difference operations

### 6. File Handling

* Automatically creates a project folder
* Generates:

  * `project_report.txt`
  * `issues.csv`
* Supports file read/write operations

### 7. Urgent Issue Detection

* Filters high-priority issues (Critical, High)
* Appends them to the report file

---

## Tech Stack

* Language: Python 3
* Libraries: os (built-in)

---

## How to Run

1. Clone the repository

```id="cl1"
git clone <your-repo-url>
```

2. Move to the project directory

```id="cl2"
cd opentrack
```

3. Run the program

```id="cl3"
python main.py
```

---

## Project Structure

```id="cl4"
project/
 ├── main.py
 ├── README.md
 ├── DOCUMENTATION.md
 └── opentrack/
      ├── project_report.txt
      └── issues.csv
```

---

## Example Workflow

1. Enter contributor information
2. Enter issue details
3. Program processes data
4. Reports and CSV files are generated
5. Summary is displayed

---

## Key Concepts Used

* Tuple (immutable data)
* List & List Comprehension
* Dictionary & Nested Data
* Set Operations
* File I/O
* Exception Handling

---

## Future Improvements

* Add GUI interface
* Store data using a database
* Improve input validation
* Add search and filtering features

---

## 📌 Notes

* This project was created as an individual assignment.
* Some features are simplified for learning purposes.
