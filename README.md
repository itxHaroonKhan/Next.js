
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

## 🛠️ 4. Installation & Setup

### Step 1: Node.js Install Karein

Sabse pehle [nodejs.org](https://nodejs.org/) se **Latest LTS version** download aur install karein.

Check karne ke liye terminal mein:
```bash
node -v
```

### Step 2: Next.js Project Create Karein

```bash
npx create-next-app@latest my-class-project
```

**Setup ke waqt ye options select karein:**
- TypeScript → **Yes**
- ESLint → **Yes**
- Tailwind CSS → **Yes**
- `src/` directory → **Yes**
- App Router → **Yes**
- Customize import alias → **No**

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
├── public/                 # Static files (images, icons, fonts)
├── src/
│   ├── app/                # App Router
│   │   ├── (auth)/         # Route Group
│   │   ├── (dashboard)/    # Route Group
│   │   ├── api/            # API Routes
│   │   ├── layout.tsx      # Root Layout
│   │   └── page.tsx        # Homepage
│   ├── components/
│   │   ├── ui/             # Small reusable UI (Button, Input etc.)
│   │   └── common/         # Navbar, Footer, Card etc.
│   ├── hooks/              # Custom hooks
│   ├── lib/                # Utilities, configs, prisma client etc.
│   ├── services/           # API calling logic
│   ├── store/              # State management (Zustand/Redux)
│   └── types/              # TypeScript types
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
| Performance          | Bahut Fast                      | Thoda slow                        |
| Interactivity        | Nahi (sirf data show)           | Haan (buttons, forms, events)     |
| "use client"         | Nahi likhte                     | File ke top par likhna zaroori    |
| Best Use             | Data fetching & rendering       | User interaction                  |

**Client Component banane ke liye:**

```tsx
"use client";

export default function Counter() {
  // interactivity code
}
```

---

## ✅ Practical Task 1: Components

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

# 🧬 Master Prop Passing & Prop Drilling in Next.js

Jab hum components banate hain, toh hamein data ek component se dusre component mein bhejna parta hai. Is process ko hum **Props** (Properties) kehte hain.

### 1. What is Prop Passing?

Props **read-only** hote hain. Parent component se Child component ko data bheja jata hai.

**Parent Component (`page.tsx`):**

```tsx
import Child from "./Child";

export default function Parent() {
  return (
    <div className="p-5 border">
      <h1>I am Parent</h1>
      <Child name="Zeeshan" />
    </div>
  );
}
```

**Child Component (`Child.tsx`):**

```tsx
export default function Child({ name }: { name: string }) {
  return (
    <div className="p-3 bg-blue-100">
      <h3>Hello {name}!</h3>
    </div>
  );
}
```

### 2. What is Prop Drilling?

Prop drilling tab hoti hai jab data ko bohot saare intermediate components se guzarna padta hai jo us data ka istemal nahi kar rahe.

**Problem Example:**
```
Parent (Data: "Laptop")
   └── Child (sirf pass kar raha hai)
          └── GrandChild (Data use kar raha hai)
```

### 3. How to Avoid Prop Drilling?

- **Component Composition**
- **Context API**
- **State Management Libraries** (Zustand, Redux, Jotai)

---

## 🛣️ Mastering Next.js Routing (App Router)

Next.js mein routing **File-system** based hoti hai. Folder ka naam hi URL ban jata hai.

### 1. Basic Routing

- `app/page.tsx` → `/`
- `app/about/page.tsx` → `/about`
- `app/contact/page.tsx` → `/contact`

### 2. Dynamic Routes

```text
app/blog/[slug]/page.tsx
```

**Code:**

```tsx
export default function BlogPost({ params }: { params: { slug: string } }) {
  return <h1>Reading Blog: {params.slug}</h1>;
}
```

### 3. Route Groups `()`

```text
app/(auth)/login/page.tsx     → URL: /login
app/(auth)/signup/page.tsx    → URL: /signup
```

### 4. Nested Routing

```text
app/dashboard/settings/page.tsx → /dashboard/settings
```

### 5. Catch-all Routes

```text
app/docs/[...slug]/page.tsx
```

### 6. Navigation

**Using Link (Recommended):**

```tsx
import Link from 'next/link';

<Link href="/about">About Us</Link>
```

**Using useRouter (Client Component):**

```tsx
"use client";
import { useRouter } from 'next/navigation';

const router = useRouter();
<button onClick={() => router.push('/dashboard')}>Go to Dashboard</button>
```

### Summary Table

| Route Type     | Folder Structure                    | URL Example                          |
|----------------|-------------------------------------|--------------------------------------|
| Static         | `app/about/page.tsx`                | `/about`                             |
| Nested         | `app/blog/first-post/page.tsx`      | `/blog/first-post`                   |
| Dynamic        | `app/product/[id]/page.tsx`         | `/product/123`                       |
| Route Group    | `app/(marketing)/home/page.tsx`     | `/home`                              |
| Catch-all      | `app/shop/[...all]/page.tsx`        | `/shop/clothes/men/shirts`           |

---

**Pro Tips for Students:**

- Hamesha **Latest Stable Next.js** use karein
- **App Router** + **`src/`** directory enable rakhein
- Chhote reusable components banayein
- Clean code aur proper folder structure follow karein
- `layout.tsx` ka use karke Header/Footer ko preserve karein

---

**Next Steps:**
- Personal Portfolio Project banao
- Blog Application with dynamic routes
- Authentication aur Database integration seekho

---
Theek hai, CSS bilkul hata dete hain taaki aapko **logic** aur **structure** saaf samajh aaye. Jab CSS nahi hogi, toh layout hierarchy simple HTML tags ki tarah dikhegi.

Yahan aapka pura folder structure aur code hai:

### Folder Structure
```text
app/
├── layout.tsx         (Root Layout - Header/Footer)
├── page.tsx           (Home Page - /)
└── dashboard/
    ├── layout.tsx     (Nested Layout - Sidebar)
    ├── page.tsx       (Dashboard Main Page - /dashboard)
    └── settings/
        └── page.tsx   (Settings Page - /dashboard/settings)
```

---

### 1. Root Layout (`app/layout.tsx`)
Yeh aapka main wrapper hai. Isme `Header` aur `Footer` sabhi pages ke liye common hain.

```tsx
import { ClerkProvider } from "@clerk/nextjs";

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <ClerkProvider>
      <html lang="en">
        <body>
          <Header /> 
          
          {/* Yahan se children shuru hota hai */}
          <main>
            {children} 
          </main>
          
          <Footer />
        </body>
      </html>
    </ClerkProvider>
  );
}
```

---

### 2. Dashboard Nested Layout (`app/dashboard/layout.tsx`)
Yeh layout sirf `/dashboard` folder ke andar wale pages ko wrap karega. Isme humne **Sidebar** rakha hai.

```tsx
export default function DashboardLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <section>
      {/* Dashboard ka sidebar sirf yahan dikhega */}
      <aside>
        <ul>
          <li>Dashboard Home</li>
          <li>Settings</li>
        </ul>
      </aside>

      {/* Is children mein dashboard ke pages (main/settings) aayenge */}
      <div>
        {children}
      </div>
    </section>
  );
}
```

---

### 3. Dashboard Main Page (`app/dashboard/page.tsx`)
Jab user `/dashboard` par jayenge:

```tsx
export default function DashboardPage() {
  return (
    <div>
      <h1>Main Dashboard Content</h1>
      <p>Yahan aapke graphs ya stats dikhenge.</p>
    </div>
  );
}
```

---

### 4. Settings Page (`app/dashboard/settings/page.tsx`)
Jab user `/dashboard/settings` par jayenge, toh **Header**, **Footer**, aur **Sidebar** teeno dikhte rahenge:

```tsx
export default function SettingsPage() {
  return (
    <div>
      <h1>User Settings</h1>
      <p>Yahan se profile update karein.</p>
    </div>
  );
}
```

---

### Summary: Page Kaise Render Hoga?

Jab aap `/dashboard/settings` route open karte hain, toh Next.js in sab ko mix kar deta hai:

1.  **Root Layout** ka `Header` dikhega.
2.  Uske andar **Dashboard Layout** ka `Sidebar` dikhega.
3.  Uske andar **Settings Page** ka content dikhega.
4.  Sabse niche **Root Layout** ka `Footer` dikhega.



**Pro Tip:** Next.js ki khasiyat ye hai ki jab aap Dashboard ke ek page se dusre page par jayenge, toh Header aur Sidebar "Fresh" load nahi honge, wo apni jagah tike rahenge. Sirf beech ka content badlega.

Kya aapko Route Groups (jis mein `(folder)` brackets use hote hain) ke baare mein bhi jaan-na hai?
