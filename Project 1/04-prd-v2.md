# Kinpay Shared Money: Product Requirements Document

| | |
|---|---|
| **Product** | Kinpay, a money app for friends, roommates and groups |
| **Document** | PRD v2.0 |
| **Release** | August 2026 |
| **Platform** | iOS, dark theme by default |
| **Status** | Released |
| **Owner** | Nikunj Chauhan, Product Designer |
| **Audience** | Product, Design, Engineering, Compliance, Support |
| **Builds on** | [PRD v1.0, January 2026](03-prd-v1.md) |

> **Concept disclaimer.** Kinpay is an original portfolio concept. It is not affiliated with any company. Numbers are planning assumptions, not measured results. Requirements marked *(designed)* are the author's own design.

## 1. Executive summary

Version 1 got people paying and asking. Version 2 makes Kinpay **the place where friends and groups manage money together**.

**What is new**

- **Conversations.** Every friend and group has a thread where payments, requests, notes and reactions live together.
- **Real splitting.** Split a bill by amount, percent or share.
- **Settle up.** Remind everyone at once, mark cash payments as paid, and use Smart settle to cut the number of payments.
- **Control.** Clear privacy settings for discovery, messaging and groups.

## 2. Why version 2

### 2.1 What v1 taught us (assumptions to validate)
| Observation | Consequence |
|---|---|
| A link request has no context once sent | People forget it and chase in chat anyway |
| Equal split is wrong for many bills | Users go back to a calculator |
| Reminders are manual, one person at a time | The organiser carries the social cost |
| Balances are scattered across groups | Nobody knows what they owe in total |
| Conversation about money happens in other apps | We lose context and the record |

### 2.2 Opportunity
Groups are where repeat use happens. Making groups fair, clear and low effort is the path from occasional payments to a weekly habit.

## 3. Goals, non-goals and principles

### 3.1 Goals
| Goal | Measure |
|---|---|
| Every payment and request lives in a thread with note, status and history | Payments started from a thread |
| A group can split any bill three ways and settle with fewer payments | Groups with a split bill, Smart settle use |
| Groups clear their balances faster | Median days to settled up |
| Users control who can find, message and add them | Privacy settings viewed, complaints |

### 3.2 Non-goals for v2

- Receipt scanning and line-item splits.
- More than one payer per bill.
- Multi-currency groups.
- A cross-group balance overview (candidate for v2.1, see the evolution document).
- Investing, cards, perks and plans.

### 3.3 Design principles (carried from v1, plus two)

1. Clear before clever.
2. Money is never a surprise.
3. No dead ends.
4. Respect the awkwardness.
5. **Context travels with money.** A payment always carries its reason.
6. **Effort belongs to the product, not the organiser.** Reminders and settling are automated or one tap.

## 4. Users

| Persona | What changed since v1 |
|---|---|
| **Aarav, roommate** | Wants recurring shared bills and fewer reminders |
| **Meera, organiser** | Wants unequal splits and an at-a-glance view of who has paid |
| **Kabir, occasional** | Wants to reply and react where the payment is |
| **Isha, trip planner (new)** | Wants one group for a whole trip with a clear end |

## 5. Scope and priority

| Priority | Features |
|---|---|
| **P0** Must | Payments tab with conversations, thread bubbles, request and send in thread, groups with split modes, settle up, member rules |
| **P1** Should | Smart settle, privacy controls, Home "Owes you" card, GIFs and reactions, blocked payments |
| **P2** Later | Cross-group overview, choose who paid, receipt split, auto reminders |

Carried from v1: signup and verification, send, link requests, scheduling, history, support.

## 6. Key user stories and acceptance criteria

| Story | Acceptance criteria |
|---|---|
| As a user, I see every payment, request and message with a friend in one thread. | Items sort by time. Each shows amount, note, status. |
| As a user, I can swipe a contact to request or send. | Swipe reveals Request and Send. Amount screen opens with the contact preselected. |
| As an organiser, I can split a bill by amount, percent or share. | Shares must add up to the bill. The difference is shown live. Confirm is disabled until it matches. |
| As an organiser, I can remind everyone who owes me with one action. | Select members, send, and see "Reminded" in group details. |
| As an organiser, I can mark a share as paid when cash changed hands. | A confirmation sheet appears. The action is logged with date and user. |
| As a member, I can turn on Smart settle. | A one-line explanation shows. A preview of "who pays whom" shows before applying. |
| As a user, I can control who adds me to groups. | A toggle in Privacy. When off, others cannot add me. |

## 7. Functional requirements

### 7.1 Payments tab
| ID | P | Requirement |
|---|---|---|
| F-801 | P0 | List of conversations sorted by latest activity, with a one-line summary such as "You requested ₹500". |
| F-802 | P0 | Search, with filters Friends, Accounts, Groups, Cards. |
| F-803 | P0 | Swipe a row to reveal Request and Send. |
| F-804 | P1 | Top bar with scan-to-pay and add contact. |
| F-805 | P1 | Entry to scheduled and blocked payments. |

