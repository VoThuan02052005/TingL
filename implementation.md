# Implementation Plan

## AI Personalized English Learning Web

---

# 1. Project Overview

**Project name:** AI Personalized English Learning Platform

**Goal:**
Xây dựng một trang web học tiếng Anh cá nhân kết hợp các ý tưởng từ các nền tảng như MochiMochi và PREP, cho phép người học:

* Chọn **trình độ học**
* Học theo **lộ trình bài học**
* Ôn từ vựng bằng **Spaced Repetition**
* Luyện **Shadowing (nghe – nói)**
* Nhận **giải thích ngữ pháp bằng AI**

Hệ thống được thiết kế để **cá nhân hóa việc học** dựa trên tiến độ của người học.

---

# 2. Core Objectives

Hệ thống cần giải quyết các vấn đề phổ biến khi tự học tiếng Anh:

* Không có **lộ trình rõ ràng**
* Học từ vựng **nhanh quên**
* Thiếu **luyện nghe và nói**
* Không biết **đang ở trình độ nào**

Giải pháp:

* Curriculum theo **level (A0 → B2)**
* Thuật toán **Spaced Repetition**
* Module **Shadowing**
* AI hỗ trợ **giải thích câu**

---

# 3. Target Users

Đối tượng chính:

* Sinh viên IT
* Người tự học tiếng Anh
* Người mất gốc tiếng Anh

Trình độ hỗ trợ:

* A0 – Beginner
* A1 – Elementary
* A2 – Pre-Intermediate
* B1 – Intermediate
* B2 – Upper Intermediate

---

# 4. System Architecture

```
User
 ↓
Frontend (Streamlit / React)
 ↓
Backend API (FastAPI)
 ↓
Database (SQLite / PostgreSQL)
 ↓
AI Services
```

Modules:

```
Frontend
Backend
Database
AI Services
Audio Processing
```

---

# 5. Technology Stack

## Frontend

Option 1 (recommended for MVP)

```
Streamlit
```

Option 2

```
React / NextJS
```

---

## Backend

```
Python
FastAPI
```

---

## Database

```
SQLite (MVP)
PostgreSQL (production)
```

---

## AI / ML Tools

Speech recognition:

```
Whisper
SpeechRecognition
```

AI explanation:

```
OpenAI API
Local LLM
```

---

# 6. Core Features

---

# 6.1 User Level Selection

Khi người dùng đăng nhập lần đầu:

```
Select your level
```

Levels:

```
A0
A1
A2
B1
B2
```

Sau khi chọn:

```
Load curriculum tương ứng
```

Hoặc sử dụng **Placement Test** để xác định trình độ.

---

# 6.2 Lesson-based Curriculum

Chương trình học được tổ chức theo:

```
Level
 └ Lessons
      └ Activities
```

Example:

```
Level A1
  Lesson 1: Greetings
  Lesson 2: Introduce yourself
  Lesson 3: Daily activities
```

Mỗi lesson gồm:

```
Vocabulary
Listening
Speaking
Grammar
Review
```

---

# 6.3 Flashcard System (Spaced Repetition)

Module học từ vựng dựa trên flashcard.

Flashcard structure:

```
Word
Meaning
Example
Pronunciation
```

Thuật toán:

```
SM2 spaced repetition
```

Review schedule example:

```
Day 1
Day 2
Day 4
Day 7
Day 15
Day 30
```

User feedback:

```
Again
Hard
Good
Easy
```

---

# 6.4 Shadowing Listening Practice

User luyện nghe bằng phương pháp shadowing.

Flow:

```
Play audio
Display transcript
User repeat sentence
```

Example:

Audio:

```
I went to the store yesterday.
```

User lặp lại câu ngay sau khi nghe.

---

# 6.5 Speaking Practice

User ghi âm giọng nói.

Flow:

```
Sentence displayed
User record voice
Speech recognition analysis
Score returned
```

Output example:

```
Pronunciation score: 78
Incorrect words:
store
yesterday
```

---

# 6.6 AI Grammar Explanation

User có thể click vào câu hoặc nhập câu.

Example:

Input:

```
I have been working here for 3 years.
```

AI output:

```
Grammar: Present Perfect Continuous
Structure: have/has + been + V-ing
Usage: hành động bắt đầu trong quá khứ và vẫn tiếp tục
```

---

# 6.7 Learning Dashboard

Trang dashboard hiển thị tiến độ học.

Example:

```
Current level: A1

Progress: 32%
Words learned: 120
Speaking score: 75
Listening time: 2h
```

---

# 6.8 Daily Learning Mission

Mỗi ngày hệ thống tạo nhiệm vụ.

Example:

```
Today's Mission

10 new words
5 speaking sentences
5 minutes listening
```

---

# 7. Database Design

## Table: users

```
id
username
email
password
level
created_at
```

---

## Table: lessons

```
id
level
lesson_name
description
```

---

## Table: vocabulary

```
id
word
meaning
example
phonetic
lesson_id
level
```

---

## Table: progress

```
id
user_id
lesson_id
score
completed
last_study
```

---

## Table: flashcard_reviews

```
id
user_id
word_id
review_level
next_review_date
last_review
```

---

# 8. Project Folder Structure

```
english_learning_platform/

backend/
    main.py
    api/
        lessons.py
        vocabulary.py
        speaking.py
        shadowing.py

frontend/
    streamlit_app.py

database/
    models.py
    schema.sql

data/
    vocabulary_dataset
    audio_files

ai/
    grammar_explainer.py
    speech_scoring.py
```

---

# 9. Development Phases

## Phase 1 – MVP

Features:

```
User login
Level selection
Lesson system
Flashcard vocabulary
Dashboard
```

---

## Phase 2 – Learning Features

```
Shadowing listening
Speaking recording
Progress tracking
Daily mission
```

---

## Phase 3 – AI Features

```
AI grammar explanation
Pronunciation scoring
Personalized lesson recommendation
```

---

# 10. Future Improvements

Possible improvements:

* Mobile version
* Gamification system
* Leaderboard
* AI conversation practice
* Automatic lesson generation

---

# 11. Expected Outcomes

Sau khi hoàn thành dự án:

User có thể:

* Học từ vựng hiệu quả
* Luyện nghe và nói
* Theo dõi tiến độ học
* Học theo trình độ cá nhân

Đối với developer:

* Project thể hiện kỹ năng **Fullstack + AI**
* Phù hợp để đưa vào **CV hoặc portfolio**

---

# 12. Conclusion

Dự án này kết hợp:

* Personalized learning
* Spaced repetition
* Shadowing listening
* AI hỗ trợ học ngôn ngữ

Hệ thống giúp người học **tự xây dựng lộ trình học tiếng Anh hiệu quả**, đồng thời là một dự án kỹ thuật có giá trị cao cho sinh viên ngành công nghệ.
