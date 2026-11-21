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

> Kinpay is an original portfolio concept and has no connection to any company. All numbers are planning assumptions, not results. Requirements marked *(designed)* are my own design.

## 1. Summary

v1 got people paying each other and asking each other for money. What it didn't do was help groups. A group could split a bill equally, and after that everyone was on their own with reminders, cash and awkward follow-ups.

v2 goes after that. Every friend and every group now has a thread where payments, requests, notes and reactions sit together. Bills can be split by amount, percent or share. The organiser can remind everyone in one tap, mark a cash payment as paid, and turn on Smart settle so the group makes fewer payments to clear up. We also added proper privacy settings, because a thread you can message in needs them.

## 2. Why version 2

### 2.1 What v1 showed us

These are assumptions from the concept, not research results. We'd confirm each one before building on it.

| What we saw | What it meant |
|---|---|
| A link request has no context once it's sent | People forget it and chase in chat anyway |
| Equal split is wrong for a lot of bills | People go back to a calculator |
| Reminders are manual and one person at a time | The organiser carries all the awkwardness |
| Balances are spread over several groups | Nobody knows what they owe in total |
| Talking about money happens in other apps | We lose the context and the record |

### 2.2 Why groups

Groups are where repeat use happens. A one-off payment can be a one-off. A flat share or a trip goes on for months. If we make groups fair and low effort, Kinpay becomes something people open every week.

## 3. Goals, non-goals and principles

### 3.1 Goals

| Goal | How we measure it |
|---|---|
| Every payment and request lives in a thread, with its note, status and history | Payments started from a thread |
| A group can split any bill three ways and settle with fewer payments | Groups with a split bill, Smart settle use |
| Groups clear their balances faster | Median days to settled up |
| Users control who can find, message and add them | Privacy settings viewed, complaints |

### 3.2 What we are leaving out

- **Receipt scanning and line-item splits.** Real demand, but it is a project of its own. See the evolution brief.
- **More than one payer on a bill.** The split screen assumes you paid. We know that is a gap.
- **Multi-currency groups.** A trip abroad would need this. Not in v2.
- **An overview of balances across groups.** Possible in v2.1.
- **Investing, cards, perks, plans.** Outside this document.

### 3.3 Principles

We kept the four from v1 and added two:

1. One main action on each screen.
2. No surprises with money. Fees and totals come before confirmation.
3. Every error says what to do next.
4. Friendly wording, never accusing.
5. A payment should always carry its reason with it.
6. The product does the chasing, not the organiser. Reminders and settling take one tap or none.

## 4. Users

| Persona | What's different since v1 |
|---|---|
| Aarav, roommate | Wants shared bills to repeat, and fewer reminders |
| Meera, organiser | Wants uneven splits and a quick view of who has paid |
| Kabir, occasional user | Wants to reply and react where the payment is |
| Isha, trip planner (new) | Wants one group for the whole trip, with a clear end |

## 5. Scope and priority

| Priority | Features |
|---|---|
| P0 | Payments tab with conversations, thread bubbles, request and send inside a thread, groups with split modes, settle up, member rules |
| P1 | Smart settle, privacy controls, "Owes you" card on Home, GIFs and reactions, blocked payments |
| P2 | Balance overview across groups, choosing who paid, receipt split, automatic reminders |

Carried over from v1: signup and verification, send, link requests, scheduling, history, support.

## 6. Key user stories and acceptance criteria

| Story | Acceptance criteria |
|---|---|
| I can see every payment, request and message with a friend in one thread. | Items are in time order. Each shows amount, note and status. |
| I can swipe a contact to request or send. | Swiping shows Request and Send. The amount screen opens with the contact already chosen. |
| I can split a bill by amount, percent or share. | The shares must add up to the bill. The difference shows live. Confirm stays disabled until it matches. |
| I can remind everyone who owes me in one go. | Pick the members, send, and "Reminded" shows in group details. |
| I can mark a share as paid when cash changed hands. | A confirmation sheet appears. The action is logged with the date and who did it. |
| I can turn on Smart settle. | A one-line explanation shows, then a preview of who pays whom before it applies. |
| I can control who adds me to groups. | A toggle in Privacy. When it's off, nobody can add me. |

