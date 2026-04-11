
# 🌐 Web Development Course: React & Next.js

Is document mein hum Web Development ke basics aur Next.js ko setup karne ka mukammal tareeqa sikhenge.

---

## 📝 1. Introduction to Web Development
Web development ka matlab hai aisi websites ya web applications banana jo internet par accessible hon. Ye ek zaroori field hai kyunki ye logon, businesses aur governments ko online presence banane aur poori duniya ke users ke saath interact karne ka mauka deti hai.

### Core Pillars:
1. **Front-End Development:** Website ka wo hissa jo user ko dikhta hai aur jis se wo interact karta hai.
2. **Back-End Development:** Wo logic aur server-side kaam jo background mein chalta hai.
3. **Data Bases:** Jahan website ka saara data store aur manage kiya jata hai.

---

## ⚛️ 2. React.js (Library)
React ek JavaScript library hai jo user interfaces banane ke liye istemal hoti hai. 

* **Kyun use karte hain?** Ye dynamic aur interactive web pages banane ke process ko simple bana deta hai.
* **Features:** Isme hum **Reusable Components** banate hain aur **State Management** ke zariye UI ko smoothly update karte hain.

---

## 🚀 3. Next.js (Framework)
Next.js ek popular framework hai jo React.js ke upar bana hai. Ye server-rendered applications banane ke liye best hai.

* **Beginner Friendly:** Beginners ke liye React par kaam karna asaan banata hai.
* **Performance:** Website ki loading speed ko super fast karta hai.
* **SEO:** Google search engine ke liye ye best framework hai.

---

## 🛠️ 4. Installation & Setup (For Students)

Class mein project start karne ke liye ye steps follow karein:

### Step 1: Install Node.js
Sabse pehle [nodejs.org](https://nodejs.org/) se Node.js install karein. Check karne ke liye terminal mein likhein:
```bash
node -v
```

### Step 2: Create Next.js App
Terminal kholein aur ye command chalayein:
```bash
npx create-next-app@latest my-class-project
```
*(Setup ke waqt saare options par Enter press kar dein)*

### Step 3: Run the Project
Folder ke andar jayein aur server start karein:
```bash
cd my-class-project
npm run dev
```
Ab browser mein `http://localhost:3000` kholein.

---

## 📋 5. Summary Table

| Topic | Description |
| :--- | :--- |
| **Frontend** | User Interface (HTML, CSS, JS) |
| **Backend** | Server & Logic (Node.js, Python) |
| **Database** | Data Storage (MongoDB, SQL) |
| **React** | UI Library |
| **Next.js** | Full-stack Framework |

Next.js mein file structure ko organize karna bohot zaroori hai taaki project bada hone par bhi manage karna asaan rahe. Niche ek standard aur **Best Practice** ke mutabiq `README.md` file ka content diya gaya hai.

Isko aap apni `FILE_STRUCTURE.md` ya `README.md` mein paste kar sakte hain.

---

```markdown
# 📂 Next.js Project File Structure - Best Practices

Next.js (App Router) mein file structure ko sahi tareeqe se manage karna ek professional developer ki nishani hai. Is guide mein hum ek clean aur scalable structure sikhenge.

---

## 🏗️ Recommended Folder Structure

Aapka project kuch is tarah dikhna chahiye:

```text
my-next-app/
├── public/              # Static files (Images, Icons, Fonts)
├── src/                 # Main Source folder
│   ├── app/             # App Router (Routes, Layouts, Pages)
│   │   ├── (auth)/      # Route Groups (Login, Signup)
│   │   ├── (dashboard)/ # Route Groups (Admin, User Panel)
│   │   ├── api/         # API Routes (Backend Endpoints)
│   │   ├── layout.tsx   # Global Layout
│   │   └── page.tsx     # Homepage
│   ├── components/      # Reusable UI Components
│   │   ├── ui/          # Small elements (Buttons, Inputs)
│   │   └── common/      # Shared components (Navbar, Footer)
│   ├── hooks/           # Custom React Hooks
│   ├── lib/             # Utility functions & Third-party configs (Prisma, Axios)
│   ├── services/        # API calling logic (Data fetching)
│   ├── store/           # State Management (Zustand, Redux)
│   └── types/           # TypeScript Interfaces/Types
├── .env.local           # Environment Variables
├── next.config.js       # Next.js Configuration
└── tailwind.config.js   # Tailwind CSS Configuration
```

---

## 🔑 Key Folder Explanations

### 1. `src/app/` (The Core)
Next.js 13+ mein saari routing `app` folder ke andar hoti hai.
* **`page.tsx`**: Ye har route ki main file hoti hai.
* **`layout.tsx`**: Ye pages ke beech shared UI (jaise Navbar) ke liye use hota hai.
* **`(folder-name)`**: Bracket wali folders "Route Groups" hoti hain, ye URL mein show nahi hoti lekin organization mein madad karti hain.

### 2. `src/components/`
Sari UI components yahan honi chahiye. Ek achi practice ye hai ke aap `ui` folder banayein jisme base components (shadcn/ui style) rakhein.

### 3. `src/lib/`
Yahan aap reusable utility functions rakhte hain (jaise `utils.ts`) ya third-party clients (jaise Database connection logic).

### 4. `src/hooks/`
Agar aap koi custom logic bar-bar use kar rahe hain (jaise `useLocalStorage`), toh uske liye alag hooks folder banayein.

---

## ✅ Best Practices (Zaroori Baatein)

1.  **Modular Approach:** Ek file mein bohot saara code na likhein. Chote-chote components banayein.
2.  **Route Groups Use Karein:** Auth aur Dashboard ke pages ko `(auth)` aur `(dashboard)` groups mein rakhein taaki folder saaf rahe.
3.  **Naming Convention:** Folder ke naam hamesha lowercase mein rakhein (e.g., `user-profile`). Components ke naam PascalCase mein honi chahiye (e.g., `Navbar.tsx`).
4.  **Keep `public` clean:** Sirf wahi images rakhein jo static hon. Baki assets ke liye Cloudinary ya AWS use karein agar project bada hai.

---

## 🚀 Pro Tip for Students
Hamesha project start karte waqt `src` directory ka option **"Yes"** karein. Isse aapka config files aur application code alag-alag rehta hai aur management asaan ho jati hai.


