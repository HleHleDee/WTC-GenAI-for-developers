
README and User Guide Documentation

**Prompt 1 Used :**
Prompt 1: Project README Generation


Please create a comprehensive README.md file for my project based on the following information:

Project name: Task Manager CLI

Description:
A simple command-line task manager built using Python. This application allows users to create, manage, and track tasks directly from the terminal. It includes features like task creation, updating task details, filtering tasks, and viewing statistics.

Key features:
- Create tasks with title, description, priority, due date, and tags
- List and filter tasks by status, priority, or overdue
- Update task status, priority, and due date
- Add and remove tags from tasks
- View task details
- Delete tasks
- View task statistics

Technologies used:
- Python 3
- argparse (for handling command-line arguments)
- datetime

The README should include: 
1. Clear project title and description 
2. Installation instructions 
3. Basic usage examples 
4. Features overview 
5. Configuration options 
6. Troubleshooting section 
7. Contributing guidelines 
8. License information Code structure overview: [Briefly describe main directories/files or paste project structure]

**Prompt 1 Response**

**README.md**

**Task Manager CLI**

Task Manager CLI is a simple command-line application built with Python that helps users create, manage, and track tasks from the terminal. It is designed to make task organization easier by allowing users to set priorities, due dates, statuses, and tags.

This project is useful for people who prefer working in the terminal instead of using a graphical task management app.

**Features**
Create new tasks
View all tasks
Filter tasks by status
Filter tasks by priority
View overdue tasks
Update task status
Update task priority
Update due dates
Add and remove tags
Delete tasks
View task details
View task statistics
Technologies Used
Python 3.11+
argparse
datetime
Python Standard Library

No external libraries are required.

**Installation Requirements**

Before running the project, make sure you have:

Python 3.11 or higher installed

You can check your Python version using:

python --version


Clone the Repository
git clone <repository-url>
cd task-manager

Since this project uses only Python standard libraries, no additional installation is needed.

**Basic Usage**

The application runs using the command line through cli.py.

Create a New Task
python cli.py create "Task Title" --description "Task description" --priority 2 --due "2024-01-31" --tags "work,urgent"
List All Tasks
python cli.py list

List Tasks by Status
python cli.py list --status todo

Available status options:

todo
in_progress
review
done
List Tasks by Priority
python cli.py list --priority 3

Priority levels:

1 = Low
2 = Medium
3 = High
4 = Urgent

**View Overdue Tasks**

python cli.py list --overdue
Update Task Status
python cli.py status <task_id> done
Update Task Priority
python cli.py priority <task_id> 4

**Update Due Date**
python cli.py due <task_id> "2024-02-15"
Add a Tag
python cli.py tag <task_id> "important"
Remove a Tag
python cli.py untag <task_id> "important"
Show Task Details
python cli.py show <task_id>

**Delete a Task**

python cli.py delete <task_id>
View Statistics
python cli.py stats

This command shows:

Total tasks
Tasks by status
Tasks by priority
Overdue tasks
Completed tasks in the last 7 days
Running Tests

This project uses Python’s built-in unittest framework.

**Basic Test Run**

python -m unittest discover tests
Verbose Test Run
python -m unittest discover -v tests
Troubleshooting
Python Command Not Found

Make sure Python is installed correctly and added to your system PATH.

Try:

python --version

Invalid Date Format

Make sure due dates are written in this format:

YYYY-MM-DD

Example:

2024-02-15
Task Not Found

Check that the task ID is correct before updating, deleting, or viewing a task.

**Contributing**

Contributions and improvements are welcome.

To contribute:

Fork the project
Create a new branch
Make your changes
Commit your work
Push your branch
Open a Pull Request

This project is for learning purposes and educational use as part of the WeThinkCode_ curriculum.

**Prompt 2**

Please create a step-by-step guide for how to create a task in our Task Manager CLI application.

The guide should:
1. Start with any prerequisites or required access
2. Break down the process into clear, numbered steps
3. Include code blocks where needed
4. Highlight potential issues or common mistakes
5. End with a troubleshooting section for common problems

Process overview:
The user needs to create a new task using the CLI. They must provide a task title and can optionally include a description, priority level (1–4), due date (YYYY-MM-DD), and tags (comma-separated). The command is executed in the terminal using Python.