## 7. Functional requirements

### 7.1 Payments tab

| ID | P | Requirement |
|---|---|---|
| F-801 | P0 | A list of conversations sorted by latest activity, each with a one-line summary such as "You requested ₹500". |
| F-802 | P0 | Search, with filters for Friends, Accounts, Groups and Cards. |
| F-803 | P0 | Swipe a row to reveal Request and Send. |
| F-804 | P1 | Top bar with scan-to-pay and add contact. |
| F-805 | P1 | Entry point to scheduled and blocked payments. |

### 7.2 Conversation thread

| ID | P | Requirement |
|---|---|---|
| F-811 | P0 | Payments and requests appear as bubbles with amount, note and status. |
| F-812 | P0 | A sent request shows Cancel until it is paid. |
| F-813 | P1 | Messages are encrypted. Payment details stay visible to the app for fraud checks, and the thread says so. |
| F-814 | P1 | GIFs and emoji reactions. |
| F-815 | P0 | Request and Send stay above the keyboard. |
| F-816 | P1 | If messaging isn't available for a contact, explain why. Payments still work. |
| F-817 | P0 | Payments to non-users fall back to a payment link. |

### 7.3 Request and send

| ID | P | Requirement |
|---|---|---|
| F-821 | P0 | Quick-amount chips and a calculator keyboard. |
| F-822 | P1 | A note field that takes text or a GIF. |
| F-823 | P0 | Review screen with the trust warning and a fee line. |
| F-824 | P0 | Confirmation sheet: "Are the payee and details correct? Once confirmed, the payment can't be unsent." |
| F-825 | P1 | "Send again" and "Schedule" on a sent payment. |

### 7.4 Groups

| ID | P | Requirement |
|---|---|---|
| F-831 | P0 | Create a group: members, name (up to 25 characters), cover photo, and a label (Home, Friends, Family, Holiday, Party, Celebration). |
| F-832 | P0 | The group currency is set once, at creation. |
| F-833 | P1 | Smart settle toggle, off by default, with a one-line explanation. |
| F-834 | P0 | The thread header shows your net position, such as "You're owed ₹674" or "You are settled up". |
| F-835 | P0 | "Add a bill" and "Settle up" sit above the message box. |
| F-836 | P0 | Group details: members, each member's balance, total spent by the group, total spent by you, currency, Smart settle, report an issue, leave. |

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
| F-851 | P0 | List the members who owe, with amounts. |
| F-852 | P0 | Remind sends a reminder to the selected members. Group details show "Reminded". |
| F-853 | P0 | Mark as paid clears a share that was paid outside the app, after a confirmation sheet. |
| F-854 | P1 | With Smart settle on, show the consolidated "who pays whom" amounts and a before and after count. |
| F-855 | P0 | A member can pay their share in the app, which updates every balance. |

### 7.7 Members

| ID | P | Requirement |
|---|---|---|
| F-861 | P0 | Add members from friends or search. Pending members show "Invite sent". |
| F-862 | P0 | Remove a member, with a confirmation sheet. |
| F-863 | P0 | Removing or leaving is blocked while balances are open. Explain which balance. |
| F-864 | P1 | You can't block someone who shares a group with you. |

### 7.8 Home

| ID | P | Requirement |
|---|---|---|
| F-871 | P1 | An "Owes you" card showing the person, amount, note and status, with Remind and Cancel. |

### 7.9 Privacy and safety

| ID | P | Requirement |
|---|---|---|
| F-881 | P1 | Make me discoverable by phone and handle: on or off. |
| F-882 | P1 | Messaging with friends: on or off. |
| F-883 | P1 | Allow others to add me to groups: on or off. |
| F-884 | P1 | Show my full name and picture in search: on or off. |
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
5. **Leave a group:** Details → Leave group → Blocked if a balance is open → Settle first

## 9. Edge cases and states

