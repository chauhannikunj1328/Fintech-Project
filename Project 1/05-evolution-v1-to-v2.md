# Evolution: from v1 (2023) to v2 (2025), and what comes next

This document explains how [Brand] changed between the two releases, why, and what we would improve next. It is the story to tell in the case study: a product that grew with its users.

## 1. One-line summary

**v1 helped people move money between friends. v2 helps friends and groups keep money fair over time.**

## 2. What changed

| Area | v1 (Nov 2023) | v2 (2025) | Why |
|---|---|---|---|
| Navigation | Transfer tab with a contact list | Payments tab with conversations | People think in people and context, not in forms |
| Request | Payment link with expiry and a status tracker | Request bubble in a thread, with a note, GIF and Cancel | A link loses context after sending |
| Send | Form: amount, reference, review | Same safety, launched from inside the thread | Fewer steps, history stays in one place |
| Conversation | None | Messages, GIFs, reactions | Chasing happened in other apps |
| Groups | Basic: equal split, balances list | Cover, label, currency, member rules, Smart settle | Groups became the main use |
| Splitting | Equal only | Amount, Percent, Share | Real bills are rarely equal |
| Settling | Pay your share, manual reminder | Remind many, Mark as paid, consolidated payments | The organiser carried too much effort |
| Home | No shared money signal | "Owes you" card with Remind | Keep the user aware without opening a group |
| Privacy | Few controls | Discoverability, messaging, groups, name visibility, per-friend authentication | Messaging and groups raise privacy needs |
| Blocking | Basic | Blocked while sharing a group | Avoid orphaned debts |
| Scheduled payments | List per account | One screen for scheduled and blocked payments | Easier control of recurring money |
| Visual style | Light mode | Dark by default, gradient home hero, chat bubbles | Evening use, a more social feel |

## 3. Flow comparison

### Splitting a dinner
**v1:** open Groups → create → add bill → equal split → each member pays or is reminded one by one.

**v2:** open the group thread → Add a bill → pick the transaction → choose Amount, Percent or Share → split → bubble appears → Settle up → Remind or Mark as paid. With Smart settle, the group needs fewer payments.

### Asking for money
**v1:** create a link → share it elsewhere → watch a tracker.

**v2:** swipe a contact → Request → note or GIF → bubble in the thread with Cancel. The reply and the payment appear in the same place.

## 4. Product thinking behind the change

1. **Context beats forms.** A payment without a reason creates follow-up questions. Threads keep the reason next to the money.
2. **Remove the organiser's burden.** Most social cost sits with the person who paid. Reminders, Mark as paid and Smart settle shift effort from people to the product.
3. **Fairness needs flexible maths.** Equal split is a good default but cannot cover drinks, shared rooms or income-based shares.
4. **Safety scales with social features.** More ways to connect means more ways to abuse. v2 adds privacy switches and blocking rules.
5. **Keep the core promise.** Fees are visible, confirmation is explicit, and the trust warning stays.

## 5. Metrics we would watch

| Question | Metric | v1 target | v2 target |
|---|---|---|---|
| Do threads become the main path? | Payments started from a thread | n/a | 60% |
| Is splitting more useful? | Groups with a split bill | 15% of users have a group | 50% of groups |
| Are people paid faster? | Requests paid in 3 days | 60% | 75% |
| Is chasing reduced? | Reminders per settled group | baseline | -30% |
| Is settling faster? | Median days to settled-up | baseline | -35% |
| Is support lower? | Contacts about "who owes what" | baseline | -40% |

All numbers are concept assumptions. In the case study, call them targets, not results.

## 6. What we would improve next (v2.1 and v3 candidates)

Each item comes from a gap seen in the 2025 reference screens. Validate with research before committing.

| # | Improvement | Problem it solves | Idea | Size |
|---|---|---|---|---|
| 1 | **Receipt and line-item split** | Bills must already exist as a card transaction. People split at the table | Scan or enter items, assign each item to people, tax and tip shared proportionally | Large |
| 2 | **Choose who paid** | The screen assumes "You paid" | A payer selector on every bill, so others can add bills they paid | Medium |
| 3 | **Group and balance overview** | Balances are trapped in each group | A Money-with-friends screen: total you owe, total owed, by person, across groups | Medium |
| 4 | **Smart reminders** | Reminders are manual | Scheduled, polite nudges, adjustable tone, stop after settled | Small |
| 5 | **Trip mode with multiple currencies** | One currency per group | Per-expense currency, a rate locked for the trip, convert once at settle | Large |
| 6 | **Guest view for non-users** | Friends without the app only get a link | A web page showing the group, their share, and a pay button | Medium |
| 7 | **Cash and partial payment handling** | "Mark as paid" is all-or-nothing | Partial amounts, proof, and a dispute flow | Medium |
| 8 | **Preview for Smart settle** | Users do not see the result before choosing | Show "Before: 6 payments, after: 3" with names | Small |
| 9 | **Recurring group bills** | Roommates repeat the same bills | Template bills, monthly, with auto-split and auto-remind | Medium |
| 10 | **Privacy at first use** | Settings are buried | Ask once during onboarding, plain language | Small |

### Suggested order
1. Smart settle preview and smart reminders (small, quick wins)
2. Choose who paid, balance overview (core gaps)
3. Receipt split and guest view (differentiators)
4. Trip mode and recurring bills (growth)

## 7. How to present this in the portfolio

- Show **v1** and **v2** side by side with dates, so the product feels like it has a history.
- Use real-looking release notes for each version.
- Keep a short "what I would do next" slide from section 6. It shows product judgement.
- State once that the project is an original concept and that targets are assumptions.

## 8. Design deliverables this suggests

| Deliverable | v1 | v2 |
|---|---|---|
| Style | Light, calm, utility feel | Dark by default, social, expressive |
| Core screens | Who to pay, Send, Review, Request link, Group (basic), History | Payments list, Thread, Group create, Split bill, Settle up, Members, Privacy |
| States | Errors, pending, expired link | Smart settle preview, blocked actions, reminded, marked as paid |
| Prototype | Pay a friend, request via link | Create group and split, settle up |
| Design system | Tokens, buttons, inputs, sheets, list rows | Adds bubbles, avatars, chips, progress, dark theme |
