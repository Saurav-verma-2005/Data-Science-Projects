# CodeBook: Social Media Data Analysis (Pure Python)

## **Project Overview**
**CodeBook** is a social media platform for coders. As a Data Scientist Intern, I was tasked with analyzing user data dumps to build core platform features. 

The defining constraint of this project was to perform all data engineering and algorithm development using **Pure Python only**—strictly avoiding external libraries like Pandas or NumPy to demonstrate a deep understanding of Python's built-in data structures and algorithmic logic.

---

## **Key Features**

### **1. Data Cleaning & Pipeline**
Raw social media data is often "noisy." This module implements:
* **Validation**: Removing records with missing critical fields (e.g., empty usernames).
* **Deduplication**: Cleaning friend lists and page registries to ensure data integrity.
* **Filtering**: Identifying and removing "inactive" users (those with zero friends and zero liked pages) to optimize analysis.

### **2. 'People You May Know' (Social Graph)**
A recommendation system that suggests potential friends based on **Mutual Connection logic**:
* Analyzes the 2nd-degree network of a user.
* Ranks suggestions by the number of shared mutual friends.
* Higher mutual counts result in higher priority recommendations.

### **3. 'Pages You Might Like' (Collaborative Filtering)**
A content discovery engine that utilizes **User-Item Collaborative Filtering**:
* Identifies "similar users" who have liked the same pages.
* Calculates a similarity score based on the intersection of interests.
* Recommends new pages that similar users have engaged with but the target user has not yet discovered.

---

## **Technical Implementation**
* **Language**: Python 3.x
* **Data Format**: JSON (JavaScript Object Notation)
* **Core Concepts**: Set Theory (for intersections), Dictionary Mapping (for O(1) lookups), and Lambda sorting.

---

## **How to Run**
1. Ensure you have `raw_data.json` in the data directory.
2. Run the master notebook `Main_Project.ipynb`.
3. The script will generate `cleaned_data.json` and print recommendation lists for the sample users.

---

## **Future Enhancements**
* Implementing a **Flask-based API** to serve these recommendations to a frontend.
* Expanding the recommendation logic to include "interest-based" weights for specific categories of pages.
