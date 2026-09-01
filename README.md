# 3K Coach V3.1 – Public-safe build

זוהי V3 עם שינוי פרטיות מינימלי בלבד.

מה השתנה לעומת V3:
- הוסרו מהקוד הציבורי נתוני אימון התחלתיים, משקל, גיל, גובה ותאריך יעד אישי.
- הוסרה תוכנית האימונים האישית המובנית מהתקנה חדשה.
- התקנה חדשה נפתחת ללא היסטוריה/תוכנית, ואז משחזרים גיבוי פרטי מתוך האפליקציה.
- מפתח האחסון המקומי נשאר זהה ל-V3, כדי לא לשבור נתונים קיימים באותו origin.
- גרסת ה-service-worker cache שונתה רק כדי שדפדפנים יטענו את הקבצים המעודכנים.

לא שונו ה-UI, מסך האימון, חריגות, הגרף, היסטוריה, העלאת גרף דופק, גיבוי/CSV או לוגיקת האימון.


## V3.2
נוסף אייקון אפליקציה ייעודי למסך הבית ב-iPhone ול-PWA, ללא שינוי בלוגיקת האפליקציה או בנתונים.

## V3.3
- Workout Focus Mode: ניווט עליון ותחתון מוסתרים בזמן אימון.
- תצוגת landscape קומפקטית.
- ביפ קצר במעבר בין מקטעים דרך Web Audio, שנועד להתערבב עם מוזיקה.
- דוח שבועי חכם כולל תמונות גרפי דופק בקובץ אחד.
- Share Sheet של iOS לטקסט + תמונות כשנתמך.

## V3.4
- אימון בדיעבד עבר למסך ייעודי שנגיש רק מכפתור "אימון בדיעבד".
- אימון מתוכנן שבוצע מסומן "בוצע" ואינו נשאר כאימון הבא.
- השלמת אימון נקבעת מתוך היסטוריית האימונים; מחיקת הרשומה מחזירה אותו אוטומטית ל"אימון הבא".
- צליל המעבר משתמש כעת בקובץ WAV אמיתי ולא ב-Web Audio סינתטי.
- נוסף כפתור "בדוק צליל מעבר".
- הדיווח השבועי יכול להיווצר כתמונת PNG אחת הכוללת את הסיכום ואת גרפי הדופק.

## V4.2
- שמע ניתן לבחירה: כבוי / ביפ / הכרזה קולית / שניהם. ברירת מחדל: כבוי.
- בדיקות שמע נפרדות לביפ ולהכרזה כדי לבדוק התנהגות מול מוזיקה ב-iOS.
- הכרזה קולית דינמית: "מתחילים" + מהירות, מהירות חדשה במעבר, ו"סיום אימון".
- דוח מלא למאמן כ-ZIP: report.txt, data.json וכל גרפי הדופק כקבצי תמונה נפרדים.
- תמונת הדיווח הקיימת נשארה כאפשרות מהירה.
- כל התנהגות V3.4 של אימון בדיעבד/בוצע/מחיקה נשמרה.

## V4.2 additions
- Planned workout distance is calculated automatically from all workout segments; manual override is available for deviations.
- HR is no longer requested at planned-workout completion. Coach plan codes may include `completedUpdates` entries keyed by `workoutId` or `planId` with `avgHr`, `maxHr`, and `coachComment`.
- HR screenshots are kept compact in weekly history and open in a large overlay via View graph.
- Treadmill segments support integer `incline` values 0–15. Incline is shown in the plan/live screen and included in speech cues.
- Gate 0 diagnostic has been retired after confirming that foreground GPS is reliable but locked/background PWA GPS is not. V4.4 now includes a foreground-only Outdoor Mode Beta with Wake Lock.

## V4.4
- Fixed/reinforced automatic speech announcements on iPhone by resuming SpeechSynthesis before cues and retrying a stalled utterance.
- Added a silent live audio-mode cycling button; changing mode does not itself play audio.
- Consistent live segment numbering and distance display, plus overall workout progress bar.
- Added Outdoor Mode Beta: Free Run and structured planned workouts using foreground GPS, smoothed live pace, target pace, automatic distance/time segment transitions, GPS accuracy/status, and workout saving.
- Added best-effort Screen Wake Lock for live workouts. Outdoor GPS remains foreground-only in the PWA; the screen must stay on.
- Added app-level workout touch lock with circular unlock gesture to reduce accidental taps.
