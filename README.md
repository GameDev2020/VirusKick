<div dir='rtl' lang='he'>

# שם המשחק: Virus Kick

**להביא את התרופה לוירוס קטלני עם נגיעות של נוסטלגיה**

### תיקון הערות:
* הוספנו משטחים אקראיים מאתגרים יותר. אחד מהערותיכם הייתה שהמשחק עדין בחיתולים שלו. הוא אמנם עדין בבנייה ויש אובייקטים חסרים.
אבל במבט על כבר קיימים 5 שלבים מלאים עובדים, תפריט ראשי מסודר, הוראות ברורות והגדרות שישרתו את השחקן.
* תיקנו את הקפיצה שתהיה תואמת את המשטחים והאובייקטים
* הוספנו מסכה שכאשר לוקחים אותה היא מעניקה מגן לשחקן מפני פסילות למשך זמן קצוב
* הוספנו סליידר שמציג בכל פריים איזה סטטוס אנחנו בשלב
* בעקבות ההערה שנתתם, כעת ניתן לחזור לאחורה.
* ייחודיות המשחק: כעת ניתן לראות את המסכה שקשורה לנגיף אך בהמשך יהיה ניתן ליירת גם ויהיה מד של אפקט הדבקה.

## itch link: https://gamedev2020.itch.io/viruskick-prefinal

## מהות המשחק

תארו את הרעיון המרכזי של המשחק שלכם
(concept) 
בשלושה-ארבעה משפטים - "נאום מעלית".

איזה סוג משחק זה, ולמי הוא מיועד?
* לאיזה פלטפורמה: המשחק מיועד למחשב רגיל
* לאילו שחקנים (איזה גילים / רמת כישרון / רמת ניסיון / תחומי עניין)? 
המשחק מיועד לכל השחקנים שאוהבים משחקי פלטפורמה עם אתגרים,ואינו דורש כישרון מיוחד כדי להתחיל את המשחק.
* לכמה שחקנים (אחד / רבים, שיתופי / תחרותי)? 
המשחק מיועד לשחקן יחיד.

---
## תיעוד הקוד
 
 * https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/GameManager.cs
 
 מנהל את המשחק כולו, מצהיר מתי המשחק מתחיל(בעת לחיצה על מקש רווח), מתי המשחק מסתיים, סוכם את הנקודות המצטברות ומאפס את המשחק בעת פסילות.
 
 * https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/PlayerMovement.cs
 
 מאפשר לשחקן תזוזה ימינה ושמאלה, וקפיצה שנעשת עם 3 דגשים:
 1. מקש רווח לחיצה קצרה- גורר קפיצה ונחיתה מהירה.
 2. לחיצה ארוכה על רווח מעט את ההתקדמות חזרה אל הקרקע.
 3. לא ניתן לבצע ריבוי קפיצות, נעשת בדיקה אם השחקן על הקרקע ולאחר מכן רק יוכל לקפוץ שוב.
 
 * https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/ShipCollsion.cs
 
   מנהל את אירוע ההתנגשות בקרקע, סקריפט שנועד לזהות אם ניתן לקפוץ או האם השחקן עדין באוויר. נועד לשם מניעת כפילויות. נוסף לכך בודק התנגשות בוירוס.
   
 * https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/ScoreCalc.cs
 
 שולף מהסקריפט 'מנהל המשחק' את הניקוד המצתבר והוא מוצג על המסך בכל פריים
 
 * https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/PlayerCollision.cs
 
מעדכן אם השחקן על הקרקע בעת הנחיתה, לאחר הנחיתה, וכאשר קופץ שוב מעדכן כי כבר לא הקרקע. באמצעות משתנה בוליאני שמעדכן את 'מנהל המשחק' בכל רגע

* https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/PlatformSpawner.cs

המשחק במבט כללי משדר שביל אינסופי, ועל מנת ליישם זאת ללא הגבלה של זמן וגודל קבוע, יצרנו סקריפט שבעת הגדרת זמן מסוים מוסיף  רכיב בסוף השביל.
 
 * https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/PlatformPooler.cs
 
יצרנו רשימה של משטחים אותה ניתן להגדיר ידנית ביוניטי. ברשימה זאת ניתן לשים כל מיני סוגים של משטחים שחלקם עם וירוסים וחלקם עם מכשולים אחרים אותם נגדיר בהמשך.
מן הרשימה הזאת מוגדר בצורה רנדומלית משטח אותו יוצרים כל זמן מוגדר בסוף השביל על מנת לדמות משחק אינסופי.

