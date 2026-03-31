# 💸 Smart Expense Splitter

> A premium AI-powered expense splitting web app built for the NeevAI SuperCloud internship assignment.

![Smart Expense Splitter](https://img.shields.io/badge/React-18-blue?logo=react) ![Vite](https://img.shields.io/badge/Vite-5-purple?logo=vite) ![Tailwind CSS](https://img.shields.io/badge/Tailwind-3-teal?logo=tailwindcss) ![Recharts](https://img.shields.io/badge/Recharts-2-orange)

---

## ✨ Features

### Core
- **Group Management** — Create groups, add/remove members dynamically with avatars
- **Expense Tracking** — Add expenses with description, amount, payer selection
- **Equal & Custom Splits** — Toggle between equal split and custom amounts per person
- **Real-time Balances** — Auto-computed who owes whom
- **Settlement Suggestions** — Minimal transaction algorithm for settling up
- **Delete Expenses** — Remove expenses with expandable detail view

### AI-Powered
- **Smart Categorization** — Auto-detects category (food, travel, rent, etc.) from description
- **Spending Insights** — AI-generated cards like "You spent 30% more on travel"
- **Visual Analytics** — Stacked area chart, pie chart, bar chart with 6-month trends

### UI/UX
- **Glassmorphism Design** — Frosted glass cards with mesh gradient backgrounds
- **Dark Mode** — Full dark mode with localStorage persistence
- **Responsive** — Sidebar on desktop, bottom nav on mobile
- **Animations** — Slide-up, fade-in, scale-in transitions throughout
- **Toast Notifications** — Success/error/info feedback
- **Loading Skeletons** — Shimmer placeholders
- **FAB Button** — Floating action button with hover scale animation

---

## 🚀 Setup & Running Locally

### Prerequisites
- Node.js 18+
- npm or yarn

### Installation

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/smart-expense-splitter.git
cd smart-expense-splitter

# Install dependencies
npm install

# Start dev server
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

### Build for Production

```bash
npm run build
npm run preview   # preview the production build
```

---

## 🏗 Architecture

```
src/
├── components/
│   ├── AddExpenseModal.jsx   # Expense creation with AI categorization + split preview
│   ├── Analytics.jsx         # Charts (area, pie, bar) + AI insight cards
│   ├── Avatar.jsx            # Member avatar with initials + color
│   ├── BalanceSummary.jsx    # Balance bars + settlement suggestions
│   ├── ExpenseList.jsx       # Timeline-style expense cards (expandable)
│   ├── GroupModal.jsx        # Add/remove members
│   ├── Sidebar.jsx           # Desktop sidebar + mobile bottom nav
│   └── StatsCards.jsx        # Gradient summary cards
├── data/
│   └── mockData.js           # Constants, mock data, balance/settlement algorithms
├── hooks/
│   └── useToast.jsx          # Toast notification context + provider
├── App.jsx                   # Root component, state management
├── main.jsx                  # React entry point
└── index.css                 # Global styles, glassmorphism, animations
```

### Key Algorithms

**Balance Computation** (`computeBalances`):
- For each expense, the payer gains the share amounts from each other participant
- Each participant's balance decreases by their share
- Net result: positive = owed money, negative = owes money

**Settlement Algorithm** (`computeSettlements`):
- Greedy two-pointer approach on sorted creditors and debtors
- Produces minimal number of transactions to settle all debts

**AI Categorization** (`categorizeByAI`):
- Regex-based keyword matching on expense description
- Detects: food, travel, rent, entertainment, utilities, other

---

## 🌐 Deployment

### Vercel (Recommended)
```bash
npm install -g vercel
vercel --prod
```

### Netlify
```bash
npm run build
# Drag and drop the `dist/` folder to Netlify dashboard
# Or: netlify deploy --prod --dir=dist
```

---

## 🧪 Tech Stack

| Tool | Purpose |
|------|---------|
| React 18 + Vite | UI framework + build tool |
| Tailwind CSS 3 | Utility-first styling |
| Recharts | Charts (area, bar, pie) |
| Lucide React | Icon library |
| Framer Motion | Animations (optional enhancement) |
| localStorage | Dark mode persistence |

---

## 📊 Evaluation Criteria Coverage

| Criteria | Implementation |
|---------|---------------|
| Feature Completion | Groups, expenses, equal/custom splits, balances, settlements, delete |
| Code Quality | Modular components, reusable hooks, separation of concerns |
| Real-Time Performance | Derived state via `useMemo`, no unnecessary re-renders |
| AI Accuracy | Regex-based categorization + spending insight generation |
| UX & UI | Glassmorphism, dark mode, animations, mobile-first responsive |
| Bonus | AI insights, charts, settlement algorithm, toast system |

---

## 📹 Demo

> [Add your demo video link here]

---

*Built with ❤️ for NeevAI SuperCloud Pvt. Ltd. Internship Assignment 2026*
