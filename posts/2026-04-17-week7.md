---
title: "Week 7 – Functional Requirements for Fan Qualification System"
date: "2026-04-19"
summary: "Defining system behaviour, constraints, and interaction logic for evaluating fan participation"
tags: ["functional requirements", "interaction design", "fan system"]
author: "Beverly"
---

## From Idea to System

In Week 6, I explored the concept of a Fan Qualification System that evaluates fan identity based on meaningful engagement rather than superficial metrics.

This week, I shift from concept to system thinking by defining the functional requirements of the application. The goal is to clearly identify what users can do, how the system responds, and how interactions are structured.

---

## Core Feature

The core feature of this system is to evaluate whether a user can be considered a "qualified fan" based on their participation behaviours.

Instead of relying on simple metrics such as likes or purchases, the system focuses on more meaningful actions, including contribution, consistency, and engagement diversity.

---

## User Actions

Users can interact with the system through the following actions:

- Post content (+3 points)
- Comment on discussions (+2 points)
- Attend events (+5 points)
- Like content (+1 point)

These actions simulate typical behaviours in online fan communities.

---

## System Constraints (Anti-abuse Design)

To prevent users from artificially inflating their scores, the system introduces constraints:

- Each action has a daily limit (e.g., limited number of comments or likes)
- Repetitive actions contribute less over time
- The system encourages diverse participation rather than single-action repetition

This ensures that the evaluation reflects authentic engagement rather than mechanical interaction.

---

## System Responsibilities

The system is responsible for:

- Recording user actions
- Calculating total engagement score
- Applying constraints and limits
- Evaluating fan level based on behaviour patterns
- Displaying real-time qualification results

---

## Evaluation Logic

The system evaluates users based on total score and behavioural diversity:

- Score < 10 → New Fan
- Score ≥ 10 → Active Fan
- Score ≥ 20 → Core Fan (Qualified)

In addition, users who perform a wider range of actions are considered more engaged than those repeating a single action.

---

## User Flow

The interaction flow of the system is:

User performs action → System records behaviour → Score updates → Constraints applied → Fan level recalculated → Result displayed

---

## Reflection

This week helped me realise that designing a system is not only about defining features, but also about shaping behaviour.

By introducing constraints and multi-dimensional evaluation, the system becomes more aligned with real-world fan culture, where authenticity and long-term engagement matter more than visible metrics.

In the next stage, I will explore how these rules can be translated into interactive components and implemented within a web application.
