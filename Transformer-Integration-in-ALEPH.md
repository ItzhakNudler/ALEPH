
# Transformer Integration in ALEPH

## 🧠 מה זה Transformer?

### 1. הגדרה כללית
Transformer הוא ארכיטקטורת למידת מכונה שפותחה על־ידי Vaswani et al. בשנת 2017 במאמר המפורסם “Attention is All You Need”.

היא תוכננה במיוחד לטיפול ברצפים (כמו טקסט), ותוך ביטול הצורך ברשתות חוזרות (RNNs), שאיבדו יעילות ככל שהרצף התארך.

### 2. עקרונות ליבה בארכיטקטורת Transformer

#### 🔹 Self-Attention
היכולת של כל מילה במשפט להתייחס לכל שאר המילים ברצף, ולשקלל כמה "להקשיב" להן.

#### 🔹 Multi-Head Attention
הפעלת כמה מערכות הקשב במקביל, שכל אחת מתמקדת בזווית שונה של הקשרים ברצף.

#### 🔹 Position Encoding
צמידת מידע על מיקום לכל מילה כדי לאפשר הבנת רצף.

#### 🔹 Feed Forward Layers
שכבות fully-connected לעיבוד נוסף של הפלט.

#### 🔹 Layer Normalization & Residual Connections
שמירה על יציבות וזרימת מידע טובה.

### 3. תרשים כללי של Transformer Block

```
[Input Embedding + Position Encoding]
        ↓
[Multi-Head Self-Attention]
        ↓
[Add & Norm]
        ↓
[Feed Forward Network]
        ↓
[Add & Norm]
```

---

## 🔧 מה זה "Transformer מותאם"?

כוונון של מודל Transformer למשימה מסוימת — לדוגמה:
- זיהוי יחידות שיח (EDU)
- זיהוי קשרים רטוריים
- ניתוח רגשי

---

## 🧩 איך מתאימים Transformer ל־ALEPH?

### שלב 1: בחירת מודל בסיס
לדוגמה: Longformer, RoBERTa, BERT

### שלב 2: Fine-Tuning למשימות ALEPH
| משימה | התאמה |
|-------|--------|
| זיהוי קשרים רטוריים | אימון על זוגות EDU |
| ניתוח הקשר | fine-tune לפי תיוג תמאטי |
| הדהוד | אימון על תרחישי תמיכה או נטישה של רעיון |

### שלב 3: שילוב בסוכנים
- קריאה למודלים מתוך סוכנים קוגניטיביים.
- הפקת תובנות ברמת קישור, הדהוד והקשר.

---

## ⚙️ דוגמה לקוד
```python
from transformers import AutoModelForSequenceClassification, AutoTokenizer

model = AutoModelForSequenceClassification.from_pretrained("bert-base-uncased")
tokenizer = AutoTokenizer.from_pretrained("bert-base-uncased")

inputs = tokenizer("Although it was raining, we went outside.", return_tensors="pt")
outputs = model(**inputs)

predicted_relation = outputs.logits.argmax(dim=1)
```

---

## 🧭 לסיכום

| רכיב | תפקיד |
|------|--------|
| Transformer | הבנת יחסים בטקסט |
| Fine-Tuning | התאמה למשימות קוגניטיביות |
| ALEPH Integration | סוכנים מנצלים את המודלים לזיהוי קשרים, רעיונות, הדהוד |

