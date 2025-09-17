### **Conflict Resolution in a Media Advisor Expert System**

---
**Conflict resolution in an expert system** refers to the process of managing situations where multiple rules are triggered at the same time, each suggesting different actions or outcomes. The system must determine which action to prioritize by evaluating the rules based on predefined criteria, such as priority levels, relevance, or specific conditions, ensuring that the most appropriate decision is made.

<p align="center">
  <img src="https://www.wellable.co/blog/wp-content/uploads/2023/08/7-Effective-Conflict-Resolution-Techniques-In-The-Workplace-2.png" width="400"/>
</p>

## Project Overview

This project demonstrates a **Conflict Resolution Mechanism** for a Media Advisor Expert System. The system provides recommendations for trainees based on:
- User preferences  
- Media source reliability  
- Recency of news  
- Relevance to current trends  
- Job type and feedback requirements  

Conflicts may arise when **multiple rules are triggered** simultaneously for the same trainee. The system resolves these conflicts using **priority-based decision-making**.

---

## Scenario of Conflicting Rules

Example scenario:

- **Rule 13:** Recommends `'lecture - tutorial'` for `stimulus_response = analytical` (priority 1)  
- **Rule 14:** Recommends `'role-play exercises'` for `stimulus_response = oral` (priority 2)  

Both rules share the same `stimulus_situation='verbal'` and require feedback. A conflict occurs because both rules apply at the same time.

**Resolution:** The system uses **priority numbers** to determine which rule fires first. In this case, Rule 13 has higher priority, so `'lecture - tutorial'` is recommended.

---

## Conflict Resolution Mechanism

1. **Rule Priority:** Assign a priority to each rule (lower number = higher priority).  
2. **Specificity / Recency Tiebreakers:** If two rules have the same priority, the system chooses based on how specifically they match the trainee's context or the recency of information.  

**Why this method?**  
- Ensures **trusted and relevant recommendations**  
- Avoids dropping useful suggestions  
- Provides **consistent and explainable outputs**

---

## Sample Snippet

```python
# Rule 13: Analytical Response
Medium(medium='lecture - tutorial', priority=1)

# Rule 14: Oral Response
Medium(medium='role-play exercises', priority=2)

# Conflict Resolver:
# Sort mediums by priority and select the highest

Final Recommendation: lecture - tutorial