### 7.2 Conversation thread
| ID | P | Requirement |
|---|---|---|
| F-811 | P0 | Payments and requests appear as bubbles with amount, note and status. |
| F-812 | P0 | A sent request shows Cancel until it is paid. |
| F-813 | P1 | Messages are encrypted. Payment details stay visible to the app for fraud checks, and the thread says so. |
| F-814 | P1 | GIFs and emoji reactions. |
| F-815 | P0 | Request and Send stay above the keyboard. |
| F-816 | P1 | If messaging is unavailable for a contact, explain why. Payments still work. |
| F-817 | P0 | Payments to non-users fall back to a payment link. |

### 7.3 Request and send
| ID | P | Requirement |
|---|---|---|
| F-821 | P0 | Quick-amount chips and a calculator keyboard. |
| F-822 | P1 | A note field that accepts text or a GIF. |
| F-823 | P0 | Review screen with the trust warning and a fee line. |
| F-824 | P0 | Confirmation sheet: "Are the payee and details correct? Once confirmed, the payment can't be unsent." |
| F-825 | P1 | "Send again" and "Schedule" on a sent payment. |

### 7.4 Groups
| ID | P | Requirement |
|---|---|---|
| F-831 | P0 | Create a group: members, name (up to 25 characters), cover photo, label chips (Home, Friends, Family, Holiday, Party, Celebration). |
| F-832 | P0 | Group currency is set once at creation. |
| F-833 | P1 | Smart settle toggle, off by default, with a one-line explanation. |
| F-834 | P0 | The thread header shows the user's net position, such as "You're owed ₹674" or "You are settled up". |
| F-835 | P0 | "Add a bill" and "Settle up" actions sit above the message box. |
| F-836 | P0 | Group details: members, each member's balance, total spent by group, total spent by you, currency, Smart settle, report an issue, leave. |

### 7.5 Split bill
| ID | P | Requirement |
|---|---|---|
| F-841 | P0 | Choose a past transaction or create a custom bill. |
| F-842 | P0 | Show who paid. |
| F-843 | P0 | Three modes: Amount, Percent, Share. |
| F-844 | P0 | Tick members in or out of the bill. |
| F-845 | P0 | Shares must add up to the bill. Show the difference live. |
| F-846 | P0 | Rounding: spread leftover paise so no two shares differ by more than one paisa. |
| F-847 | P0 | After confirming, post a bubble in the group thread: "You lent ₹674". |

### 7.6 Settle up
| ID | P | Requirement |
|---|---|---|
| F-851 | P0 | List members who owe, with amounts. |
| F-852 | P0 | Remind sends a reminder to selected members. Group details show "Reminded". |
| F-853 | P0 | Mark as paid clears a share paid outside the app, after a confirmation sheet. |
| F-854 | P1 | With Smart settle on, show consolidated "who pays whom" amounts and a before and after count. |
| F-855 | P0 | A member can pay their share in the app, which updates all balances. |

### 7.7 Members
| ID | P | Requirement |
|---|---|---|
| F-861 | P0 | Add members from friends or search. Pending members show "Invite sent". |
| F-862 | P0 | Remove a member with a confirmation sheet. |
| F-863 | P0 | Removal and leaving are blocked while balances are open. Explain which balance. |
| F-864 | P1 | Blocking a person is blocked while they share a group with the user. |

### 7.8 Home
| ID | P | Requirement |
|---|---|---|
| F-871 | P1 | An "Owes you" card shows person, amount, note and status, with Remind and Cancel. |

### 7.9 Privacy and safety
| ID | P | Requirement |
|---|---|---|
| F-881 | P1 | Make me discoverable by phone and handle: on or off. |
| F-882 | P1 | Messaging with friends: on or off. |
| F-883 | P1 | Allow others to add me to groups: on or off. |
| F-884 | P1 | Show full name and picture in search: on or off. |
| F-885 | P0 | Block and report a contact. |
| F-886 | P1 | Require authentication for each transfer to a chosen friend. |

### 7.10 Scheduled and blocked payments
| ID | P | Requirement |
|---|---|---|
| F-891 | P1 | One screen for upcoming transfers and subscriptions. |
| F-892 | P1 | Pause, resume, edit and delete a scheduled payment. |
| F-893 | P1 | Block a recurring merchant payment and unblock it later. |

## 8. Key flows

1. **Pay inside a thread:** Payments → Friend → Send → Amount and note → Review → Confirm → Bubble
2. **Request with a GIF:** Payments → Swipe → Request → Amount → Note or GIF → Send → Bubble with Cancel
3. **Create a group and split:** New → Group → Members → Name, cover, currency → Create → Add a bill → Pick transaction → Choose mode → Split → Bubble
4. **Settle up:** Group → Settle up → Select members → Remind or Mark as paid → Confirm
5. **Leave a group:** Details → Leave group → Blocked if balance open → Settle first

## 9. Edge cases and states

