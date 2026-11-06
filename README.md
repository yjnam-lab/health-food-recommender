# 🥗 Health Food Safety & Personal Recommender System

> **Personalized Health Food Recommendation Engine with Safety & Constraint Logic**  
> An end-to-end user-centric recommendation pipeline designed to safeguard users by filtering out restricted ingredients and matching optimal product combinations.

---

## 📌 Project Overview & Core Concept

### 💡 Problem Statement
Standard recommendation algorithms (e.g., popularity-based or basic similarity models) applied to health supplements pose critical safety risks: **they often recommend products containing ingredients that users must avoid due to allergies, medical conditions, or dietary constraints.**

### 💡 Core Concept: Safety-First Recommendation Engine
This project adopts a **"Safety-First Recommendation"** architecture, using an abstracted pipeline to prioritize user safety before evaluating product suitability:

1. **Safety Constraint Layer**: Strictly excludes candidates containing user-defined restricted ingredients (Hard Exclusion).
2. **Domain-Specific Scoring**: Computes weighted scores by combining ingredient composition and quality certifications (e.g., HACCP).
3. **Zero Cold-Start Dependency**: Operates immediately based on explicit user constraints without relying on historical interaction data (click/purchase logs).

---

## 📐 System Pipeline Architecture

The internal computational logic is encapsulated within security layers, exposing a clean, scalable interface.

```text
[ User Profile & Constraints ] ─── (Input: Restricted Ingredients)
                │
                ▼
  [ 🛡️ Safety Constraint Layer ]  ─── (Hard Exclusion & Risk Mitigation)
                │
                ▼
  [ ⚙️ Custom Scoring Engine ]   ─── (Domain-Specific Weighted Scoring)
                │
                ▼
   [ 🎯 Personalized TOP-N ]    ─── (Filtered Product Output)