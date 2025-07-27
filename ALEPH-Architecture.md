# ALEPH – Architecture Overview (v0.1)
תאריך עדכון: 2025-07-27

---

## 1. מבנה כללי
ALEPH בנוי במבנה רב-שכבתי (Layered Architecture) המשלב תשתית חישובית, שכבת ידע, סוכנים (Agents), מנועי למידה, וממשקי משתמש.

```
[ User Interface ]
        |
        v
[ Visualization & ALEPH Studio ]
        |
        v
[ Agents Layer ]
        |
        v
[ Knowledge Layer (Knowledge Graph + Ontology) ]
        |
        v
[ Infrastructure Layer (Cloud + Security + Data Lake) ]
```

---

## 2. תיאור שכבות

### שכבה 0 – Infrastructure Layer
- מחשוב ענן / Local GPU
- Data Lake לאחסון מידע גולמי
- Event Bus (Kafka/Redis Streams)
- Security Fabric (AI-based Cyber Security)

### שכבה 1 – Knowledge Layer
- Knowledge Graph (ALEPH-KG) – מיפוי קשרים בין תחומי ידע
- Ontology & Lexicon Engine – מבנה מושגים ויחסים
- Memory & Context Store – היסטוריית למידה
- Semantic Mapping

### שכבה 2 – Agents Layer
- Curator Agent – סינון מקורות ומידע איכותי
- Synthesizer Agent – שילוב תובנות ממקורות שונים
- Explorer Agent – חקירה אסוציאטיבית והצעות נושאים
- Philosopher Agent – מסגרות רעיוניות ופילוסופיות
- Scientist Agent – חישובים, סימולציות ומודלים
- Historian Agent – הקשרים היסטוריים
- Meta-Teacher Agent – מעקב ושיפור תהליכי הלמידה
- Security & Privacy Agent – ניהול פרטיות ואבטחה

### שכבה 3 – Learning & Reasoning Engines
- LLMs + Symbolic Reasoners
- Causal Inference Engine
- Simulation Engine
- Conceptual Bridge Engine

### שכבה 4 – User Interfaces
- ALEPH Studio – ממשק אינטראקטיבי
- Visualization Dashboard – הצגת Knowledge Graph ודשבורדים
- API Gateway
- Voice/Chat Interface

---

## 3. זרימות עבודה מרכזיות
1. **Associative Learning Pipeline**
   - מושג נכנס → Explorer Agent יוצר אסוציאציות → Synthesizer מרחיב → Knowledge Graph מעדכן.

2. **Systematic Learning Pipeline**
   - הגדרת תחום → Curator מסנן → Ontology ממפה מושגים → יצירת מסלול למידה מובנה.

3. **Convergence Pipeline**
   - חיבור בין תחומי ידע → Conceptual Bridge Engine יוצר קשרים חדשים → עדכון ALEPH-KG.

---

## 4. תרחישי שימוש ראשוניים
- חקירה פתוחה ע"י שילוב Explorer + Philosopher Agents.
- בניית תכניות למידה ממוקדות ע"י Curator + Synthesizer.
- ניתוחי עומק רב-תחומיים עם Scientist + Philosopher.
```