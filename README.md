# testrep

##Editing this file

#This is a markdown file!

# task5

import os

project = ("OpenTrack", "1.0", 2026, "Python", "Ky")

print("=" * 42)
print(f"   {project[0]} — Open Source Project")
print(f"   Project Lead : {project[4]}")
print("=" * 42)

print(f"Name : {project[0]}  |  Version : {project[1]}  |  Started : {project[2]}")

print(f"First 3 fields : {project[:3]}")

print(f"Language count : {project.count('Python')}  Language index : {project.index('Python')}")
# project[0] = "Test"
# TypeError: tuple does not support item assignment
# Description: Tuples have the immutable property, meaning they cannot be changed once created,
# making them suitable for protecting data that needs to be fixed, such as project names or start years.
print("-" * 42)

contributors = []

for i in range(4):
    print(f"\nEnter contributor {i+1}")
    name = input("Name: ")
    role = input("Role: ")
    language = input("Language: ")
    commits = int(input("Commits: "))
    country = input("Country: ")

    contributors.append({
        "name": name,
        "role": role,
        "language": language,
        "commits": commits,
        "country": country
    })

names = [c["name"] for c in contributors]
names.sort()

print(f"Sorted names : {names}")
print(f"Last name : {names[-1]}   First two : {names[:2]}")

for c in contributors:
    c.update({"status": "Active"})

print(f"Contributor 1 status : {contributors[0].get('status')}")

backup = contributors[0].copy()
print(f"Backup : {backup}")

issues = []

for i in range(5):
    print(f"\nEnter issue {i+1}")
    id_ = input("ID: ")
    title = input("Title: ")
    type_ = input("Type (Bug/Feature): ")
    priority = input("Priority: ")
    reporter = input("Reporter: ")
    status = input("Status: ")

    issues.append({
        "id": id_,
        "title": title,
        "type": type_,
        "priority": priority,
        "reporter": reporter,
        "status": status
    })

open_count = 0
for i in issues:
    if i["status"] == "Open":
        open_count += 1

print(f"Open issues : {open_count}")

issues[0]["priority"] = "Critical"
print("First issue → priority updated to Critical.")

print(f"Last two issues : {issues[-2:]}")

print("-" * 42)

# Set
reporters = set()
tech_stack = set()

for i in issues:
    reporters.add(i["reporter"])

for c in contributors:
    tech_stack.add(c["language"])

tech_stack.add("Go")
tech_stack.discard("C++")

print(f"reporters : {reporters}")
print(f"tech_stack : {tech_stack}")
print(f"union : {reporters.union(tech_stack)}")
print(f"intersection : {reporters.intersection(tech_stack)}")
print(f"difference : {reporters.difference(tech_stack)}")

priority_set = set(i["priority"] for i in issues)

if "Critical" in priority_set:
    print("Critical present : YES")
else:
    print("Critical present : NO")

print("-" * 42)

priority_count = {}
for i in issues:
    p = i["priority"]
    if p in priority_count:
        priority_count[p] += 1
    else:
        priority_count[p] = 1

print(f"priority keys : {priority_count.keys()}")
print(f"priority values : {priority_count.values()}")

status_groups = {}
for i in issues:
    s = i["status"]
    if s not in status_groups:
        status_groups[s] = []
    status_groups[s].append(i["title"])

for k, v in status_groups.items():
    print(f"{k} : {v}")

report_count = {}
for i in issues:
    r = i["reporter"]
    if r in report_count:
        report_count[r] += 1
    else:
        report_count[r] = 1

top_reporter = ""
max_count = 0

for k, v in report_count.items():
    if v > max_count:
        max_count = v
        top_reporter = k

print(f"Top reporter : {top_reporter} ({max_count} issues)")

issues[0].pop("type")
print(f"After pop : {issues[0]}")

folder_name = project[0].lower().replace(" ", "_")

if not os.path.exists(folder_name):
    os.mkdir(folder_name)

print(f"Folder created : {folder_name}/")

report_path = os.path.join(folder_name, "project_report.txt")
csv_path = os.path.join(folder_name, "issues.csv")

try:
    with open(report_path, "w") as f:
        f.write("PROJECT REPORT\n")
        f.write(str(project) + "\n")
        f.write(str(contributors) + "\n")
        f.write(str(issues) + "\n")

    with open(csv_path, "w") as f:
        f.write("id,title,priority,reporter,status\n")
        for i in issues:
            f.write(f"{i['id']},{i['title']},{i['priority']},{i['reporter']},{i['status']}\n")

except IOError:
    print("Write error")

try:
    with open(report_path, "r") as f:
        print(f.read())

    with open(report_path, "r") as f:
        print(f.readline())
        print(f.readline())

    with open(report_path, "r") as f:
        lines = f.readlines()
        print(f"Total lines : {len(lines)}")

        for line in lines:
            if "Critical" in line or "High" in line:
                print(line.strip())

except FileNotFoundError:
    print("File not found")

print("=" * 42)
print(f"{project[0]} FINAL SUMMARY")
print("=" * 42)

print(f"Project : {project[0]} Version : {project[1]}")
print(f"Contributors : {len(contributors)} Names : {names}")
print(f"Issues : {len(issues)} Open : {open_count}")
print(f"Top Reporter : {top_reporter} ({max_count})")
print(f"Report : {report_path}")
print(f"CSV : {csv_path}")

urgent = [i["title"] for i in issues if i["priority"] in ("Critical", "High")]

print(f"Urgent issues : {urgent}")
print(f"Count : {len(urgent)}")

with open(report_path, "a") as f:
    f.write("\nURGENT ISSUES\n")
    for u in urgent:
        f.write(u + "\n")

with open(report_path, "r") as f:
    lines = f.readlines()
    for line in lines[-6:]:
        print(line.strip())


