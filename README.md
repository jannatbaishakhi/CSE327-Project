# SplitWise+

> Shared money, without the shared headache.

SplitWise+ is a full-stack collaborative financial workspace for groups that share expenses, plans, and decisions. Built BDT-first, it covers everything from splitting a dinner bill to settling a multi-week trip — with a real-time messaging system, a simulated payment flow, and a personal dashboard that keeps every member in the loop.

---

## Features

### Expenses & Splits
- Add expenses with a title, amount, category, date, and note
- Choose payer from group members with colorful avatar picker
- Three split modes: **Equal**, **Exact amount per person**, or **Percentage**
- Rounding-safe participant share calculation (last person absorbs remainder)
- Attach a receipt (JPG, PNG, WEBP, or PDF) on creation
- Paginated expense ledger with category filters, month filter, and sort by date
- Click any row for a full expense detail modal (participants, receipt download/view)

### Settlement & Payments
- Optimized settlement plan: fewest transfers to close group balances
- Group owners can request a settlement on behalf of any two members
- Members can request settlement for money owed to them
- Simulated payment modal (bKash, Nagad, Card, Bank Transfer) — no real gateway needed
- Settlement reference number (SIM-xxxxx) generated on payment
- Notification sent to the payer on request, and to the payee on payment

### Messaging
- Group thread and private DMs for every group member
- Near-real-time message delivery via 3-second background polling
- Images, videos, and file attachments stored as local session blob URLs
- Reactions (toggle per user), reply threading with preview, read receipts
- Searchable inbox, shared-media gallery, theme cycling (Lime / Midnight / Soft)
- Message detail panel with file/link gallery

### Planning
- **Events**: create group events with date, location, budget; RSVP support
- **Polls**: publish a decision question with custom options; group voting
- **Recurring expenses**: schedule weekly/monthly/quarterly shared costs with one-click generation
- Dedicated full-page view for each (Events in Plan, Budgets, Recurring, Documents, Activity)

### Budgets & Documents
- Create spending-limit budgets per category; track % used with live spend calculation
- Documents page shows all expenses with attached receipts; open in new tab or download
- Activity log with full group history, paginated

### Notifications & Invitations
- Announcement banner for incoming group invitations (dismiss, accept, decline)
- Bell icon lights up only when there are unread notifications or pending invitations
- 10-second background poll keeps notification state fresh without page reload

### Personal Dashboard
- Per-user summary: total shared spend, amount paid, share owed, pending settlements
- Bar charts for spend by group and money position
- Quick access to all groups and next-steps

### Authentication & Sessions
- JWT-based signup and signin; automatic silent token refresh on 401
- Session-aware authentication: every session gets a unique key, revocable individually
- Active sessions list, per-device revocation, and sign-out-everywhere
- Profile settings: avatar upload, bio, status, and theme (dark/light) persisted to account

### Quick Access
- Create a budget, poll, recurring expense, or group event from a single page
- Live settlement summary and sync button

---

## Tech stack

| Layer | Stack |
|---|---|
| Frontend | React 19, TypeScript, Vite, Lucide React |
| Backend | Django 5, Django REST Framework, Django Channels, Daphne |
| Auth | `djangorestframework-simplejwt` + session-aware JWT middleware |
| Database | SQLite |
| Storage | Django `default_storage` for avatars, receipts, and chat attachments |


---

## Getting started

### Frontend

```bash
cd frontend
pnpm install        
pnpm run dev        
```

The frontend works standalone in demo mode — no backend required to explore the UI.

### Backend

```bash
cd backend
pip install -r requirements.txt
python manage.py migrate
python manage.py seed_demo        
python manage.py runserver     
```


## Demo accounts


Username: rafi
Password: splitwise-demo-123

