# Project 1: Reference screenshot analysis

Internal research notes. The source app is called "the reference app" throughout. The portfolio project must not use its name, logo or brand colours. Screenshot numbers refer to the files in the 2023 and 2025 folders.

- **2023 set:** 596 screens, iOS, Singapore account, light mode default.
- **2025 set:** 656 screens, iOS, Singapore account, dark mode default.

## 1. What the app is

A mobile money app that combines:

- A current account with multi-currency balances
- Cards (physical, virtual, disposable)
- Peer payments
- Investing (stocks, robo-advisor, commodities, crypto)
- Lifestyle perks (cashback shops, eSIM, lounges, donations)
- A teen account for ages under 18
- Subscription plans (Standard, Premium, Metal)

Most of it is irrelevant to a "split expenses with friends" project. The sections below mark what matters.

## 2. Structure of the 2023 version (light)

| Screens | Area |
|---|---|
| 001-053 | Splash, welcome carousel, phone and OTP signup, name, date of birth, address, email, passcode, ID document and selfie check, purpose selection, plan selection, card order, PIN, checkout |
| 054-112 | Home (account, cards, linked, stocks, vaults tabs), widgets, coach marks, themes and backgrounds, analytics, categories |
| 113-155 | Add money, card checkout, virtual card creation, card settings, spend limit, linking a bank |
| 156-282 | Investing: disclosure, tax forms, stock detail, orders, watchlists, news, corporate events |
| 283-322 | Vaults (savings pots): create, spare change, goals, recurring funding, invite friends, close |
| 323-350 | Exchange currency, account details, statement, converter |
| **351-392** | **Transactions list, "Who to pay", bank recipient, send, schedule, recurring transfer, friend profile, invite friends, request via payment link** |
| 393-407 | Hub (feature grid), Pockets for bills |
| 408-462 | Under-18 account: child details, allowance, challenges, goals, card customising |
| 463-546 | Shops and cashback, donations, gift sending, lounges, flight tracking, ATMs, plan management and downgrade |
| 547-596 | Profile, legal, app settings, appearance, security and privacy, support chat, login |

Navigation in 2023 is three tabs (Home, Transfer, Hub), later five (Home, Invest, Transfers, Crypto, Lifestyle).

## 3. Structure of the 2025 version (dark)

Navigation is five tabs: **Home, Invest, Payments, Crypto, Lifestyle**. The Transfer tab is now Payments.

| Screens | Area |
|---|---|
| 001-070 | Onboarding, identity check, plan and card choice, card customising |
| 071-126 | Home with hero balance, quick actions (Add money, Move, Details, More), add money, move money, statement, converter, transactions, transaction detail |
| 127-210 | Card controls, under-18 account, allowance, challenges, Pockets and goals |
| 211-262 | Total wealth, analytics, budgets, categories, preferences |
| 263-392, 522-543 | Invest and crypto (not relevant) |
| **393-434** | **Payments tab: contacts list, scheduled payments, blocked payments, subscriptions** |
| **435-476** | **New payment, add recipient, send, review transfer, tracking, chat-style payment thread, GIFs, reactions, friend profile** |
| **477-518** | **Add friend, create group, split bill, settle up, remind, mark as paid, members, leave group, donations** |
| 544-656 | Lifestyle, plan management, support, account, privacy, passcode, login |

## 4. The part that matters: payments between people

### 4.1 2023 behaviour

- "Who to pay" is a list with search, alphabet index, Friends and Accounts filters, and links to invite a friend or add a bank recipient (353).
- Sending money is a form: amount, reference, optional schedule, review, send (356-364).
- A friend's profile shows total sent, account details and scheduled transfers (381-385).
- The "New transfer" sheet lists a **Group** option labelled "Pay expenses with friends" (386). The group screens are **not captured** in this set.
- Requesting money works through a shareable payment link with an amount and expiry (388-393). A tracker shows Link created, Paid, Received.
- Invite flow with a referral reward (373-379).
- Vaults let people invite friends to a shared pot (315-322). That is shared saving, not expenses.

### 4.2 2025 behaviour

- Payments tab is a **chat-style contact list**. Each row shows the last event, for example "You requested $10" (394-397). Swiping reveals **Request** and **Send** (396).
- Opening a contact shows a thread: sent and received payments appear as message bubbles, with a note, GIFs, emoji reactions and a text box (452-473). Request and Send sit above the keyboard.
- Request flow: amount, optional note or GIF, Request (456-461). A pending request shows a Cancel button on the bubble.
- Send flow: amount, review screen with a "Do you know and trust the payee?" warning, confirm sheet, success, then a bubble in the thread (463-467).
- Contact detail: totals sent and received, scheduled transfers, groups in common, authentication setting, block, report (474-478).
- Blocking is refused while two people share a group (481).
- Messaging can be switched off by a privacy setting, and some contacts cannot be chatted with (468).

### 4.3 2025 groups and split bill

