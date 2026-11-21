# Kinpay: evolution from v1 to v2, and what comes next

| | |
|---|---|
| **Document** | Product evolution brief |
| **Covers** | v1.0 (released January 2026) and v2.0 (released August 2026) |
| **Related** | [PRD v1](03-prd-v1.md), [PRD v2](04-prd-v2.md) |
| **Owner** | Nikunj Chauhan, Product Designer |
| **Status** | Final |

> Kinpay is an original portfolio concept and has no connection to any company. Targets are assumptions, not measured results.

## 1. Summary

v1 helped people move money between friends. v2 helps friends and groups keep that money fair over time.

This brief explains what changed between the two releases, why we changed it, and what we would work on next. It is meant to be read next to the two PRDs.

## 2. What changed

| Area | v1 (Jan 2026) | v2 (Aug 2026) | Why |
|---|---|---|---|
| Navigation | Transfer tab with a contact list | Payments tab with conversations | People think about people and context, not forms |
| Request | Payment link with an expiry and a status tracker | A request bubble in a thread, with a note, GIF and Cancel | A link loses its context once it's sent |
| Send | A form: amount, reference, review | Same safety checks, started from inside the thread | Fewer steps, and the history stays in one place |
| Conversation | None | Messages, GIFs, reactions | Chasing was happening in other apps |
| Groups | Basic: equal split and a balance list | Cover, label, currency, member rules, Smart settle | Groups turned out to be the main use |
| Splitting | Equal only | Amount, percent, share | Real bills are rarely equal |
| Settling | Pay your share, remind people one at a time | Remind many, mark as paid, fewer payments with Smart settle | The organiser was doing too much of the work |
| Home | Nothing about shared money | An "Owes you" card with Remind | Keeps people aware without opening a group |
| Privacy | A few controls | Discoverability, messaging, groups, name visibility, per-friend authentication | Messaging and groups need real privacy settings |
| Blocking | Basic | Not allowed while you share a group | Avoids debts with nobody to collect them |
| Scheduled payments | A list per account | One screen for scheduled and blocked payments | Easier control of recurring money |
| Visual style | Light theme | Dark by default, chat bubbles | Mostly used in the evening, and a more social feel |

## 3. Two flows, before and after

### 3.1 Splitting a dinner

In v1 you open Groups, create a group, add the bill, and the app splits it equally. Each member then pays, or you remind them one by one.

In v2 you stay in the group thread. You tap Add a bill, pick the transaction, choose Amount, Percent or Share, and confirm. A bubble appears in the thread. Later you tap Settle up and either remind everyone or mark a share as paid. With Smart settle on, the group makes fewer payments to clear up.

### 3.2 Asking for money

In v1 you create a link, share it somewhere else, and watch a tracker.

In v2 you swipe the contact, tap Request, add a note or a GIF, and a bubble appears in the thread with a Cancel button. The reply and the payment end up in the same place.

## 4. The thinking behind the changes

**Context matters more than forms.** A payment with no reason attached leads to questions. Threads keep the reason next to the money.

**The organiser does too much.** Most of the awkwardness sits with whoever paid first. Reminders, Mark as paid and Smart settle move that effort from the person to the product.

**Equal split is a default, not an answer.** It doesn't cover drinks, a shared room, or shares based on income.

**More social features mean more ways to get it wrong.** Once people can message each other, they need ways to switch it off, so v2 adds privacy settings and blocking rules.

**The basics stay.** Fees are always visible, confirmation is always explicit, and the trust warning is still there.

## 5. Metrics we would watch

| Question | Metric | v1 target | v2 target |
|---|---|---|---|
| Do threads become the main route to a payment? | Payments started from a thread | n/a | 60% |
| Is splitting more useful? | Groups with a split bill | 15% of users have a group | 50% of groups |
| Do people get paid faster? | Requests paid within 3 days | 60% | 75% |
| Is there less chasing? | Reminders per settled group | Baseline | 30% lower |
| Do groups settle faster? | Median days to settled up | Baseline | 35% lower |
| Is support busier or quieter? | Contacts about "who owes what" | Baseline | 40% lower |

## 6. What we would do next

Every item below comes from a gap in how v2 works today. We would check each one with users before committing to it.

| # | Improvement | The problem | The idea | Size |
|---|---|---|---|---|
| 1 | Receipt and line-item split | A bill has to exist as a card transaction first, and people often split at the table | Scan or enter items, assign them to people, share tax and tip in proportion | Large |
| 2 | Choose who paid | The split screen always assumes you paid | A payer selector on every bill, so others can add bills they paid | Medium |
| 3 | Balance overview | Balances are stuck inside each group | One screen: what you owe, what you're owed, by person, across all groups | Medium |
| 4 | Smarter reminders | Reminders are manual | Scheduled, polite nudges with a choice of tone, stopping once settled | Small |
| 5 | Trip mode with several currencies | A group has one currency | Per-expense currency, a rate locked for the trip, convert once at settle | Large |
| 6 | Guest view for non-users | Friends without the app only get a link | A web page showing the group, their share and a pay button | Medium |
| 7 | Cash and partial payments | "Mark as paid" is all or nothing | Partial amounts, proof, and a way to dispute | Medium |
| 8 | Smart settle preview | People can't see the result before switching it on | Show "Before: 6 payments, after: 3" with names | Small |
| 9 | Recurring group bills | Roommates repeat the same bills | Bill templates that repeat monthly, split and remind automatically | Medium |
| 10 | Privacy at first use | The settings are buried | Ask once during onboarding, in plain language | Small |

### 6.1 Suggested order

1. Smart settle preview and smarter reminders. Both are small and quick.
2. Choose who paid, and the balance overview. These close the biggest gaps.
3. Receipt split and the guest view. These would set us apart.
4. Trip mode and recurring bills. These help growth.

## 7. How to present this in the portfolio

- Show v1 and v2 side by side with their dates, so the product has a visible history.
- Write short release notes for each version.
- Finish with a "what I would do next" slide based on section 6.
- Say once that the project is an original concept and that the targets are assumptions.

## 8. Design work this suggests

| Deliverable | v1 | v2 |
|---|---|---|
| Style | Light, calm, practical | Dark by default, more social |
| Core screens | Who to pay, Send, Review, Request link, basic Group, History | Payments list, Thread, Create group, Split bill, Settle up, Members, Privacy |
| States | Errors, pending, expired link | Smart settle preview, blocked actions, reminded, marked as paid |
| Prototype | Pay a friend, request with a link | Create a group and split, settle up |
| Design system | Tokens, buttons, inputs, sheets, list rows | Adds bubbles, avatars, chips, progress, dark theme |
