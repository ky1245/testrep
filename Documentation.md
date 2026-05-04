# Documentation

## Overview

This project simulates an open source project management system.
It manages project information, contributors, and issues, and generates reports.

---

## Module: Project Initialization

### Description

Initializes project metadata using a tuple and prints basic project information.

### Key Features

* Uses tuple to store fixed project data
* Demonstrates immutability of tuples
* Accesses elements using indexing and slicing

### Variables

* `project` (tuple): Contains project name, version, start year, language, and lead

---

## Module: Contributor Management

### Description

Collects contributor information and stores it in a list of dictionaries.

### Input Data

* Name
* Role
* Language
* Commits
* Country

### Key Operations

* Store contributors in a list
* Extract and sort contributor names
* Add new field (`status = Active`)
* Copy contributor data (backup)

### Output Example

* Sorted contributor names
* Contributor status
* Backup of first contributor

---

## Module: Issue Management

### Description

Handles issue tracking including creation, counting, and updates.

### Input Data

* ID
* Title
* Type
* Priority
* Reporter
* Status

### Key Operations

* Count open issues
* Update issue priority
* Slice list (last two issues)
* Remove key (`pop`)

---

## Module: Set Operations

### Description

Uses sets to manage unique reporters and tech stack.

### Key Operations

* Add/remove elements
* Union, intersection, difference
* Check existence (e.g., "Critical")

### Variables

* `reporters` (set)
* `tech_stack` (set)

---

## Module: Data Analysis

### Description

Analyzes issue data using dictionaries.

### Key Operations

* Count issues by priority
* Group issues by status
* Find top reporter

### Data Structures

* `priority_count` (dict)
* `status_groups` (dict)
* `report_count` (dict)

---

## Module: File Handling

### Description

Creates project folder and writes reports to files.

### Files Created

* `project_report.txt`
* `issues.csv`

### Key Operations

* Write project, contributor, and issue data
* Read full file / line-by-line
* Count lines
* Filter important lines (Critical, High)

---

## Module: Final Summary

### Description

Displays overall project statistics.

### Output Includes

* Total contributors
* Total issues
* Open issues count
* Top reporter
* File paths

---

## Module: Urgent Issue Extraction

### Description

Extracts high-priority issues (Critical, High) and appends them to report.

### Key Operations

* List comprehension
* File append mode
* Print last lines of report

---

##  Notes

* This project was created as an individual assignment.
* It demonstrates Python data structures such as tuple, list, dictionary, and set.
* File handling and basic data analysis are included.
