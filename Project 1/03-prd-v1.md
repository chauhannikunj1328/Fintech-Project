# Kinpay Shared Money: Product Requirements Document

| | |
|---|---|
| **Product** | Kinpay, a money app for friends, roommates and groups |
| **Document** | PRD v1.0 |
| **Release** | January 2026 |
| **Platform** | iOS, light theme |
| **Status** | Released |
| **Owner** | Nikunj Chauhan, Product Designer |
| **Audience** | Product, Design, Engineering, Compliance, Support |
| **Next version** | [PRD v2.0, August 2026](04-prd-v2.md) |

> **Concept disclaimer.** Kinpay is an original portfolio concept. It is not affiliated with any company. Numbers are planning assumptions, not measured results. Requirements marked *(designed)* are the author's own design, not copied from any existing product.

## 1. Executive summary

Kinpay v1 lets people **pay a friend, ask a friend for money, and see who has paid**, with a first simple way to **share a bill in a group**.

Version 1 does one job well: it removes the need for bank details, chat screenshots and mental arithmetic when money moves between people who know each other.

**At a glance**

- Send money to a friend in under five taps.
- Request money with a link, even from people who do not have Kinpay.
- Track every request: created, paid, received.
- Create a group and split one bill equally.
- Schedule and repeat payments, such as monthly rent.

## 2. Problem and opportunity

### 2.1 The problem
People share costs all the time: dinners, rides, rent, trips. Today they:

- Ask for account details, then copy them between apps.
- Keep a tally in their head or in a notes app.
- Chase friends in chat, with no record of who paid.
- Lose track when several people and several bills are involved.

### 2.2 Hypotheses to validate
| # | Hypothesis | How we would test it |
|---|---|---|
| H1 | Paying a friend is too slow when you need their bank details | Time-on-task test with 8 users |
| H2 | Asking for money feels awkward, and nothing shows its status | Interviews, review mining |
| H3 | Group bills are settled off-app, one person at a time | Interviews with roommates and trip organisers |

### 2.3 Opportunity
Peer payments are frequent, low value and high emotion. A product that makes them fast, clear and polite can earn weekly use, which is rare in finance apps.

## 3. Goals, non-goals and principles

### 3.1 Goals
| Goal | Measure |
|---|---|
| A new user sends money to a friend within 2 minutes of finishing signup | Median time to first payment |
| Anyone can be asked for money, with or without Kinpay | Share of requests paid by non-users |
| Every request and payment has a visible status | Support contacts about "where is my money" |
| People can split a bill in a group | Groups created, bills split |

### 3.2 Non-goals for v1

- Chat or messages between friends.
- Unequal splits (amount, percent, share).
- Automatic debt reduction across a group.
- Multi-currency groups.
- Investing, cards, perks, savings pots (part of a wider vision, out of scope here).

### 3.3 Design principles

1. **Clear before clever.** One primary action per screen.
2. **Money is never a surprise.** Fees and totals are shown before every confirmation.
3. **No dead ends.** Every error offers a next step.
4. **Respect the awkwardness.** Words for asking and reminding are polite and neutral.

## 4. Users

### 4.1 Personas
| Persona | Need | Context |
|---|---|---|
| **Aarav, 26, roommate** | Share rent and utilities every month | Pays on the 1st and tires of chasing |
| **Meera, 29, organiser** | Collect money for dinners and outings | Often pays upfront by card |
| **Kabir, 24, occasional** | Pay a friend back quickly | Does not want to set anything up |

### 4.2 Jobs to be done

- When I owe a friend, I want to pay without asking for details, so I can settle fast.
- When I paid for others, I want to ask politely and see who has paid, so I stop chasing.
- When a bill is shared, I want everyone's share worked out for me, so nobody argues.

## 5. Scope and priority

| Priority | Meaning | Features |
|---|---|---|
| **P0** Must | Cannot launch without | Signup and identity check, friends list, send money, request link, history |
| **P1** Should | Launch if possible | Scheduling, notifications, groups (basic), statements |
| **P2** Later | After launch | Unequal splits, chat, reminders by schedule |

## 6. Key user stories and acceptance criteria