* https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/MovePlatforms.cs

לשחקן אין יכולת לקבוע לעצמו מהירות, הוא נע באופן דיפולטיבי קדימה, אך למעשה אנחנו הגדרנו כי המשטח נע לכיוון השחקן כך שזה מדומה לכך שהשחקן רץ על המשטח.
לכל משטח שנוצר, מוגדר סקריפט זה שנותן מהירות מסוימת שעולה בהדרגה לכיוון השחקן. כל המשטחים נעים באותה מהירות על מנת ליצור אחידות למשחק.

* https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/FollowPlayer.cs 

סקריפט שמייצב את המצלמה בקצב קבוע אחרי השחקן בהתאם לתזוזתו

* https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/FinalScore.cs

כאשר מוגדר כי המשחק הסתיים, יוצג התוצאה הסופית של המשחק. לקוח מהסקריפט של מנהל המשחק

* https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/DeactivateObject.cs

אחר התקדמות במשטחים במשך זמן מסוים נכבה את הרכיבים שהתרחקנו מהם, על מנת לא להעמיס ברכיבים דלוקים במשחק. את הזמן ניתן לקבוע ידנית 

* https://github.com/GameDev2020/VirusKick_week9/blob/main/Assets/scripts/CanvasBoardManager.cs
בוחר איזה רכיבים מהקנאבס יופיעו בעת הרצת המשחק ואיזה רכיבים יוצגו בעת איפוס

## פרטי המשחק


### 1. מה רואים?

* איך נראה מסך המשחק?  
במשחק ישנו משטח ראשי במרכז המצלמה בתחתית המסך שעליו השחקן נמצא עד סוף השלב, ובמסך עצמו ניתן לראות כמה חיים נשארו לשחקן, ניקוד, וכמה זמן נותר לסיום השלב.
* מה רואים בגבולות של המסך?  
ניתן לראות כמה חיים נשארו לשחקן, ניקוד, וכמה זמן נותר לסיום השלב.
* האם אפשר לעבור את גבולות המסך?  
לא ניתן לעבור את גבולות המסך.
* מה רואים מעבר לגבולות המסך?  
אין עצמים מחוץ למסך\ מצלמה.

![alt text](https://raw.githubusercontent.com/GameDev2020/VirusKick_week9/main/mainGame.JPG)

### 2. מה עושים?

איך דברים קורים? איך מתקדמים במשחק?

* תהליך ההתחלה של המשחק - שלושים השניות הראשונות.  
לשחקן תהיה אפשרות לבחור דמות בה הוא ירצה לשחק. לשחקן יובהר מטרת המשחק והחוקים בו. יוצג מסך ראשי בו יהיה ניתן לבחור מתי להתחיל את המשחק, או האם לצפות בהוראות. מרחב המשחק יוצג לשחקן על ידי מפה.  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/%D7%AA%D7%94%D7%9C%D7%99%D7%9A%20%D7%94%D7%AA%D7%97%D7%9C%D7%94.jpg?raw=true)
*	תהליך הליבה של המשחק – רצף-הפעולות שהשחקן מבצע שוב ושוב על-מנת להתקדם במשחק.  
השחקן יתחיל לשחק שלב אחר שלב לפי רמות קושי ויצבור נקודות, משלב לשלב יש יותר מכשולים (וירוסים) שמעכבים את השחקן ומפריעים לו להתקדם במשחק ולעבור את השלב. יתכן ויהיו מכשולים שיורידו לו מהזמן, או מכשולים שיעצרו את תנועתו, ואף מכשולים שיגרמו לו להתחיל את השלב מחדש ויגרמו לפסילה.  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/%D7%AA%D7%94%D7%9C%D7%99%D7%9A%20%D7%9C%D7%99%D7%91%D7%94.jpg?raw=true)
*	תהליך הסיום של המשחק – הפעולות שהשחקן מבצע כדי לנצח / לסיים את המשחק.
השחקן מגיע לשלב האחרון, הקשה ביותר. כשמגיע לסופו יוצג מסך של ניצחון ותוצג התרופה שתוציא את העולם מהמשבר.  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/%D7%AA%D7%94%D7%9C%D7%99%D7%9A%20%D7%A1%D7%99%D7%95%D7%9D.jpg?raw=true)
* מה המטרות שהשחקן צריך להשיג כדי לנצח במשחק?  
על השחקן לנצח את כל השלבים במשחק.  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/%D7%9E%D7%98%D7%A8%D7%95%D7%AA%20%D7%94%D7%A9%D7%97%D7%A7%D7%9F.jpg?raw=true)
לגבי כל תהליך, תארו את המכניקה שלו - באיזה פקדים השחקן ישתמש (עכבר / מקלדת / מגע), ומה יקרה במשחק כתוצאה מכך.  
השחקן ישחק בעזרת המקלדת במחשב בלבד.




