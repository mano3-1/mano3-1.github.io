---
title: Interview Experience for Data Scientist 1 Role | Swiggy
tags: [Interview archives]
style: fill
color: secondary
comments: true
description: This explains my interview experience for data scientist role at Swiggy in detail.
---

# Introduction

I am Sai Manoj Akondi, a Machine Learning Engineer at Tiger Analytics with close to three years of experience in developing and deploying AI-powered solutions. My expertise lies in building production-ready Agentic RAG-based applications to automate business workflows. I have a strong foundation in LLMs, including fine-tuning, optimization, and deployment on cloud platforms like Azure and AWS.

In my current role, I have led the development of various LLM-based systems, including RAG-based chatbots, automated story generation for Jira, and predictive analytics models. I have hands-on experience in writing and deploying APIs for LLM applications, integrating them with scalable cloud infrastructure. Previously, as a Data Scientist, I worked on NLP-focused projects such as fine-tuning transformers for text classification and summarization.

Beyond NLP, I have a deep understanding of deep learning frameworks like PyTorch and TensorFlow.

Coming to my academic qualifications, I got graduated from NIT Calicut where I have worked extensively on computer vision projects. My research work at NIT Calicut involved developing a novel object detection method for cervical cancer detection, which was published in an SCI journal. I also worked on contrastive learning techniques for cleaning medical image datasets, contributing to another SCI publication.

With a strong technical background, cloud expertise, and a research-oriented mindset, I am passionate about building AI-driven solutions that drive real business impact.

# Round 1 - Coding round

## Guessing Game

**Question:** Guess the output of the following code snippet

```python
sample = "Swiggy"

def function(sample):
    sample += " Swiggy India"
    print("Inside Function:", sample)

function(sample)
print("Outside Function:", sample)
```

**Hint:**

Call by value

**Answer:** 

Inside Function: Swiggy Swiggy India
Outside Function: Swiggy

**Question:** Guess the output of the following code snippet

```
sample = ["Swiggy"]

def function(sample):
    sample += ["Swiggy India"]
    print("Inside Function:", sample)

function(sample)
print("Outside Function:", sample)
```

**Hint:**

Call by reference

**Answer:** 

Inside Function: ['Swiggy', 'Swiggy India']
Outside Function: ['Swiggy', 'Swiggy India']

## Python concepts

**Question:** What is a list comprehension? Explain with an example

**Answer:** 

List comprehension is a compact way to create a new list by applying an operation to each item in an existing iterable (like a list, string, range, etc.) — all in a single line of code.

It makes the code shorter, readable, and faster compared to writing a traditional for loop.

```python
l = [0,1,2,3,4]
l = [_**2 for _ in l]
```

**Question:** What are generators? Write a generator to print even numbers

**Answer:** Generators are special functions that return an iterator but don't store all the values in memory at once.

✅ They save memory

✅ They are faster when you're working with large datasets

```python
def even_numbers(n):
    for i in range(1, n+1):
        yield 2*i

for _ in even_numbers(10):
    print(_)
```

**Question:** Have you ever used multi processing and multi threading? What is the difference between multi processing and multi threading?

**Answers:**

Yes, I have used both in Python when I needed to speed up tasks.

- I used multithreading when my program was I/O-bound — like waiting for API responses, reading files, or downloading data.
- I used multiprocessing when my program was CPU-bound — like heavy computations, model training, data processing.

| Multiprocessing | Multithreading |
| --- | --- |
| Multiple processes with separate memory spaces | Multiple threads within the same process sharing memory |
| Best for CPU-bound tasks (heavy computation) | Best for I/O-bound tasks (waiting for input/output) |
| Each process runs independently; crashing one doesn’t affect others | Threads are linked; if one thread crashes, it can affect others |
| Higher memory consumption | Lower memory consumption |
| Uses multiple CPU cores | Limited by **GIL** (Global Interpreter Lock) in Python |

## SQL

**Question:**

You are given a table `de_earnings` with the following columns:

- `de_id` (delivery executive id)
- `date` (date of earnings)
- `order_id` (order id)
- `earnings` (earnings for that order)

Example data:

| de_id | date | order_id | earnings |
| --- | --- | --- | --- |
| 1 | 28-Mar | 1 | 100 |
| 1 | 28-Mar | 2 | 120 |
| 2 | 28-Mar | 3 | 140 |
| 2 | 29-Mar | 4 | 200 |

Write an SQL query to find the order_ids having maximum earnings for each `de_id` for each date.

Expected Output:

| de_id | date | order_id |
| --- | --- | --- |
| 1 | 28-Mar | 2 |
| 2 | 28-Mar | 3 |
| 2 | 29-Mar | 4 |