| Story | Acceptance criteria |
|---|---|
| As a user, I can pay a friend in under five taps. | Friends list, amount, note and review take at most five taps. Fee line is visible. |
| As a user, I can create a payment link and share it anywhere. | Link carries amount and note. Share sheet opens. Link expires in 9 days and shows the expiry. |
| As a user, I can see the status of a request. | Status moves Link created, Paid, Received. Each change sends a notification. |
| As a user, I can schedule a payment. | Start date and repeat are set. A day missing in a month pays on the last day. |
| As a user, I can invite a friend who is not on Kinpay. | Invite goes through the share sheet. The friend appears as invited. |
| As a user, I can split a bill equally in a group. *(designed)* | Equal shares add up to the bill. Any remainder goes to the payer. |

## 7. Functional requirements

Priority key: **P0** must, **P1** should.

### 7.1 Signup and verification
| ID | P | Requirement |
|---|---|---|
| F-101 | P0 | Sign up with a phone number and a 6-digit code. Resend allowed after 15 seconds. |
| F-102 | P0 | Collect name as on ID, date of birth, address and email. |
| F-103 | P0 | Create and confirm a 6-digit passcode. |
| F-104 | P0 | Verify identity with a document photo and a selfie. Show clear errors for blurry or dark images. |
| F-105 | P1 | Ask the purpose of use, as required by regulation. |

### 7.2 Friends
| ID | P | Requirement |
|---|---|---|
| F-201 | P0 | "Who to pay" list with search, alphabet index and filters for Friends and Accounts. |
| F-202 | P0 | Invite a friend by link, message app or copy. |
| F-203 | P1 | Add a contact by name and phone or email. |
| F-204 | P1 | Friend profile: total sent, account details, scheduled transfers, transactions. |
| F-205 | P1 | Add a label to a friend, for example "Landlord". |

### 7.3 Send money
| ID | P | Requirement |
|---|---|---|
| F-301 | P0 | Enter an amount with a calculator keyboard and quick-amount chips. |
| F-302 | P0 | Show fees before sending, including "No fees". |
| F-303 | P1 | Optional note. |
| F-304 | P0 | Review screen with the warning "Do you know and trust the payee?" |
| F-305 | P0 | Success state with a tracker: in review, leaving, arrived. |
| F-306 | P0 | If the balance is too low, show the shortfall and an "Add money" action. |

### 7.4 Request with a link
| ID | P | Requirement |
|---|---|---|
| F-401 | P0 | Create a link for a set amount or any amount, with an optional note. |
| F-402 | P0 | Share through the system share sheet. |
| F-403 | P0 | The link expires after 9 days, and the expiry is shown. |
| F-404 | P0 | Tracker: Link created, Paid, Received in account. |
| F-405 | P0 | The payer does not need a Kinpay account. |
| F-406 | P1 | The requester can cancel an open link. |

### 7.5 Scheduling
| ID | P | Requirement |
|---|---|---|
| F-501 | P1 | Choose a start date and repeat: never, daily, weekly, every 2 weeks, monthly. |
| F-502 | P1 | If the day is missing in a month (29th to 31st), pay on the last day. |
| F-503 | P1 | A list of upcoming payments with edit, deactivate and delete. |

### 7.6 Groups, basic *(designed)*
| ID | P | Requirement |
|---|---|---|
| F-601 | P1 | Create a group with a name and members chosen from friends. |
| F-602 | P1 | Add one bill from a past transaction or by amount. |
| F-603 | P1 | Split equally among selected members. Any remainder goes to the payer's share. |
| F-604 | P1 | The group screen shows each member's balance: owes, owed, settled. |
| F-605 | P1 | A member can pay their share from the group screen. |
| F-606 | P1 | The organiser can send a reminder, once per day per member at most. |
| F-607 | P1 | Leaving is blocked while the member has an open balance. |

### 7.7 History and notifications
| ID | P | Requirement |
|---|---|---|
| F-701 | P0 | Transaction list with Past and Upcoming tabs, search and an account filter. |
| F-702 | P1 | Push notifications: payment received, request paid, request expiring. |
| F-703 | P1 | Statement download as PDF or Excel for a date range. |

## 8. Key flows

1. **Pay a friend:** Payments → Choose friend → Amount → Note → Review → Send → Tracker
2. **Request with a link:** Payments → Request → Amount → Create link → Share → Status
3. **Split a bill, basic:** Groups → Create → Add bill → Pick members → Equal split → Pay or remind
4. **Schedule rent:** Choose friend → Amount → Schedule → Monthly → Review → Confirm

## 9. Edge cases and states

