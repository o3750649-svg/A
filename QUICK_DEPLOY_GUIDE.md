# 🚀 دليل النشر السريع - MedFutureAI

## 📍 روابط سريعة

- **GitHub**: https://github.com/o3750649-svg/A
- **Render Dashboard**: https://dashboard.render.com/
- **التوثيق الكامل**: اقرأ `DEPLOYMENT_COMPLETE.md`

---

## ⚡ خطوات النشر السريعة (10 دقائق)

### 1️⃣ Backend على Render

```
اذهب إلى: https://dashboard.render.com/
اضغط: New + → Web Service
Repository: o3750649-svg/A

الإعدادات:
- Name: medfutureai-backend
- Environment: Node
- Build: cd backend && npm install
- Start: cd backend && npm start
- Branch: main

Environment Variables: (أضف جميع القيم من ملف المتغيرات البيئية)
- NODE_ENV=production
- PORT=3001
- DATABASE_URL=<supabase_url>
- ADMIN_USERNAME=<username>
- ADMIN_PASSWORD=<password>
- CORS_ORIGIN=<frontend_url>
- RATE_LIMIT_WINDOW_MS=900000
- RATE_LIMIT_MAX_REQUESTS=100
- GEMINI_API_KEY=<key>
- OPENAI_API_KEY=<key>
- DEEPSEEK_API_KEY=<key>

اضغط: Create Web Service
```

### 2️⃣ Frontend على Render

```
اضغط: New + → Static Site
Repository: o3750649-svg/A

الإعدادات:
- Name: medfutureai-frontend
- Build: npm install --legacy-peer-deps && npm run build
- Publish: dist
- Branch: main

Environment Variables:
- VITE_API_URL=https://<backend-url>.onrender.com/api
- GEMINI_API_KEY=<key>

اضغط: Create Static Site
```

### 3️⃣ تهيئة قاعدة البيانات

```bash
# في Backend Shell على Render
cd backend && npm run init-postgres-db
```

### 4️⃣ اختبار

```
Backend: https://<backend-name>.onrender.com/api/health
Frontend: https://<frontend-name>.onrender.com
```

---

## ⏱️ الوقت المتوقع

- Backend Deploy: 5-7 دقائق
- Frontend Deploy: 3-5 دقائق  
- Database Init: 1 دقيقة
- **المجموع**: ~10-15 دقيقة

---

## 🆘 مشاكل؟

راجع `DEPLOYMENT_COMPLETE.md` قسم "المشاكل الشائعة"

---

## ✅ تم النشر؟

تسجيل الدخول:
- Username: من ملف المتغيرات البيئية
- Password: من ملف المتغيرات البيئية

🎉 استمتع بنظام MedFutureAI!
