# ALEPH – Agent Interactions and Rules (v0.1)
תאריך עדכון: 2025-07-27

---

## 1. עקרונות מנחים לאינטראקציה
1. **מודל אורקסטרלי** – יש Orchestrator Layer שמסנכרן אינטראקציות בין הסוכנים.
2. **עבודת צוות מבוזרת** – כל Agent יכול להפעיל Agent אחר (Request/Response) דרך Event Bus.
3. **חוקי טריגר** – אינטראקציה בין Agents מבוססת על טריגרים (מילות מפתח, שאלות, מצבים).
4. **חוקי העמקה** – כל Agent מחויב לספק הסבר (Explainability) למידע שהוא מחזיר.
5. **בקרת Meta** – Meta-Teacher Agent מנטר את התקשורת בין כל Agents ומייעל אותה.

---

## 2. תרשים אינטראקציה טקסטואלי
```
[User] 
   |
   v
[Orchestrator Agent]
   |----> Curator Agent (איסוף נתונים)
   |          |
   |          v
   |----> Synthesizer Agent (סינתזה)
   |          |
   |          v
   |----> Explorer Agent (אסוציאציות חדשות)
   |          |
   |          v
   |----> Scientist/Philosopher Agents (ניתוחים)
   |          |
   |          v
   +----> Historian Agent (רקע היסטורי)
   |
   v
[Meta-Teacher Agent] (בקרה על התהליך)
   |
   v
[User - תוצר סופי]
```

---

## 3. חוקי אינטראקציה כלליים
1. **User → Orchestrator** – כל אינטראקציה מתחילה מה-Orchestrator שמחליט מי הסוכן הראשון לפנות אליו.  
2. **Orchestrator → Curator** – אם נדרשת אינטגרציה של ידע חדש, Curator הוא הראשון.  
3. **Curator → Synthesizer** – לאחר איסוף נתונים, Synthesizer מסכם ומארגן.  
4. **Explorer Trigger** – אם נדרש עומק אסוציאטיבי, Orchestrator מפעיל את Explorer.  
5. **Philosopher/Scientist** – נכנסים כשהשאלה מחייבת פרספקטיבה תיאורטית או אנליטית.  
6. **Historian** – מוזמן לספק רקע והקשרים היסטוריים.  
7. **Meta-Teacher** – מפקח על כל התהליך ומספק פידבק לשיפור.

---

## 4. טבלת תפקידי Agents

| Agent               | תפקיד ראשי                              | קלט עיקרי               | פלט עיקרי                          | מתקשר עם מי?                   |
|---------------------|-----------------------------------------|-------------------------|-------------------------------------|--------------------------------|
| **Curator Agent**   | אוסף ומסנן מקורות איכותיים              | שאלת משתמש/טריגר       | רשימת מקורות נקיים ומעובדים         | Orchestrator, Synthesizer      |
| **Synthesizer Agent** | סינתזה של מקורות ותובנות               | מידע מ-Curator          | סיכום מובנה, מסקנות                | Curator, Explorer, Philosopher |
| **Explorer Agent**  | יצירת הקשרים אסוציאטיביים               | מושג/תחום מ-Synthesizer | מפת אסוציאציות                     | Synthesizer, Philosopher       |
| **Scientist Agent** | ניתוח אנליטי, ניסויים, סימולציות        | שאלות מורכבות           | מודלים, חישובים, תוצאות ניסוי      | Explorer, Philosopher          |
| **Philosopher Agent** | פרספקטיבה רעיונית ופילוסופית           | מושגים/סוגיות           | מסגרות תיאורטיות                   | Synthesizer, Scientist         |
| **Historian Agent** | הקשר היסטורי ותרבותי                    | מושג/תחום               | מידע היסטורי                       | Synthesizer, Philosopher       |
| **Meta-Teacher Agent** | בקרה על תהליך הלמידה                  | כל פלט מהסוכנים         | פידבק, שיפור אינטראקציות            | כולם                           |
| **Security Agent**  | בדיקות פרטיות ואבטחת מידע               | זרימות דאטה             | דוחות אבטחה, ניתוח סיכונים         | Orchestrator, Meta-Teacher     |
