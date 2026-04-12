

# 🌐 Web Development Course: React & Next.js

Is document mein hum Web Development ke basics se lekar Next.js ko setup karne aur uske core concepts tak ka **mukammal tareeqa** sikhenge.

---

## 📝 1. Introduction to Web Development

Web development ka matlab hai aisi websites aur web applications banana jo internet par accessible hon. Yeh ek bahut zaroori field hai kyunki isse businesses, governments aur individuals poori duniya ke users ke saath interact kar sakte hain.

### Core Pillars of Web Development:

1. **Front-End Development** → Jo user ko dikhta hai aur jis se user interact karta hai (HTML, CSS, JavaScript, React).
2. **Back-End Development** → Server-side logic aur functionality (Node.js, Express, Python, etc.).
3. **Database** → Data ko store aur manage karne ke liye (MongoDB, PostgreSQL, MySQL).

---

## ⚛️ 2. React.js (Library)

React ek powerful JavaScript **library** hai jo user interfaces (UI) banane ke liye bani hai.

- **Kyun use karte hain?** Dynamic aur interactive web pages banana bohot simple aur efficient ho jata hai.
- **Main Features:**
  - Reusable Components
  - Virtual DOM (fast updates)
  - State Management
  - One-way data binding

---

## 🚀 3. Next.js (Framework)

Next.js React.js ke upar bana ek full-featured **framework** hai. Yeh specially server-rendered aur production-ready applications banane ke liye best hai.

### Key Advantages:
- **Beginner Friendly** – React ke concepts ko asaan banata hai
- **Excellent Performance** – Super fast loading speed
- **Built-in SEO** – Search engines ke liye bahut accha
- **App Router** – Modern routing system
- **Server & Client Components** – dono ka support
- **Image Optimization, Font Optimization, API Routes** etc.

---

## 🛠️ 4. Installation & Setup (For Students)

### Step 1: Node.js Install Karein
Sabse pehle [nodejs.org](https://nodejs.org/) se **Latest LTS version** download aur install karein.

Check karne ke liye terminal mein:
```bash
node -v
```

### Step 2: Next.js Project Create Karein (Recommended Way)

```bash
npx create-next-app@latest my-class-project
```

**Setup ke waqt ye options select karein:**
1. Project name → `my-class-project` (apna naam de sakte hain)
2. TypeScript → **Yes**
3. ESLint → **Yes**
4. Tailwind CSS → **Yes**
5. `src/` directory → **Yes**
6. App Router → **Yes**
7. Customize import alias → **No**

### Step 3: Project Run Karein

```bash
cd my-class-project
npm run dev
```

Ab browser mein kholein: `http://localhost:3000`

---

## 📋 5. Recommended Project Structure (Best Practices)

```text
my-class-project/
├── public/                  # Static files (images, icons, fonts)
├── src/
│   ├── app/                 # App Router
│   │   ├── (auth)/          # Route Group
│   │   ├── (dashboard)/     # Route Group
│   │   ├── api/             # API Routes
│   │   ├── layout.tsx       # Root Layout
│   │   └── page.tsx         # Homepage
│   ├── components/
│   │   ├── ui/              # Small reusable UI (Button, Input etc.)
│   │   └── common/          # Navbar, Footer, Card etc.
│   ├── hooks/               # Custom hooks
│   ├── lib/                 # Utilities, configs, prisma client etc.
│   ├── services/            # API calling logic
│   ├── store/               # State management (Zustand/Redux)
│   └── types/               # TypeScript types
├── .env.local
├── next.config.js
├── tailwind.config.ts
└── README.md
```

---

## 🧩 6. Understanding Components & JSX

Next.js mein har cheez **Component** hoti hai. Components ko likhne ke liye hum **JSX** use karte hain.

### Basic Component Example:

```tsx
export default function WelcomeMessage() {
  return <h1>Hello, Students! Welcome to Next.js</h1>;
}
```

### JSX Rules (Yaad rakhne wali baatein):

- Saara JSX ek single parent element ke andar hona chahiye
- HTML `class` → JSX mein `className`
- Self-closing tags: `<img />`, `<br />`
- JavaScript use karne ke liye `{ }` curly braces

### Server Component vs Client Component

| Feature              | Server Component (Default)      | Client Component                  |
|----------------------|----------------------------------|------------------------------------|
| Performance          | Bahut Fast                       | Thoda slow                         |
| Interactivity        | Nahi (sirf data show)            | Haan (buttons, forms, events)      |
| "use client"         | Nahi likhte                      | File ke top par likhna zaroori     |
| Best Use             | Data fetching & rendering        | User interaction                   |

**Client Component banane ke liye:**
```tsx
"use client";

export default function Counter() {
  // interactivity code
}
```

---

## ✅ Practical Task (Class ke liye)

1. `src/components` folder banayein
2. Usme `Header.tsx` aur `Footer.tsx` components banayein
3. `app/page.tsx` mein dono ko import karke use karein

**Example:**
```tsx
import Header from '@/components/Header';
import Footer from '@/components/Footer';

export default function Home() {
  return (
    <>
      <Header />
      <main>Welcome to my First Next.js Project!</main>
      <Footer />
    </>
  );
}
```

---

**Pro Tips for Students:**
- Hamesha **Latest Stable Next.js** use karein
- **App Router** + **`src/`** directory ko enable rakhein
- Chhote-chhote reusable components banayein
- Clean code aur proper folder structure follow karein

---