**Answer:**

```sql

WITH ranked_items AS (
    SELECT de_id, date, DENSE_RANK() OVER (PARTITION BY de_id, date ORDER_BY earnings DESC) as rn
    FROM de_earnings
)

SELECT order_id, de_id, date, rn FROM ranked_items WHERE rn=1
```

## Pandas

**Data:**

```python
import pandas as pd
sales_data = pd.DataFrame({'month': ['Jan', 'Jan', 'Feb', 'Feb', 'Feb'],
                           'product': ['A', 'B', 'A', 'B', 'C'],
                           'sales': [100, 200, 150, 250, 180]})

sales_data.head()
```

**Question:**

Given a DataFrame sales_data containing columns 'month', 'product', and 'sales'. calculate the total sales revenue for each product across all months.

**Answer:**

```python
sales_data.groupby("product").agg({"sales": sum})
```

**Data:**

```python
orders = pd.DataFrame({'order_id': [1, 2, 3, 4],
                       'customer_id': ['A', 'B', 'C', 'D']})

customers = pd.DataFrame({'customer_id': ['A', 'B', 'C', 'E'],
                          'location': ['New York', 'Chicago', 'Boston', 'Los Angeles']})

print(orders)
print(customers)
```

**Question**

Suppose you have two DataFrames, orders and customers, representing orders and customer information respectively. Get the orders placed by customers in 'New York' city.

**Answer**

```python
all_data = pd.merge(orders, customers, how="left", on=["customer_id"])
all_data[all_data.location=="New York"]
```

## Python Problem

**Question:**

Given an array of points where points[i] = [xi, yi] represents a point on the X-Y plane and an integer k, return the k closest points to the origin (0, 0).

The distance between two points on the X-Y plane is the Euclidean distance.

You may return the answer in any order. The answer is guaranteed to be unique (except for the order that it is in).

Example

Input: points = [[1,3],[-2,2]], k = 1

Output: [[-2,2]]

**Answer:**

```python
def distance(x,y):
    return (x**2+y**2)**0.5

def get_top_k(l, k):
    distances = [distance(*_) for _ in l]
    results = sorted(zip(l, distances), key=lambda x: x[-1])[:k]
    return [_[0] for _ in results]

get_top_k([[1,3],[-2,2], [4,5]], 2)
```

## ML/DL Concepts

**Question:** Explain the optimization problem of Linear regression, write equations for parameter updation

**Answer:**

```

Y = W*X + b
C = sigma((y_hat_i-y_i)**2)/N
min C w.r.t W,B

dC/DW, DC/db

w = w-lr*dc/DW
b = b-lr*dc/DB

dc/DW = 2*(y_hat_i-y_i)*X
dc/DB = 2*(y_hat_i-y_i)*1
```

# Round 2 - ML Depth + Breadth

1. What is lightGBM model?
2. Why did you use lightGBM for jira bug prediction, why not a neural network?
3. What is bias-variance trade off?
4. What is boosting vs bagging?
5. Comment on bias, variance of boosting and bagging
6. Which is better: bagging or boosting?
7. What is overfitting? How do you combat it?
8. How does L1, L2 losses help with overfitting? How does L1 exhibits feature selection, while L2 doesn’t?
9. Do you remember the graphs for L1, L2?
10. You have a model A and model B trained in different regions, How can you test and compare them without needing to shuffle them?
11. What is A/B testing?
12. What are learning rate schedulers? 
13. When a model reached saturation, if you cannot tweak architecture and data, what else can you tweak/tune to push it further?

# Round 3 - ML Problem Solving

**Question:**

To predict ETA for a delivery in insta mart. (The interview wants me to engineer the features required for the same)

**My answer:**

1. Average time taken by the delivery partner for delivering in that area on week day/weekend - low
2. Average ETA in last couple of hours - 0
3. Number of deliveries that are registered in the past in that hour -
4. Distance between the delivery address and nearest warehouse - real time
5. Distance of delivery agent from the warehouse
6. Time taken for packing based on weight

**His explanation**

(collected it post my interview)

ETA is heavily dependent on stress experienced by system

Stress on the system can be from three sources:

1. Stress at delivery center
2. Stress at the app
3. Stress from the delivery agent

# Round 4 - HM Round

This round is to check if I am culturally and behaviorally fit

- The interviewer asked about my journey till that point. I explained how ended up my AI jobs and stuff being from mechanical
- Is there any instance where you were frustrated with your employee and how did you handle it?
- Is there any instance where you got really bad feedback and how did you handle it?
- Do you like to work in teams or are you a solo player?
- Why swiggy?