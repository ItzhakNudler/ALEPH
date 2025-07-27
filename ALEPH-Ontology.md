# ALEPH – Ontology (v0.1)
תאריך עדכון: 2025-07-27

---

## 1. מטרת המסמך
Ontology זה מתאר את סוגי הקשרים והישויות במערכת ALEPH, ומהווה תשתית סמנטית ל-Knowledge Graph (ALEPH-KG).

---

## 2. ישויות עיקריות (Entities)
1. **Concept (מושג)** – רעיון, תיאוריה או מונח.
2. **Agent (סוכן)** – יחידה אוטונומית במערכת המבצעת פעולות מסוימות.
3. **Flow (זרימה)** – תהליך למידה (Associative, Systematic, Convergence).
4. **Source (מקור)** – פריט מידע או ידע (מאמר, ספר, מאגר).
5. **Task (משימה)** – מטרה או פעולה לביצוע בתוך ALEPH.

---

## 3. סוגי קשרים (Relations)
- **related_to** – קשר כללי בין שני מושגים.
- **is_a** – היררכיה (לדוגמה: Philosopher Agent is_a Agent).
- **part_of** – רכיב שהוא חלק ממבנה רחב יותר (Synthesizer part_of Agents Layer).
- **uses** – שימוש של סוכן בכלי או מנוע (Curator uses Knowledge Graph).
- **inspired_by** – קשר השראה (לדוגמה: Concept A inspired_by Concept B).
- **converges_with** – קשר קונברגנציה בין תחומי ידע שונים.
- **validates** – סוכן שמאמת או בודק תוצאה (Scientist validates Hypothesis).
- **orchestrates** – סוכן שמתאם בין אחרים (Meta-Teacher orchestrates Agents).
- **produces** – תוצר שמופק מתהליך מסוים (Flow produces Report).
- **derived_from** – ידע או מושג שמקורו בנתון אחר.

---

## 4. מבנה גרפי לדוגמה (Textual)
```
[User] --initiates--> [Task]
[Task] --handled_by--> [Agent]
[Agent] --uses--> [Source]
[Agent] --produces--> [Concept]
[Concept] --related_to--> [Concept]
[Flow] --orchestrates--> [Agents]
```

---

## 5. Ontology Core Classes
- **Entity** – בסיס לכל סוג ישות.
  - **Concept**
  - **Agent**
  - **Flow**
  - **Source**
  - **Task**
- **Relation** – סוגי הקשרים שהוגדרו לעיל.

---

## 6. שימוש עתידי
- הרחבת ה-Ontology לתחומים נוספים.
- שימוש בה ליצירת **Semantic Search** בתוך ALEPH.
- קישור בין ה-Ontology ל-Lexicon (מיפוי שמות לקשרים ולסוכנים).
