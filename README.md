# What I Learned - Data Engineering Basics & Snowflake

## Introduction

Hi!

These are my notes after learning Data Engineering basics and Snowflake. I wanted to write everything in my own words so I can revise it later and also show what I understood during my learning journey.

I also built a small Hotel Booking project to practice these concepts.

---

# What is Data Engineering?

From what I understood, Data Engineering is about collecting data, cleaning it, storing it properly and making it ready for analysis.

A Data Engineer builds data pipelines so that analysts and data scientists can use clean and reliable data.

---

# Data Pipeline

A data pipeline is simply the journey of data.

Example:

Raw Data
↓

Cleaning
↓

Transformation
↓

Store Data
↓

Reports / Dashboard

The goal is to move data from one place to another in the correct format.

---

# ETL and ELT

ETL means

Extract
Transform
Load

The data is cleaned before loading.

ELT means

Extract
Load
Transform

The data is loaded first and then cleaned inside the data warehouse.

Snowflake mainly follows ELT.

---

# What is Snowflake?

Snowflake is a cloud data warehouse.

It helps us store large amounts of data and analyze it quickly.

One thing I liked is that storage and compute are separate, so we can increase compute power whenever needed without affecting storage.

---

# Snowflake Objects

The basic hierarchy is

Database

↓

Schema

↓

Table

Database stores everything.

Schema helps organize related objects.

Tables store the data.

---

# Warehouse

Warehouse is the compute engine of Snowflake.

It does all the work like running queries, loading data and processing data.

Without a running warehouse, queries cannot execute.

---

# File Format

Before loading a file, Snowflake needs to know how to read it.

A File Format tells Snowflake things like

- CSV or JSON
- Delimiter
- Header
- Null values

---

# Stage

A Stage is a temporary place where files are stored before loading them into tables.

Flow:

File

↓

Stage

↓

Table

---

# COPY INTO

COPY INTO is used to load data from a Stage into a table.

It is one of the most common commands used for loading data.

---

# Bronze, Silver and Gold Layers

This was one of my favourite concepts.

Bronze Layer

Stores raw data exactly as it is.

Silver Layer

Data is cleaned and transformed.

Gold Layer

Contains final business-ready data which can be used in dashboards.

---

# Structured and Semi-Structured Data

Structured Data

Data stored in rows and columns.

Example

CSV

Semi-Structured Data

Data like JSON and Parquet.

Snowflake can read both types of data.

---

# Snowpipe

Snowpipe is used to automatically load new files into Snowflake.

Instead of running COPY INTO manually every time, Snowpipe does it automatically whenever a new file arrives.

---

# Streams

Streams keep track of changes made to a table.

They help us process only the new or changed data instead of reading the whole table again.

---

# Tasks

Tasks are used to automate SQL queries.

They can run on a schedule or after another task finishes.

This is useful for building automated data pipelines.

---

# Time Travel

Time Travel allows us to see old versions of data.

It also helps recover accidentally deleted tables or records.

This is one of the coolest features in Snowflake.

---

# Fail-safe

Fail-safe is an extra recovery period after Time Travel ends.

It is mainly used by Snowflake for disaster recovery.

---

# Zero Copy Clone

Zero Copy Clone creates a copy of a table or database without copying the actual data.

It saves storage and is very fast.

---

# Types of Tables

Permanent Table

Stores data normally.

Supports Time Travel and Fail-safe.

Transient Table

No Fail-safe.

Less storage cost.

Temporary Table

Exists only during the current session.

Gets deleted automatically after the session ends.

---

# Data Sharing

Snowflake allows data sharing without copying the data.

The Provider shares data.

The Consumer reads the data.

Only metadata is shared, not the actual data.

---

# Access Management

Snowflake uses Role-Based Access Control (RBAC).

The flow is

User

↓

Role

↓

Privileges

↓

Object

This makes permission management simple and secure.

---

# Hotel Booking Project

To practice these concepts, I built a Hotel Booking Analysis project.

The project uses:

- Bronze Layer for raw data
- Silver Layer for cleaned data
- Gold Layer for reporting
- Data validation
- Data cleaning
- SQL transformations
- Business reports

Working on this project helped me understand how data flows in a real pipeline.

---

# What I Learned

- How data moves through a pipeline.
- Difference between ETL and ELT.
- Basics of Snowflake architecture.
- Loading data using Stage and COPY INTO.
- Cleaning data using SQL.
- Working with Bronze, Silver and Gold layers.
- Understanding Snowpipe, Streams and Tasks.
- Recovering data using Time Travel.
- Managing users and roles using RBAC.
- Building a simple end-to-end data engineering project.

---