| Situation | What happens |
|---|---|
| Shares don't add up | "Split with group" stays disabled and the difference is shown |
| Someone else paid the bill | Not supported in v2. A known gap |
| A member isn't on Kinpay | They get a link and show as "Invite sent" |
| A member ignores reminders | The organiser can mark the share as paid or contact support |
| A contact has turned messaging off | The thread explains it. Payments still work |
| Leaving or removing with an open balance | Blocked, with an explanation |
| Blocking someone in a shared group | Blocked until they leave the group |
| Payment declined or not enough money | Error sheet with retry and an add-money action |
| Offline | Blocking message and retry |
| Same request sent twice for one bill | Warn before sending |
| Smart settle switched on with bills already in the group | Recalculate and show a preview before applying |

## 10. Non-functional requirements

| Area | Requirement |
|---|---|
| Performance | A thread opens within 400 ms with the latest 50 items. Split calculation is instant. |
| Accessibility | WCAG 2.1 AA in the dark theme. Text contrast 4.5:1 on dark surfaces. GIFs and reactions have text alternatives. Reduce Motion is respected. |
| Security | As v1, plus encrypted messages and per-friend authentication. |
| Privacy | Discoverability is off by default. Reports and blocks are reviewed by Support. |
| Moderation | GIF content is filtered. Abuse reports are triaged within 24 hours. |
| Reliability | 99.9% monthly availability. A messaging outage must never block payments. |
| Localisation | English, Hindi and Gujarati strings. Bubbles handle long names and different scripts. |

## 11. Content and tone

Bubbles should read like people talking: "You asked Meera for ₹450", "Meera paid you ₹450". Reminders stay neutral and never shame anyone. For Smart settle we explain the result first and the method second, because people care about "I pay one person once" more than how the maths works.

## 12. Analytics plan

| Event | Properties | Used for |
|---|---|---|
| thread_opened | type (friend, group) | Engagement |
| payment_started | source (thread, swipe, scan) | How people get to a payment |
| split_created | mode, members, bill size band | Split adoption |
| split_mode_changed | from, to | Whether the modes are useful |
| reminder_sent | group, count | How much chasing happens |
| marked_as_paid | by, amount band | Cash settling |
| smart_settle_toggled | on or off, payments before and after | What Smart settle is worth |
| group_settled | days since first bill | Time to settle |
| privacy_setting_changed | setting, value | Privacy awareness |
| block_attempt_refused | reason | Whether the rule is clear |

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
| A2 | People will accept messaging inside a payments app if the privacy side is clear. |
| A3 | We can show Smart settle with a preview people understand. |
| D1 | Messaging service with encryption, ready by May 2026. |
| D2 | GIF provider contract and content filter, ready by May 2026. |
| D3 | Moderation tooling and Support training, ready by July 2026. |

## 15. Risks

| Risk | Likelihood | Impact | What we do about it |
|---|---|---|---|
| Abuse in messages | Medium | High | Block and report, discovery off by default, moderation |
| Users don't trust Smart settle | Medium | Medium | Preview before applying, audit trail, off by default |
| "Mark as paid" gets misused | Medium | Medium | Log who and when, visible to every member |
| Threads get long and bury the balances | Medium | Medium | Net position in the header, Settle up always visible |
| A messaging outage damages trust | Low | High | Payments run independently of messaging |

## 16. Release plan

| Phase | Date | Content | Exit criteria |
|---|---|---|---|
| Design and research | January to March 2026 | Interviews, prototype tests | Task success above 85% |
| Closed beta | May 2026 | Threads, request and send | No open P0 bugs, error rate below 2% |
| Beta 2 | June to July 2026 | Groups, split modes, settle up | Split results correct in every test case |
| Public launch | August 2026 | Smart settle, privacy controls, Home card | All P0 and P1 pass QA, Compliance and Support sign off |

Threads, split modes and Smart settle are behind feature flags. Messaging can be switched off remotely while payments carry on.

## 17. Open questions

1. Should the payer be selectable, so someone other than the user can have paid?
2. Should Smart settle be on by default for new groups?
3. What do we do for a group that spends in several currencies, such as a trip abroad?
4. When someone is in many groups, do we show a combined overview on Home?

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