1. **Create group** (484-491): add members from friends, name, cover photo, label chips (Home, Friends, Family, Holiday, Party, Celebration), currency, **Smart settle** toggle ("consolidate debts and reduce number of payments").
2. **Group thread** (492): empty state, "Add a bill", message box.
3. **Select bill** (493-494): pick one or more **past card or account transactions**, or "Create a custom bill".
4. **Split bill** (495-496): the payer is shown ("You paid $10.10"). Three modes: **Amount, Percent, Share**. Members are ticked in or out. Rounding shows as $3.36, $3.36, $3.38. Button: "Split with group".
5. **Result** (497-498): a bubble in the thread, "You lent $6.74". The header shows "You're owed $6.74".
6. **Settle up** (499-502): lists who owes what. Actions: **Remind** (manual) or **Mark as paid** (for cash or outside payments). Confirmation sheet, toast.
7. **Group details** (503-505): members with owed or owing amounts, expandable per person with "Reminded" status, total spent by group and by you, group currency, Smart settle toggle, report an issue, leave group.
8. **Members** (507-511): add, remove with confirmation.
9. **Leave or remove** is blocked while balances are unsettled (509, 512).
10. Home shows an **"Owes you"** card with Remind and Cancel (639).

### 4.4 Cross-cutting patterns worth noting

- Calculator keyboard for amounts, with quick-amount chips ($10 / $20 / $50 / $100).
- Bottom-sheet confirmations for every destructive or irreversible action.
- Success toast or modal after each action, plus a tracker for long operations.
- Fraud warning copy on every send to a non-friend.
- Fee line always shown, even when zero ("No fees").
- Empty states with a short sentence and one action.

## 5. Edge cases and states captured (usable as a checklist)

Good coverage in the reference:

- Wrong OTP (2025: 013)
- Blurry ID photo, too dark selfie (2023: 027; 2025: 041, 647)
- Card declined for insufficient funds (2025: 086, 116)
- Unsupported card (2025: 089)
- No connection (2025: 159)
- Amount exceeds balance, red field (2023: 240; 2025: 095)
- Minimum amount error (2023: 326)
- Pending verification (2023: 114, 330)
- Paused scheduled payment (2025: 401)
- Blocked merchant and unblock (2025: 407-413)
- Cannot leave or block while group balances are open
- Easy PIN warning (2025: 166)
- Same passcode reused (2025: 596)
- Email verification failed (2025: 588)
- Reverted transaction (2025: 406)

## 6. Gaps and pain points (opportunities for the concept)

These come from what is absent or thin in the screens. They are hypotheses to validate with research, not facts.

1. **Split happens after the fact.** The bill must already exist as a transaction the user paid with the app. There is no way to start from a restaurant receipt, split at the table, or add items.
2. **Only one payer.** The split screen assumes "You paid". There is no "Alex paid, I owe" path from the same screen.
3. **No line-item or receipt split.** Modes are Amount, Percent, Share only.
4. **No overview across groups.** Balances live inside each group. There is no single "who owes me / I owe" summary beyond one home card.
5. **Reminders are manual.** No schedule, no tone, no nudge when someone ignores a request.
6. **Group = chat.** Bills and payments are bubbles in a thread, so the history is hard to scan. Totals by category or by person are not visible.
7. **Multi-currency trips are weak.** A group has one currency. There is no per-expense currency, no rate lock for the trip, no "convert at settle".
8. **Non-users are second-class.** A friend without an account only gets a payment link. They cannot see the group or their share.
9. **Settle with cash is a bare "Mark as paid".** No proof, no partial amount, no dispute path.
10. **Partial payments and disputes are not shown.** What if someone pays less, or says the item was not theirs?
11. **Smart settle is explained in one sentence.** The result (who pays whom) is not previewed before the user opts in.
12. **Privacy surprises.** Messaging, discoverability and "allow others to add me to groups" sit deep in Security and privacy settings (2025: 598-599).

## 7. Visual and interaction observations (for building an original look)

Described so the concept can deliberately differ, not copy.

- 2023: light surfaces, soft grey input fields, one bright blue primary button, small chip filters, bottom sheets with rounded top corners, large bold headings, 3D illustration for empty states.
- 2025: near-black surfaces, white pill primary button, dark grey input fields, a gradient hero on Home that changes with the account, chat bubbles in saturated blue, numeric keyboard styled dark.
- Both: big centred amount with a currency selector underneath, grouped list cards, icon plus two-line list rows, floating success sheet.

The concept needs its own name, logo, colours, type, illustration style and component shapes.

## 8. Out of scope for the concept

Investing, crypto, robo-advisor, commodities, perks and shops, eSIM, lounges, donations, plans, cards, under-18 account, vaults and Pockets (except as inspiration for shared goals).

## 9. Open questions

1. Group flow screens are missing from the 2023 set. The 2025 set has them, so 2023 is only a reference for the older pattern.
2. Should the concept be a standalone app, or a feature inside a bank app? Real-looking Figma is easier as a standalone app with its own brand.
3. Which market and currency? Examples in the references are Singapore. The earlier notes mention Indian names and rupee amounts.