### 3. מה העצמים?

מה הם האובייקטים במשחק ומה הם עושים?  האם כל אחד מהאובייקטים הוא:
* עצם חיוני לצורך השגת היעדים (main quest object)?  
לא כל אובייקט במשחק הוא מיועד להשגת המשימה העיקרית של המשחק, ישנם הרבה מאוד עזרים שרק עוזרים לנו להגיע לסוף שלב מסויים ולא תואמים לעלילה המשחק.
* עצם לא-חיוני אבל מסייע לשחקן (משאב)?  
ישנם סוגים שונים של עזרים שעוזרים לנו במשחק:  
מסכה- מגינה על השחקן מפני המכשולים למשך זמן קצוב.  
ערכת עזרה ראשונה - מגבירה לשחקן את מהירות התנועה שלו ומוסיפה לו חיים.  
שעון חול- מוסיף לשחקן זמן לסיים את השלב.  
מטבעות- מיועדות לצבירת נקודות ושיא אישי,המטבעות מהוות אתגר עבור השחקן מכיוון שמאלצות אותו לנוע בתזוזה יותר מסוכנת וללכת למקומות בהן הם נמצאים. מצד אחד זה עוזר במיומנות ובצבירת הנקודות אך מצד שני יכול לסכן את השחקן לגעת בוירוסים.  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/mask.jpg?raw=true)  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/first%20aid%20kit.jpg?raw=true)  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/sand%20watch.jpg?raw=true)  
![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/coin.jpg?raw=true)  

* עצם נייטרלי?  
אין עצמים נייטרלים במשחק.
* עצם המפריע לשחקן (מכשול)?  
ישנם עצמים אשר מפריעים לשחקן במשחק:  
וירוס A –וירוס המסוכן ביותר שגורם לפסילת של השלב והתחלתו מחדש. על השחקן להיזהר מהווירוס הזה יותר מכולם.  
וירוס B- וירוס שמוריד לשחקן מהזמן הקצוב של השלב. וירוס זה יכול להזיק אם נשאר מעט זמן לשחקן לסיים את השלב אך עדין הוא לא קרוב לסיומו.  
וירוס C- מוריד מהצבירת נקודות ויכול לפגוע בשבירת שיא אישי.  
וירוס D- וירוס שעוצר את הדמות מתזוזה. 
ומכשולים סטטיים שמונעים מהשחקן לזוז.


### 4. מה האפשרויות?

