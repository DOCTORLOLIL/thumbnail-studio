# סטודיו טאמבניילים

עורך טאמבניילים חינמי בעברית, בדף אחד בלי שרת. האתר החי: https://thumbnail.bulu.lol

## מבנה הפרויקט

- `public/index.html` - כל האתר (HTML, CSS ו-JS בקובץ אחד)
- `public/og.png` - תמונת השיתוף (1200×630)
- `public/robots.txt`, `public/sitemap.xml` - קבצים לגוגל
- `wrangler.jsonc` - הגדרות הפריסה ל-Cloudflare Workers (שם ה-Worker: `thumbnails`)

## פריסה ל-Cloudflare

ב-Cloudflare: Workers & Pages ← `thumbnails` ← Settings ← Builds ← Connect, ובחירת המאגר הזה.
בהגדרות הבנייה: Build command נשאר ריק, Deploy command `npx wrangler deploy`, ו-Production branch `main`.
אחרי החיבור, כל `git push` ל-`main` מעדכן את האתר.

## הרצה מקומית

פתחו את `public/index.html` בדפדפן, או הריצו `npx wrangler dev`.

## שינוי הדומיין

הכתובת `https://thumbnail.bulu.lol/` מופיעה ב-`public/index.html` (canonical, og:url, og:image, JSON-LD), ב-`public/robots.txt` וב-`public/sitemap.xml`.

## עדכונים

כל דחיפה לענף `main` מפעילה בנייה ופריסה אוטומטית ב-Cloudflare.
