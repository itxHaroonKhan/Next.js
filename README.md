

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

# 🧬 Master Prop Passing & Prop Drilling in Next.js

Jab hum components banate hain, toh hamein data ek component se dusre component mein bhejna parta hai. Is process ko hum **Props** (Properties) kehte hain.

---

## 1. What is Prop Passing? (Data Bhejna)
Prop passing ka matlab hai Parent component se Child component ko data transfer karna. Props **read-only** hote hain, yani child component unhe khud change nahi kar sakta.

### Example:
**Parent Component (`page.tsx`):**
```javascript
import Child from "./Child";

export default function Parent() {
  return (
    <div className="p-5 border">
      <h1>I am Parent</h1>
      {/* 'name' prop pass kiya ja raha hai */}
      <Child name="Zeeshan" />
    </div>
  );
}
```

**Child Component (`Child.tsx`):**
```javascript
export default function Child(props) {
  return (
    <div className="p-3 bg-blue-100">
      <h3>I am Child, Hello {props.name}!</h3>
    </div>
  );
}
```

---

## 2. What is Prop Drilling? (The Problem)
Prop drilling tab hoti hai jab aapko data ek aise component ko bhejna ho jo tree mein bohot niche hai, aur aapko beech wale components se wo data guzarna pare jo us data ka istemal bhi nahi kar rahe.



### Example of Prop Drilling:
1. **Parent** ke paas data hai.
2. **Child** ko data nahi chahiye, lekin usse guzarna par raha hai.
3. **GrandChild** ko asliyat mein data chahiye.

```text
Parent (Data: "Laptop") 
   └── Child (Sirf pass kar raha hai) 
          └── GrandChild (Data use kar raha hai)
```

**Nuksan:** Code ganda ho jata hai aur manage karna mushkil hota hai.

---

## 3. How to Avoid Prop Drilling? (The Solutions)
Agar data bohot zyada deep levels tak bhejna hai, toh hum ye tareeqe use karte hain:

1. **Component Composition:** Child components ko directly Parent mein wrap kar dena.
2. **Context API:** Ek "Global Store" banana jahan se koi bhi component directly data utha sake.
3. **State Management Libraries:** Bada project ho toh **Zustand** ya **Redux** use karna.

---

## 🛠️ Classroom Task for Students:

**Target:** Ek "User" ka naam Parent se GrandChild tak pass karein.

1. **`Parent.tsx`**: Define a variable `const user = "Ali"`.
2. **`Middle.tsx`**: Receive `user` as prop and pass it to `End`.
3. **`End.tsx`**: Display the `user` name.

### Practice Challenge:
Kya aap beech wale `Middle.tsx` component ko bypass kar sakte hain? (Hint: Use Context API later).

---

## 💡 Key Takeaway:
* **Prop Passing** achi cheez hai (2-3 levels tak).
* **Prop Drilling** se bachna chahiye (agar 4+ levels hon).
```

---

# 🛣️ Mastering Next.js Routing (App Router)

Next.js mein routing "File-system" par mabni hoti hai. Yani jo folder ka naam hoga, wahi aapki website ka URL ban jayega.

---

## 1. Basic Routing
Har folder ke andar ek `page.tsx` file hona zaroori hai taaki wo URL accessible ho.

* `app/page.tsx`  -->  `domain.com/` (Home)
* `app/about/page.tsx`  -->  `domain.com/about`
* `app/contact/page.tsx`  -->  `domain.com/contact`

---

## 2. Dynamic Routes (Slug) 🔄
Jab aapko aise pages chahiye hon jinka data change hota rahe (jaise Product ID ya Blog Title), toh hum **Square Brackets `[]`** use karte hain.

* **Folder Structure:** `app/blog/[slug]/page.tsx`
* **URL Example:** `domain.com/blog/react-guide` ya `domain.com/blog/nextjs-tips`

### Code Example:
```tsx
// app/blog/[slug]/page.tsx
export default function BlogPost({ params }: { params: { slug: string } }) {
  return <h1>Reading Blog: {params.slug}</h1>;
}
```

---

## 3. Route Groups `()` 📁
Kabhi kabhi humein folders sirf organization ke liye chahiye hote hain, URL mein dikhane ke liye nahi. Iske liye hum **Parentheses `()`** use karte hain.

* **Folder:** `app/(auth)/login/page.tsx`  -->  URL: `domain.com/login` (auth skip ho jayega)
* **Folder:** `app/(auth)/signup/page.tsx` -->  URL: `domain.com/signup`

**Fayda:** Aap `(auth)` folder ke liye ek alag `layout.tsx` bana sakte hain jo sirf login/signup par dikhega.

---

## 4. Nested Routing 📂
Ek folder ke andar dusra folder banane ko nested routing kehte hain.

* `app/dashboard/settings/page.tsx` --> `domain.com/dashboard/settings`

---

## 5. Catch-all Segments `[...slug]` 🎒
Agar aap chahte hain ke ek hi file saare sub-URLs ko handle kare, toh `...` ka use karein.

* **Folder:** `app/docs/[...slug]/page.tsx`
* **Matches:** `/docs/intro`, `/docs/intro/setup`, `/docs/intro/setup/config` wagera.

---

## 6. Navigation (Links & Router) 🚀

Next.js mein ek page se dusre page par jaane ke do tarike hain:

### A. Link Component (Recommended)
```tsx
import Link from 'next/link';

<Link href="/about">About Us</Link>
```

### B. useRouter Hook (Client Components)
```tsx
"use client";
import { useRouter } from 'next/navigation';

const router = useRouter();
<button onClick={() => router.push('/dashboard')}>Go to Dashboard</button>
```

---

## 🛠️ Summary Table

| Route Type | Folder Structure | URL Example |
| :--- | :--- | :--- |
| **Static** | `app/about/page.tsx` | `/about` |
| **Nested** | `app/blog/first-post/page.tsx` | `/blog/first-post` |
| **Dynamic** | `app/product/[id]/page.tsx` | `/product/123` |
| **Group** | `app/(marketing)/home/page.tsx` | `/home` |
| **Catch-all**| `app/shop/[...all]/page.tsx` | `/shop/clothes/men/shirts` |

---

## 💡 Pro Tip for Class:
Students ko batayein ke Next.js mein **`layout.tsx`** ka use kar ke hum Header aur Footer ko preserve kar sakte hain, taaki jab page change ho toh sirf content change ho, header reload na ho.
```

---