User experience level: Beginner

**Prompt 2 response**

# How to Create a Task in Task Manager CLI

This guide shows how to create a new task using the Task Manager CLI.

---

## ✅ Prerequisites

Before you start, make sure:
- You have Python 3.11 or higher installed
- You have already downloaded or cloned the project
- You are inside the project folder in your terminal

---

## 🪜 Steps to Create a Task

### Step 1: Open your terminal
Open Command Prompt, PowerShell, or your terminal.

---

### Step 2: Navigate to the project folder
Use `cd` to go to your project directory:

```bash
cd task-manager

Step 3: Run the create command

Basic example:

python cli.py create "My First Task"

This will create a task with just a title.

Step 4: Add more details (optional)

You can also include more information like description, priority, due date, and tags:

python cli.py create "Finish assignment" -d "Complete README task" -p 3 -u "2024-02-10" -t "school,important"

What each option means:

-d → description 

-p → priority (1 = low, 4 = urgent) 

-u → due date (format: YYYY-MM-DD) 

-t → tags (separated by commas) 

Step 5: Check if the task was created

Run:

python cli.py list

You should see your task in the list.

 Common Mistakes

Forgetting to put the title in quotes
Wrong:

python cli.py create My Task

✔ Correct:

python cli.py create "My Task"

Using the wrong date format
Must be:

YYYY-MM-DD

Using a priority outside 1–4
Only values 1, 2, 3, or 4 are allowed 

 Troubleshooting

Task not showing

Run:

python cli.py list

Make sure the task was created successfully.

Error when running command

Check if Python is installed:

python --version

Make sure you are in the correct folder 


Error when running command

Check if Python is installed:

python --version

Make sure you are in the correct folder 

Invalid date error

Make sure your date looks like:

2024-02-10

✔ Summary

Use create to add a task 

You must include a title 

Other fields are optional but useful 

Always check with list after creating a task


**Prompt 3**

Please help me create a comprehensive FAQ document for a Task Manager CLI application.

Basic information:
- A simple Python command-line tool used to create and manage tasks
- Target audience: Beginner programmers (FNB App Academy / CS50 level)
- Focus on basic usage, commands, and common mistakes

Please include:
1. Questions about getting started
2. Questions about common features and functionality
3. Questions about troubleshooting common issues

For each question, provide a clear, simple answer.

Known issues or common user questions:
- How to create a task
- Why a task is not showing
- How to update a task
- What priority levels mean
- Errors when entering dates

**Prompt 3 Response**

# Task Manager CLI – FAQ

This FAQ answers common questions about using the Task Manager CLI.

---

## 🚀 Getting Started

### What is Task Manager CLI?
It is a simple command-line application built with Python that helps you create, manage, and track tasks using the terminal.

---

### How do I start using the application?
Open your terminal, go to the project folder, and run:

```bash
python cli.py

To see available commands:

python cli.py --help



What do I need before using it?

Python 3.11 or higher installed 

Basic knowledge of using the terminal 

The project files on your computer 

 Features and Usage

How do I create a task?

Use the create command:

python cli.py create "My Task"


You can also add more details:

python cli.py create "My Task" -d "Description" -p 2 -u "2024-02-10" -t "school,work"

How do I view my tasks?

Run:

python cli.py list
You can also filter:

python cli.py list --status todo
python cli.py list --priority 3

How do I update a task?

You can update different parts of a task:

Update status:

python cli.py status <task_id> done

Update priority:

python cli.py priority <task_id> 3

Update due date:

python cli.py due <task_id> "2024-02-15"


What do priority levels mean?

1 = Low 

2 = Medium 

3 = High 

4 = Urgent 

 Troubleshooting

Why is my task not showing?

Make sure you created the task successfully 

Run python cli.py list to check 

Check if filters are hiding your task 

Why am I getting an error with dates?

Make sure your date is in this format:

YYYY-MM-DD

Example:

2024-02-10

Why is my command not working?

Make sure you are inside the correct folder 

Check that Python is installed: 

python --version

What happens if I enter the wrong task ID?

The system will not find the task and will show an error message.
Make sure you copy the correct task ID from the list command.

✔ Tips

Always use quotes for task titles 

Double-check your command before running it 

Use --help if you forget a command








