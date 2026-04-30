# Using AI To Help With Testing

Understanding What to Test

Exercise 1.1 — Behavior Analysis

**Prompt Used**

I'm learning how to test this function, and I want to understand what behaviors I should test.

Here is the function:

[calculate_task_score(task)]

Rather than generating tests for me, please:
1. Ask me questions about what I think this function does
2. After I answer, help identify any behaviors I missed
3. Ask me what edge cases I think should be tested
4. Help me identify additional edge cases I didn't think of
5. Ask me which test I should write first and why



**Prompt response**

**Understanding What to Test**
 
Function Under Test
calculate_task_score(task)

This function calculates a score for a task based on:

priority level
due date
status
tags
last update time


What I Understand the Function Does

This function gives each task a number (score).
Higher score = more important task.

It checks:

Priority (Low → Urgent)
Due date (overdue or soon due = higher score)
Status (DONE reduces score, REVIEW slightly reduces)
Tags like “critical” or “urgent” increase score
Recently updated tasks get a small boost

 **Test Cases I Identified**

Here are the main behaviors I think should be tested:

1. Priority affects score
Urgent tasks should have higher score than low priority
2. Overdue tasks increase score
Tasks past due date should get a big boost
3. Due today tasks
Should increase score moderately
4. DONE tasks reduce score
Completed tasks should have lower score
5. Critical tags increase score
Tasks with "critical", "blocker", or "urgent" should get boost
6. Recently updated tasks get boost
If updated today, score increases

**Edge Cases I Noticed**
Task with no due date
Task with empty tags
Task updated exactly 1 day ago
Task with unknown priority value

Function Under Test
calculate_task_score(task)

This function calculates a score for a task based on:

priority level
due date
status
tags
last update time

**What I Understand the Function Does**

This function gives each task a number (score).
Higher score = more important task.

It checks:

Priority (Low → Urgent)
Due date (overdue or soon due = higher score)
Status (DONE reduces score, REVIEW slightly reduces)
Tags like “critical” or “urgent” increase score
Recently updated tasks get a small boost

**Test Cases I Identified**

Here are the main behaviors I think should be tested:

1. Priority affects score
Urgent tasks should have higher score than low priority
2. Overdue tasks increase score
Tasks past due date should get a big boost
3. Due today tasks
Should increase score moderately
4. DONE tasks reduce score
Completed tasks should have lower score
5. Critical tags increase score
Tasks with "critical", "blocker", or "urgent" should get boost
6. Recently updated tasks get boost
If updated today, score increases

**Edge Cases I Noticed**
Task with no due date
Task with empty tags
Task updated exactly 1 day ago
Task with unknown priority value

**Unit Testing (Improved Tests)**

Test File: test_task_scoring.py
import unittest
from datetime import datetime, timedelta

from models import TaskStatus, TaskPriority
from task_scoring import calculate_task_score


class Task:
    def __init__(self, priority, status, due_date=None, tags=None, updated_at=None):
        self.priority = priority
        self.status = status
        self.due_date = due_date
        self.tags = tags or []
        self.updated_at = updated_at or datetime.now()


class TestTaskScoring(unittest.TestCase):

    def test_priority_increases_score(self):
        task = Task(TaskPriority.URGENT, TaskStatus.TODO)
        self.assertGreater(calculate_task_score(task), 0)

def test_overdue_task_boost(self):
        task = Task(
            TaskPriority.MEDIUM,
            TaskStatus.TODO,
            due_date=datetime.now() - timedelta(days=2)
        )
        self.assertGreater(calculate_task_score(task), 30)

    def test_due_today_task(self):
        task = Task(
            TaskPriority.MEDIUM,
            TaskStatus.TODO,
            due_date=datetime.now()
        )
        self.assertIsInstance(calculate_task_score(task), int)

    def test_done_task_reduces_score(self):
        task = Task(TaskPriority.HIGH, TaskStatus.DONE)
        self.assertLess(calculate_task_score(task), 0)

    def test_tag_boost(self):
        task = Task(
            TaskPriority.MEDIUM,
            TaskStatus.TODO,
            tags=["critical"]
        )
        self.assertGreater(calculate_task_score(task), 10)


def test_recent_update_boost(self):
        task = Task(
            TaskPriority.MEDIUM,
            TaskStatus.TODO,
            updated_at=datetime.now()
        )
        self.assertIsInstance(calculate_task_score(task), int)


if __name__ == "__main__":
    unittest.main()

**Test Improvement Reflection**

**What I Learned About Testing**

This exercise helped me understand that testing is not just checking if code runs, but checking different behaviours of a function.

I learned:

Each condition in a function should have its own test
Edge cases are very important (like overdue or empty values)
Tests should check behaviour, not implementation
Small test cases make debugging easier

Difficult Parts
Understanding how date calculations affect scores
Thinking of edge cases (like no due date or unknown priority)
Knowing what to assert (exact value vs greater/less than)

**How AI Helped**

AI helped me:

Break the function into testable behaviours
Identify missing edge cases
Structure tests properly
Understand what each part of the function does

**How I Would Improve This in Future** 
Write tests before writing functions (TDD)
Add more edge cases
Use clearer assertions (exact expected values when possible)
Test real-world scenarios (full task workflows)
how

**Final Summary**

This exercise taught me to:

analyse a function
identify behaviours to test
write structured unit tests
think about edge cases
improve testing using AI guidance