אילו בחירות השחקן יכול לעשות כדי לשנות את צורת המשחק? בפרט:
* אילו רמות-קושי יהיו במשחק? מה יהיו ההבדלים בין רמות-קושי שונות?  
הרמות קושי במשחק יהיו באופן מדורג באופן הבא:
שלב ראשון – מעט וירוסים, המון זמן , מהירות קבועה סבירה לשחקן.  
שלב שני – יותר וירוסים , פחות זמן מוגבל, מהירות גבוהה יותר לשחקן.  
שלב שלישי- הרבה וירוסים , זמן קצוב שמקשה על השחקן, מהירות גבוהה  
שדורשת זריזות של השחקן.  
משלב לשלב הכישורים זירוז ודיוק נדרשים יותר ויותר, מכיוון שבהדרגה כמות  
הווירוסים שצריך להרוג או להתחמק עולה, הזמן נהיה קצר יותר וכן המהירות  
של השחקן נהיית גבוהה והוא נאלץ להתמודד עם לחץ ולחדד את הכישורים   
שלו לפי רמת קושי.  
* אילו סוגי-שחקנים יהיו במשחק?  
במשחק לא יהיו מספרים שחקנים שניתן לשחק איתם אלה שחקן אחד שניתן לשחק איתו. 
* אילו אפשרויות יהיו למאפיינים החיצוניים של המשחק? (בהירות, קול וכו')  
יהיה ניתן לבחור רמת קושי למשחק, ויהיה מסך של הוראות.  
     

### 5. מה העולם?

* באיזה עולם מתרחש המשחק?  באיזו סביבה?  
המשחק מתרחש בחלל, כל פעם באיזור אחר שידוע לאדם והמטרה היא להתקרב לכדור הארץ.
* האם העולם יהיה סגור או פתוח?  עגול או שטוח?  
העולם הוא עולם סגור ושטוח.
* מה הם חוקי הפיסיקה, הטבע, הגיאוגרפיה, ההסטוריה, הכלכלה, החברה והפוליטיקה בעולם שלכם?  
חוקי הטבע- עולם שבו מותר לנוע ימינה ושמאלה והגוף נמשך באופן דיפולטיבי קדימה. ההתנגשויות באובייקטים בטבע נושאות בתוצאות. אם מתנגשים בווירוס עלולים להיתקע או לחזור לנקודת ההתחלה. ובמקביל יש אמצעים נוספים שיתנו כוחות נוספים לשחקן.  
חוקי הגיאוגרפיה- תחילת המשחק יהיה בכוכב הרחוק ביותר וכל שלב יהיה בכוכב לכת אחר שהולך וקרב אל כדור הארץ. המשחק יבנה בצורה גרפית כך שיראה בחלל החיצון על כוכבי הלכת השונים.  
חוק ההיסטוריה- ההיסטוריה היא המגפה העולמית בכדור הארץ, השחקן המריא אל הכוכב הרחוק על מנת להביא תרופה שתציל את האנושות.  
חוקי הכלכלה- לשחקן תהיה אפשרות של צבירת מטבעות במהלך המשחק כך שהמשחק מונע על ידי צבירת מספר מקסימלי של מטבעות.  
חוקי החברה- הקונפליקטים שיהיו לשחקן במהלך המשחק הן התנגשויות בווירוסים והתנגשויות במשאבים חיוניים. התנגשות בווירוס יהווה עבורו אויב בעוד שהתנגשות במשאב חיוני יהיה עבורו חבר עזר.  
חוקי הפוליטיקה- השחקן במטרתו במסע שלב אחר שלב היא להציל את האנושות.
* איזה חוקים יגבילו את פעולות השחקן במשחק?  
יהיה לשחקן זמן מוקצב, כמות חיים שנגמרת אם פוגעים במכשולים, וירוסים מדבקים, חולים מודבקים או אם השחקן נופל מהמפה.
* לפי איזה חוקים ייקבעו תוצאות של פעולות במשחק?
לפי המכשולים שהשחקן נתקל בהם, כמה חיים נשאר לשחקן בשלב, וכמה זמן נשאר לשחקן בשלב.  
מכיוון שהמשחק הוא לינארי ומדובר בחללית שמתקדמת קדימה, השלבים הם יהיו משטח שבו השחקן צריך להיות כל הזמן, דוגמא לשלבים (ראשוניים) :  

![alt text](https://raw.githubusercontent.com/GameDev2020/VirusKick_week9/main/endlessWorld.JPG)


### 6.	מה הסיפור?
*	מהו סיפור הרקע של המשחק – מה קרה לפני שהמשחק התחיל?  
סיפור הרקע מאחורי המשחק הוא שמגיפה הגיעה אל כדור הארץ, כמו בחיים האמתיים , מגפה שפרצה לפתע ולא נמצאה לה תרופה. על השחקן מוטלת האחריות לטוס בחללית אל הלא נודע להביא את התרופה. כאן הוספנו את האפקט הקומי והבדיוני שהתרופה נמצאה בחלל הרחוק, וכל שלב במשחק יהיה כוכב לכת שמתקרב יותר ויותר אל כדור הארץ. נוכל לחדד את הסיפור במשחק על ידי הצגת סקירה כללית בתחילת המשחק שתבהיר את המטרה שלו. וכן במפה צדדית במהלך המשחק עצמו יהיה ניתן לראות את כל הכוכבים שיש לעבור על מנת להעביר את התרופה אל היעד – כדור הארץ!
*   מהי עלילת המשחק - מה קורה במהלך המשחק ואיך השחקן משפיע על העלילה?  
עלילת המשחק היא לאסוף את התרופה מהכוכב הרחוק, ולהביאה אל כדור הארץ. כל שלב יתבצע על כוכב לכת אחר שיותר קרוב לכדור הארץ. היא תשתנה בהתאם לקשת הדרמטית על פי התקדמות השחקן. אם יתקע על שלב מסוים העלייה בציר y תיעצר מכיוון שמבזבז את זמנו על אותו שלב. אם יתקדם ויעבור שלבים, הגרף יתעצב כך שמאיץ אל היעד.  
התנהגות השחקן תשפיע על העלילה לפי האופן שבו משחק, אם השחקן זריז , צובר נקודות, מתחמק מווירוסים ואוסף משאבים חיוניים הוא יביא יותר מהר את התרופה אל כדור הארץ. באותה נשימה אם יתקע בשלבים ולא יעמוד ביעדיו ההתקדמות שלו אל כדור הארץ תהיה איטית וייאלץ לחזור על שלבים.  

![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/%D7%A7%D7%A9%D7%AA%20%D7%93%D7%A8%D7%9E%D7%98%D7%99%D7%AA.jpg?raw=true)


### 7.	מי הדמויות?

*   מה התכונות שלהן, מה התפקיד שלהן במשחק, ואיך הן ייראו?  
דמויות מרכזיות: השחקן כדמות חללית שמהווה הגיבור, והווירוסים שמהווים האויב והמכשול.  
דמויות משניות: המגן והערכת עזרה ראשונה- יהוו אמצעים שיסייעו לשחקן ה"גיבור" להעביר את התרופה אל כדור הארץ ולהתחמק מהווירוסים.     
*	דמויות מרכזיות -  מי יהיה ה"גיבור" ומי ה"מתנגד" העיקרי?  
הגיבור יהיה השחקן שבו נשחק והמתנגדים יהיו המכשולים והוירוסים בשלב עצמו.
*	דמויות משניות – מי הן יהיו, ומה כל אחת תוסיף לחוויית השחקן? 
הדמויות המשניות יהיו המגן והערכת עזרה ראשונה- יהוו אמצעים שיסייעו לשחקן ה"גיבור" להעביר את התרופה אל כדור הארץ ולהתחמק מהווירוסים.  

![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/Q3%20Player.jpg?raw=true)

## שלבים במשחק

שלב ראשון – מעט וירוסים, המון זמן , מהירות קבועה סבירה לשחקן.    
שלב שני – יותר וירוסים , פחות זמן מוגבל, מהירות גבוהה יותר לשחקן.    
שלב שלישי- הרבה וירוסים , זמן קצוב שמקשה על השחקן, מהירות גבוהה    
שדורשת זריזות של השחקן.    
משלב לשלב הכישורים זירוז ודיוק נדרשים יותר ויותר, מכיוון שבהדרגה כמות    
הווירוסים שצריך להרוג או להתחמק עולה, הזמן נהיה קצר יותר וכן המהירות    
של השחקן נהיית גבוהה והוא נאלץ להתמודד עם לחץ ולחדד את הכישורים     
שלו לפי רמת קושי.    

---


## סקר שוק

לפני שמתחילים לעבוד על משחק (או כל מוצר אחר), חשוב לוודא שלא עשו את זה קודם. לא נעים לעבוד סמסטר שלם (או שנה שלמה) על משחק ואז לגלות שכבר יש משחק כזה. 

חפשו בגוגל, בחנות play, בפייסבוק, ובכל מקום אחר שיש לכם גישה אליו, משחקים דומים לרעיון שלכם. ציינו באיזה ביטויי-חיפוש השתמשתם.  

חיפשנו משחקי Runner-ים, ומתוך ידע כללי על עולם המשחקים חיפשנו ספציפית את המשחקים הבאים:  


Temple Run:  

![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/temple%20run.jpg?raw=true)  

המשחק שלנו שונה בכך שאנחנו לא רצים כדי להציל את חיינו אלה כדי להציל את שאר האנושות מווירוס קטלני, ולא בכדור הארץ אלה בחלל החיצון.   

Subway Surfers:  

![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/subway%20surfer.jpg?raw=true)  

המשחק שלנו לא נראה קרוב מבחינה גראפית, המטרה של המשחק שלנו היא שונה, ולא תופס את השחקן שלנו שוטר שאנחנו נפסלים כי אנחנו לא "עוברים על החוק".  

Hill Climb Racing:  

![alt text](https://github.com/GameDev2020/VirusKick/blob/master/Pictures%20and%20Flowcharts/hill%20climb%20racer.jpg?raw=true)  

המשחק שלנו לא נראה קרוב מבחינה גראפית מכיוון שזהו משחק תלת מימדי ולא דו מימדי כמו המשחק שכביכול דומה לשלנו, אנחנו לא מנסים להגיע לסוף השלב עם אוטו נתון רק כדי לסיים אותו אלה יש לנו מטלה למצוא תרופה לוירוס.     


</div>
