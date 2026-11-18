# النشر على GitHub Pages — لوحة الإدارة

الرابط: https://amo120661-sketch.github.io/alhamd-admin/

المجلد `docs/` يحتوي النسخة الثابتة الجاهزة (GitHub Pages يقرأ من `/docs` على الفرع `main`).

## مهم
لوحة الإدارة تعتمد بالكامل على API موجود في `server.ts` (قاعدة بيانات Supabase/PostgreSQL + Firebase Admin). GitHub Pages لا يشغّل Node.js، لذلك تسجيل الدخول وإدارة المنتجات/الطلبات لن تعمل إلا بعد نشر السيرفر وضبط `VITE_API_BASE` عند البناء.

## إعادة البناء
```bash
npm install --legacy-peer-deps
cp admin.html index.html
VITE_API_BASE=https://your-backend.example npx vite build --base /alhamd-admin/
# انسخ dist/ إلى docs/ ثم استعد index.html الأصلي
```

أضف نطاق `amo120661-sketch.github.io` إلى Authorized Domains في Firebase Auth إذا كنت تستخدم الدخول عبر Google.
