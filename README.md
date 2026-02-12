Overview

MEDIQ is a Python-based intelligent emergency medical scheduling system designed to prioritize patients in hospital emergency departments using an efficient data structure and a multi-factor scoring algorithm.

The system uses a Binomial Heap to dynamically manage patient priorities based on medical urgency, age, waiting time, and special needs. It ensures that critical patients receive immediate attention while maintaining fairness across all cases.

Problem Statement

Traditional first-come-first-served scheduling systems in emergency departments fail to account for:

Medical severity

Patient vulnerability (age and special needs)

Waiting time

Resource optimization

This can lead to delays for critical patients and inefficient healthcare delivery.

Objectives

Implement a Binomial Heap for efficient patient priority management

Generate a synthetic dataset of 10,000 realistic patient records

Design a multi-factor priority scoring algorithm

Ensure fairness using structured tie-breaking mechanisms

Demonstrate scalable performance for large datasets

System Architecture

The system consists of:

Synthetic Data Generator

Multi-Factor Priority Scoring Algorithm

Binomial Heap Implementation

Priority Extraction Engine

Optional Web Interface for hospital staff (HTML-based)

Dataset Generation

A synthetic dataset of 10,000 patient records was generated with the following attributes:

Patient ID (P001 – P10000)

Severity Level (Normal, Urgent, Emergency, Critical)

Waiting Time (5–120 minutes)

Age (1–100 years)

Special Needs / Insurance (Yes/No)

Appointment Time (September 2025, 8 AM – 10 PM)

Doctor ID (1–20)

Data was stored in CSV format for structured processing.

Advantages:

No privacy concerns

Controlled testing environment

Realistic distribution of severity levels

Priority Scoring Algorithm

Each patient receives a composite score based on multiple factors:

Severity Weight

Emergency: 100 points

Critical: 50 points

Urgent: 20 points

Normal: 0 points

Age Factor

Seniors (60+): age / 5

Children (<12): 10 points

Adults (12–59): age / 10

Priority Order:
Senior > Child > Adult

Special Needs Bonus

+10 points

Waiting Time Bonus

0.6 × waiting time (minutes)

Tie-Breaking Rules

If multiple patients have equal priority scores, the system resolves ties in the following order:

Severity

Special Needs

Check-in Time

Age (children and seniors prioritized)

Appointment ID

Binomial Heap Implementation

Key operations implemented:

Insert

Extract Max

Union

Tree Linking

Root List Merging

Why Binomial Heap?

Amortized O(1) insertion

O(log n) extraction

Efficient heap merging

Suitable for dynamic priority queues

Methodologies and Python Concepts Used

Object-Oriented Programming (custom classes for heap nodes and heap structure)

Advanced Data Structures (Binomial Heap)

CSV File Handling using Pandas

Random data generation

Datetime handling

Conditional logic for priority scoring and tie-breaking

Results and Validation

Successfully processed 10,000 patient records

Correct priority extraction order observed

Emergency cases with long waiting times served first

Special consideration applied for children and seniors

Sub-second insertion and extraction performance

Manual validation of first 24 extractions confirmed correctness

Technologies Used

Python

Pandas

Random

Datetime

HTML (for basic web interface)