| Situation | Behaviour |
|---|---|
| Wrong code | Error sheet and retry |
| Blurry document or dark selfie | Inline message and retake |
| Amount above balance | Red amount, "exceeds balance", Add money action |
| Amount below minimum | Disabled button with the reason |
| Friend not on Kinpay | Offer invite and payment link |
| Link expired | Status "Expired", create a new one |
| Payment pending verification | Pending label and explanation |
| No connection | Blocking message and retry |
| Member leaves with open balance | Blocked with explanation |

## 10. Non-functional requirements

| Area | Requirement |
|---|---|
| Performance | Send flow screens respond within 300 ms. Payment confirmation within 5 seconds in 95% of cases. |
| Accessibility | WCAG 2.1 AA. Contrast 4.5:1 for text. Touch targets 44 pt. Dynamic Type supported. Screen reader labels on all controls. |
| Security | Passcode and biometric unlock. Screen content hidden in app switcher. Session timeout. |
| Privacy | Data stored as required by law. Plain-language consent. |
| Reliability | 99.9% monthly availability for payments. |
| Localisation | English first. Layout ready for Hindi and Gujarati. Amounts shown in ₹ with Indian digit grouping. |

## 11. Content and tone

- Plain words. "Ask" rather than "Request" in buttons where space allows.
- Never blame: "This request has expired", not "You failed to pay in time".
- Always give the next step in an error.
- Reminders are neutral: "A friendly reminder from Meera: ₹450 for dinner."

## 12. Analytics plan

| Event | Properties | Used for |
|---|---|---|
| signup_completed | method, duration | Funnel |
| first_payment_sent | amount band, time since signup | Activation |
| payment_succeeded / failed | reason | Reliability |
| request_created | type (link), amount band | Adoption |
| request_paid | hours to pay, payer is non-user | Effectiveness |
| invite_sent / invite_accepted | channel | Growth |
| group_created / bill_split | members, mode | Group usage |
| reminder_sent | count | Chasing effort |

## 13. Success metrics

| Metric | Baseline | 90-day target | Source |
|---|---|---|---|
| Signup to first payment within 7 days | New product | 40% | first_payment_sent |
| Median active time from signup to first payment | New product | under 2 minutes | session timing |
| Requests created per active user per month | New product | 1.5 | request_created |
| Requests paid within 3 days | New product | 60% | request_paid |
| Users who create a group | New product | 15% | group_created |
| Payment error rate | New product | below 2% | payment_failed |
| Support contacts per 1,000 payments | New product | below 8 | Support tool |

## 14. Assumptions and dependencies

| # | Item |
|---|---|
| A1 | Launch market is India, currency ₹. Sample data uses Indian names. |
| A2 | Payments run on a licensed partner's rails. Kinpay does not hold funds itself. |
| A3 | Identity checks use an approved partner and meet local rules. |
| A4 | Contact import needs the user's permission. |
| D1 | Partner bank or payment provider ready by October 2025. |
| D2 | Identity partner integrated by October 2025. |
| D3 | Support tool with chat ready before launch. |

## 15. Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Fraud through new-recipient payments | Medium | High | Trust warning, limits on new accounts, monitoring |
| Users expect chat and unequal splits | High | Medium | Set expectations in onboarding, collect feedback in-app |
| Identity check drop-off | Medium | High | Clear photo guidance and retake, track each step |
| Link requests ignored | High | Medium | Expiry shown, notification before expiry |
| Partner downtime | Low | High | Clear status messages, retry, fallback copy |

## 16. Release plan

| Phase | Date | Content | Exit criteria |
|---|---|---|---|
| Internal test | September 2025 | Signup, send, history | No P0 bugs open |
| Closed beta | November 2025 | Request links, scheduling, invites | Payment error rate below 3% |
| **Public launch** | **January 2026** | Groups (basic), notifications, support | All P0 and P1 pass QA, Compliance sign-off |

**Rollback.** Feature flags for groups and scheduling. A partner outage switches Send and Request to a read-only state with a clear message.

## 17. Open questions

1. Is equal split enough for the first release, or do we need amount-based splits?
2. Should link requests work in several currencies?
3. How long should a request stay open by default?

## 18. Glossary and revision history

| Term | Meaning |
|---|---|
| Request | A message asking someone to pay a set amount |
| Payment link | A web link that lets anyone pay a request |
| Group | A set of friends who share bills |
| Settled up | Nobody in the group owes anything |

| Version | Date | Change |
|---|---|---|
| 0.9 | October 2025 | Beta scope frozen |
| 1.0 | January 2026 | Public launch |