| Situation | Behaviour |
|---|---|
| Shares do not add up | Disable "Split with group" and show the difference |
| Payer is someone else | Out of scope in v2, a known gap |
| Member is not on Kinpay | They receive a link and show as "Invite sent" |
| Member ignores reminders | Organiser can mark as paid or contact support |
| Messaging disabled by a contact | Explain in the thread. Payments still work |
| Leave or remove with open balance | Blocked with explanation |
| Block a person in a shared group | Blocked until they leave the group |
| Payment declined or insufficient funds | Error sheet with retry and add-money action |
| Offline | Blocking message and retry |
| Duplicate request for the same bill | Warn before sending |
| Smart settle turned on with existing bills | Recompute and preview before applying |

## 10. Non-functional requirements

| Area | Requirement |
|---|---|
| Performance | Thread opens within 400 ms with the last 50 items. Split calculation is instant. |
| Accessibility | WCAG 2.1 AA in the dark theme. Contrast 4.5:1 for text on dark surfaces. Reaction and GIF content has text alternatives. Reduce Motion respected. |
| Security | As v1, plus encrypted messages and per-friend authentication. |
| Privacy | Discoverability off by default. Reports and blocks reviewed by Support. |
| Moderation | GIF content filtered. Abuse reports triaged within 24 hours. |
| Reliability | 99.9% monthly availability. Messaging outage must not block payments. |
| Localisation | English, Hindi and Gujarati strings. Bubbles handle long names and scripts. |

## 11. Content and tone

- Bubbles read like people: "You asked Meera for ₹450", "Meera paid you ₹450".
- Reminders stay neutral and never shame.
- Smart settle copy explains the result first, the method second.

## 12. Analytics plan

| Event | Properties | Used for |
|---|---|---|
| thread_opened | type (friend, group) | Engagement |
| payment_started | source (thread, swipe, scan) | Path to payment |
| split_created | mode, members, bill size band | Split adoption |
| split_mode_changed | from, to | Mode usefulness |
| reminder_sent | group, count | Chasing effort |
| marked_as_paid | by, amount band | Cash settling |
| smart_settle_toggled | on or off, payments before and after | Value of Smart settle |
| group_settled | days since first bill | Time to settle |
| privacy_setting_changed | setting, value | Privacy awareness |
| block_attempt_refused | reason | Rule clarity |

## 13. Success metrics

| Metric | v1 | v2 target (90 days) | Source |
|---|---|---|---|
| Users opening a thread each week | n/a | 70% of active users | thread_opened |
| Payments started from a thread | n/a | 60% | payment_started |
| Groups with at least one split bill | 15% of users have a group | 50% of groups | split_created |
| Median days to settled up | Baseline | 35% lower than v1 | group_settled |
| Reminders per settled group | Baseline | 30% lower than v1 | reminder_sent |
| Requests paid within 3 days | 60% | 75% | request_paid |
| Groups using Smart settle | n/a | 40% | smart_settle_toggled |
| Support contacts about "who owes what" | Baseline | 40% lower | Support tool |

## 14. Assumptions and dependencies

| # | Item |
|---|---|
| A1 | The v1 assumptions still hold: India, ₹, partner rails. |
| A2 | Users accept messaging inside a payments app if privacy is clear. |
| A3 | Smart settle can be shown with a clear preview. |
| D1 | Messaging service with encryption, ready by May 2026. |
| D2 | GIF provider contract and content filter, ready by May 2026. |
| D3 | Moderation tooling and Support training, ready by July 2026. |

## 15. Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Abuse in messages | Medium | High | Block, report, defaults off for discovery, moderation |
| Users distrust Smart settle | Medium | Medium | Preview before applying, audit trail, off by default |
| "Mark as paid" misuse | Medium | Medium | Log who and when, visible to all members |
| Thread clutter hides balances | Medium | Medium | Net position in header, Settle up always visible |
| Messaging outage affects trust | Low | High | Payments independent of messaging |

## 16. Release plan

| Phase | Date | Content | Exit criteria |
|---|---|---|---|
| Design and research | January to March 2026 | Interviews, prototype tests | Task success above 85% |
| Closed beta | May 2026 | Threads, request and send | No P0 bugs, error rate below 2% |
| Beta 2 | June to July 2026 | Groups, split modes, settle up | Split accuracy 100% in tests |
| **Public launch** | **August 2026** | Smart settle, privacy controls, Home card | All P0 and P1 pass QA, Compliance and Support sign-off |

**Rollback.** Feature flags for threads, split modes and Smart settle. Messaging can be turned off remotely while payments continue.

## 17. Open questions

1. Should the payer be selectable, so another person can have paid?
2. Should Smart settle be on by default for new groups?
3. How do we handle a group with several currencies, for trips abroad?
4. Do we show a group overview on Home when a user belongs to many groups?

## 18. Glossary and revision history

| Term | Meaning |
|---|---|
| Thread | The conversation with one friend or one group |
| Bubble | One payment, request or message in a thread |
| Smart settle | Reduces the number of payments needed to clear a group |
| Mark as paid | Clears a share that was paid outside the app |
| Net position | What you are owed minus what you owe in a group |

| Version | Date | Change |
|---|---|---|
| 1.9 | July 2026 | Beta 2 scope frozen |
| 2.0 | August 2026 | Public launch |
