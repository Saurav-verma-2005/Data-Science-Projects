# CodeBook: Social Media Data Analysis (Pure Python)

## **Project Overview**
[cite_start]**CodeBook** is a social media platform for coders based in Delhi[cite: 1, 2]. [cite_start]As a Data Science Intern, I was tasked with analyzing user data dumps to build core platform features[cite: 3, 6]. 

[cite_start]The defining constraint of this project was to perform all data engineering and algorithm development using **Pure Python only**—strictly avoiding external libraries like Pandas or NumPy to demonstrate a deep understanding of Python's built-in data structures and algorithmic logic[cite: 5].

---

## **Key Features**

### **1. Data Cleaning & Pipeline**
[cite_start]Raw social media data is often "noisy"[cite: 96, 97]. This module implements:
* [cite_start]**Validation**: Removing records with missing critical fields, such as empty usernames[cite: 134, 140].
* [cite_start]**Deduplication**: Cleaning friend lists to ensure unique entries and deduplicating page registries by ID[cite: 135, 137, 141, 143].
* [cite_start]**Filtering**: Identifying and removing "inactive" users who have zero friends and zero liked pages[cite: 136, 142].

### **2. 'People You May Know' (Social Graph)**
[cite_start]A recommendation system that suggests potential friends based on **Mutual Connection logic**[cite: 201, 202]:
* [cite_start]Analyzes the 2nd-degree network of a user (friends of friends)[cite: 217, 235].
* [cite_start]Ranks suggestions by the number of shared mutual friends[cite: 207, 219].
* [cite_start]Higher mutual counts result in higher priority recommendations[cite: 207].

### **3. 'Pages You Might Like' (Collaborative Filtering)**
[cite_start]A content discovery engine that utilizes **User-Item Collaborative Filtering**[cite: 263, 279]:
* [cite_start]Identifies "similar users" who have liked the same pages[cite: 272, 286].
* [cite_start]Calculates a similarity score based on the intersection of interests[cite: 306, 328].
* [cite_start]Recommends new pages that similar users have engaged with but the target user has not yet discovered[cite: 274, 308].

---

## **Technical Implementation**
* [cite_start]**Language**: Python 3.x[cite: 5].
* [cite_start]**Data Format**: JSON (JavaScript Object Notation)[cite: 11].
* [cite_start]**Core Concepts**: Set Theory for intersections, Dictionary Mapping for efficient lookups, and Lambda functions for ranking[cite: 151, 157, 245, 311].

---

## **How to Run**
1. Ensure you have `raw_data.json` in the root directory.
2. Run the master notebook `Main_Project.ipynb`.
3. The script will generate a cleaned dataset and print recommendation lists for the sample users.

---

## **Future Enhancements**
* [cite_start]Implementing a **Flask-based API** to serve these recommendations to a frontend[cite: 257].
* Expanding the recommendation logic to include "interest-based" weights for specific categories of pages.
