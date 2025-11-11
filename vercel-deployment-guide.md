# 🚀 คู่มือ Deploy ฟอร์มรับออเดอร์บน Vercel

## ขั้นตอนที่ 1: สร้างไฟล์โปรเจค

### 1.1 สร้างโฟลเดอร์ใหม่
สร้างโฟลเดอร์ชื่อ `order-form` บนคอมพิวเตอร์

### 1.2 สร้างไฟล์ `package.json`
```json
{
  "name": "order-form",
  "version": "1.0.0",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "lucide-react": "^0.263.1"
  },
  "devDependencies": {
    "@vitejs/plugin-react": "^4.0.0",
    "vite": "^4.3.9",
    "autoprefixer": "^10.4.14",
    "postcss": "^8.4.24",
    "tailwindcss": "^3.3.2"
  }
}
```

### 1.3 สร้างไฟล์ `vite.config.js`
```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
})
```

### 1.4 สร้างไฟล์ `tailwind.config.js`
```javascript
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 1.5 สร้างไฟล์ `postcss.config.js`
```javascript
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
```

### 1.6 สร้างไฟล์ `index.html`
```html
<!DOCTYPE html>
<html lang="th">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>ฟอร์มรับออเดอร์ - BALANC</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
```

### 1.7 สร้างโฟลเดอร์ `src` และไฟล์ภายใน

**ไฟล์ `src/main.jsx`:**
```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './index.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

**ไฟล์ `src/index.css`:**
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

**ไฟล์ `src/App.jsx`:**
คัดลอกโค้ดทั้งหมดจาก Artifact ที่สร้างไว้มาวางที่นี่

---

## ขั้นตอนที่ 2: สร้าง GitHub Repository

### 2.1 สมัคร GitHub (ถ้ายังไม่มี)
1. ไปที่ https://github.com
2. คลิก "Sign up" 
3. กรอกข้อมูลตามที่ขอ

### 2.2 สร้าง Repository ใหม่
1. คลิก "+ New repository" มุมบนขวา
2. ตั้งชื่อ: `order-form`
3. เลือก "Public"
4. คลิก "Create repository"

### 2.3 อัพโหลดโค้ด

**วิธีที่ 1: ใช้ GitHub Desktop (ง่ายที่สุด)**
1. ดาวน์โหลด GitHub Desktop: https://desktop.github.com
2. เปิดโปรแกรม > File > Add local repository
3. เลือกโฟลเดอร์ `order-form`
4. Commit และ Push

**วิธีที่ 2: ใช้ Command Line**
```bash
cd order-form
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/order-form.git
git push -u origin main
```

---

## ขั้นตอนที่ 3: Deploy บน Vercel

### 3.1 สมัคร Vercel
1. ไปที่ https://vercel.com
2. คลิก "Sign Up"
3. เลือก "Continue with GitHub" (ง่ายที่สุด)

### 3.2 Import Project
1. ที่หน้า Dashboard คลิก "Add New..."
2. เลือก "Project"
3. คลิก "Import" ที่ repository `order-form`

### 3.3 Configure Project
1. **Framework Preset:** เลือก "Vite"
2. **Root Directory:** ใช้ค่าเริ่มต้น (./")
3. **Build Command:** `npm run build`
4. **Output Directory:** `dist`
5. คลิก "Deploy"

### 3.4 รอสักครู่...
- Vercel จะ build และ deploy ให้อัตโนมัติ
- ใช้เวลาประมาณ 1-2 นาที

### 3.5 เสร็จสิ้น! 🎉
- คุณจะได้ URL แบบนี้: `https://order-form-xxxxx.vercel.app`
- เว็บพร้อมใช้งานแล้ว!

---

## ขั้นตอนที่ 4: สร้าง QR Code

### 4.1 คัดลอก URL
- คัดลอก URL ที่ได้จาก Vercel

### 4.2 สร้าง QR Code
1. ไปที่ https://www.qr-code-generator.com
2. วาง URL
3. ปรับแต่งสี/ดีไซน์ (ถ้าต้องการ)
4. ดาวน์โหลด

### 4.3 นำไปใช้
- พิมพ์ติดที่ร้าน
- ส่งให้ลูกค้าผ่าน Line/Facebook
- ใส่ในแคตตาล็อก

---

## 🎨 Custom Domain (ถ้าต้องการ)

### หากมีโดเมนของตัวเอง
1. ไปที่ Project Settings > Domains
2. คลิก "Add"
3. ใส่โดเมน เช่น `order.nexterra.com`
4. ตั้งค่า DNS ตามที่ Vercel แนะนำ
5. รอ 24-48 ชั่วโมง

---

## 🔄 วิธีอัพเดตเว็บไซต์

เมื่อต้องการแก้ไขฟอร์ม:

1. แก้ไขไฟล์ `src/App.jsx`
2. Push ขึ้น GitHub
3. Vercel จะ auto-deploy ใหม่ให้อัตโนมัติ!

---

## ❓ แก้ปัญหาที่พบบ่อย

### ไม่สามารถ Deploy ได้
- ตรวจสอบว่าไฟล์ครบถ้วน
- ตรวจสอบ package.json มี dependencies ครบ

### เว็บแสดงผลไม่ถูกต้อง
- ตรวจสอบ Build Command และ Output Directory
- ดู Build Logs ใน Vercel

### ต้องการความช่วยเหลือ
- ดู Documentation: https://vercel.com/docs
- ติดต่อ Vercel Support (ฟรี)

---

## 💡 เคล็ดลับ

- **ฟรีตลอดกาล:** Vercel ให้ใช้ฟรีสำหรับ personal projects
- **HTTPS อัตโนมัติ:** ความปลอดภัยสูง
- **CDN ทั่วโลก:** โหลดเร็ว
- **Auto Deploy:** แก้โค้ดแล้ว deploy อัตโนมัติ

---

## 📞 ต้องการความช่วยเหลือเพิ่มเติม?

หากมีปัญหาในขั้นตอนใด สามารถถามได้เลยค่ะ! 😊