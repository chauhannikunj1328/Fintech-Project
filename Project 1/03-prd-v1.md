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

> Kinpay is an original portfolio concept and has no connection to any company. All numbers are planning assumptions, not results. Requirements marked *(designed)* are my own design, not taken from an existing product.

## 1. Summary

Kinpay v1 does one thing: it moves money between people who already know each other, without anyone hunting for bank details. You can pay a friend, ask a friend for money, and see whether they have done it yet.

We are also shipping a small first version of groups. A group can split a bill equally, and that is as far as splitting goes in this release. Anything smarter waits for v2.

Rent can be scheduled and repeated. Everything else in the wider app (cards, saving, investing) is outside this document.

## 2. Problem and opportunity

### 2.1 The problem

Think about the last time you split a dinner. Someone paid, someone else asked for account details, a third person said they'd transfer it later and forgot. A week on, the person who paid is still sending polite messages.

Rent is worse. It happens every month, it is the same amount, and it still gets handled through chat and screenshots.

Three things keep going wrong:

- Paying a friend means finding their bank details first.
- Asking for money feels awkward, and once you've asked you can't see what happened.
- Group bills get settled off-app, one person at a time, and nobody has the full picture.

### 2.2 What we think is true

We haven't tested these yet. They are the assumptions the design is built on.

| # | Assumption | How we would check |
|---|---|---|
| H1 | Paying a friend is slow mainly because of the bank details | Timed task test with 8 people |
| H2 | People put off asking for money because there is no visible status | Interviews and app review mining |
| H3 | Groups settle off-app, one person at a time | Interviews with roommates and trip organisers |

### 2.3 Why it is worth doing

Paying a friend is frequent, small and emotional. If we make it quick and polite, people will come back every week, which doesn't happen much with money apps.

## 3. Goals, non-goals and principles

### 3.1 Goals

| Goal | How we measure it |
|---|---|
| A new user sends their first payment within 2 minutes of finishing signup | Median time to first payment |
| Anyone can be asked for money, whether or not they have Kinpay | Share of requests paid by non-users |
| Every request and payment shows a clear status | Support contacts asking where their money is |
| People can split a bill in a group | Groups created, bills split |

### 3.2 What we are leaving out

- **Chat.** It is the first thing people will ask for. We are leaving it out because notes on payments cover the basic need, and we want to see how people use requests before building a conversation around them.
- **Unequal splits.** Equal is right more often than not for a first release. Amount, percent and share come in v2.
- **Automatic debt reduction.** It needs groups with real history before it is worth building.
- **Multi-currency groups.** Not needed at launch.
- **Cards, saving, investing.** Part of the longer vision, not this release.

### 3.3 Principles we designed to

1. One main action on each screen. If a screen has two, we split it.
2. No surprises with money. Fees and totals appear before anyone confirms.
3. Every error says what to do next.
4. Asking for money is awkward enough already, so the wording stays friendly and never accusing.

## 4. Users

### 4.1 Who we are designing for

| Persona | What they need | Situation |
|---|---|---|
| Aarav, 26, roommate | To share rent and bills every month | Pays on the 1st, tired of chasing |
| Meera, 29, the organiser | To collect money for dinners and outings | Usually pays first, on her card |
| Kabir, 24, occasional user | To pay a friend back quickly | Doesn't want to set anything up |

### 4.2 What they are trying to get done

- "I owe a friend. I want to pay without asking for their details."
- "I paid for everyone. I want to ask politely and see who has paid, so I can stop chasing."
- "We're sharing a bill. I want the shares worked out for me so nobody argues."

## 5. Scope and priority

| Priority | Meaning | Features |
|---|---|---|
| P0 | Can't launch without it | Signup and identity check, friends list, send money, request link, history |
| P1 | Should be in, can slip if needed | Scheduling, notifications, basic groups, statements |
| P2 | After launch | Unequal splits, chat, scheduled reminders |

## 6. Key user stories and acceptance criteria

| Story | Acceptance criteria |
|---|---|
| I can pay a friend in under five taps. | Friends list, amount, note and review take no more than five taps. The fee line is visible. |
| I can create a payment link and share it anywhere. | The link carries the amount and note, and the share sheet opens. It expires after 9 days and shows the expiry. |
| I can see the status of a request. | Status moves from Link created to Paid to Received. Each change sends a notification. |
| I can schedule a payment. | Start date and repeat are set. If a month has no 31st, the payment goes out on the last day. |
| I can invite a friend who isn't on Kinpay. | The invite uses the share sheet and the friend shows as invited. |
| I can split a bill equally in a group. *(designed)* | The shares add up to the bill. Any remainder goes to whoever paid. |

## 7. Functional requirements

P0 means must have, P1 means should have.

### 7.1 Signup and verification

| ID | P | Requirement |
|---|---|---|
| F-101 | P0 | Sign up with a phone number and a 6-digit code. Resend is allowed after 15 seconds. |
| F-102 | P0 | Collect name as on ID, date of birth, address and email. |
| F-103 | P0 | Create and confirm a 6-digit passcode. |
| F-104 | P0 | Verify identity with a document photo and a selfie. Show clear errors for blurry or dark images. |
| F-105 | P1 | Ask the purpose of use, as regulation requires. |

### 7.2 Friends

| ID | P | Requirement |
|---|---|---|
| F-201 | P0 | A "Who to pay" list with search, an alphabet index, and filters for Friends and Accounts. |
| F-202 | P0 | Invite a friend by link, message app or copy. |
| F-203 | P1 | Add a contact by name and phone or email. |
| F-204 | P1 | Friend profile showing total sent, account details, scheduled transfers and transactions. |
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
| F-405 | P0 | The payer doesn't need a Kinpay account. |
| F-406 | P1 | The requester can cancel an open link. |

### 7.5 Scheduling

| ID | P | Requirement |
|---|---|---|
| F-501 | P1 | Choose a start date and a repeat: never, daily, weekly, every 2 weeks, monthly. |
| F-502 | P1 | If the day doesn't exist in a month (29th to 31st), pay on the last day. |
| F-503 | P1 | A list of upcoming payments with edit, deactivate and delete. |

### 7.6 Groups, basic *(designed)*

| ID | P | Requirement |
|---|---|---|
| F-601 | P1 | Create a group with a name and members picked from friends. |
| F-602 | P1 | Add one bill from a past transaction or by amount. |
| F-603 | P1 | Split equally among the chosen members. Any remainder goes to the payer's share. |
| F-604 | P1 | The group screen shows each member's balance: owes, owed, settled. |
| F-605 | P1 | A member can pay their share from the group screen. |
| F-606 | P1 | The organiser can send a reminder, at most once a day per member. |
| F-607 | P1 | A member can't leave while they have an open balance. |

### 7.7 History and notifications

| ID | P | Requirement |
|---|---|---|
| F-701 | P0 | Transaction list with Past and Upcoming tabs, search and an account filter. |
| F-702 | P1 | Push notifications for payment received, request paid and request expiring. |
| F-703 | P1 | Statement download as PDF or Excel for a date range. |

## 8. Key flows

1. **Pay a friend:** Payments → Choose friend → Amount → Note → Review → Send → Tracker
2. **Request with a link:** Payments → Request → Amount → Create link → Share → Status
3. **Split a bill, basic:** Groups → Create → Add bill → Pick members → Equal split → Pay or remind
4. **Schedule rent:** Choose friend → Amount → Schedule → Monthly → Review → Confirm

## 9. Edge cases and states

| Situation | What happens |
|---|---|
| Wrong code | Error sheet, try again |
| Blurry document or dark selfie | Message on the screen, retake |
| Amount above balance | Amount turns red, "exceeds balance", Add money action |
| Amount below the minimum | Button disabled, with the reason |
| Friend isn't on Kinpay | Offer an invite and a payment link |
| Link expired | Status shows "Expired", create a new one |
| Payment pending verification | Pending label with a short explanation |
| No connection | Blocking message and retry |
| Member leaves with an open balance | Blocked, with an explanation |

## 10. Non-functional requirements

| Area | Requirement |
|---|---|
| Performance | Screens in the send flow respond within 300 ms. Payment confirmation within 5 seconds for 95% of payments. |
| Accessibility | WCAG 2.1 AA. Text contrast 4.5:1. Touch targets 44 pt. Dynamic Type supported. Screen reader labels on every control. |
| Security | Passcode and biometric unlock. Screen content hidden in the app switcher. Session timeout. |
| Privacy | Data kept as the law requires. Consent written in plain language. |
| Reliability | 99.9% monthly availability for payments. |
| Localisation | English first. Layout ready for Hindi and Gujarati. Amounts in ₹ with Indian digit grouping. |

## 11. Content and tone

We keep the wording short and plain. "Ask" is better than "Request" where a button is tight on space. We never blame the user: "This request has expired", not "You failed to pay in time". Errors always say what to do next. Reminders stay neutral, for example "A friendly reminder from Meera: ₹450 for dinner."

## 12. Analytics plan

| Event | Properties | Used for |
|---|---|---|
| signup_completed | method, duration | Signup funnel |
| first_payment_sent | amount band, time since signup | Activation |
| payment_succeeded / failed | reason | Reliability |
| request_created | type (link), amount band | Adoption |
| request_paid | hours to pay, payer is non-user | Whether requests work |
| invite_sent / invite_accepted | channel | Growth |
| group_created / bill_split | members, mode | Group usage |
| reminder_sent | count | How much chasing happens |

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
| A1 | We launch in India, in ₹. Sample data uses Indian names. |
| A2 | Payments run on a licensed partner's rails. Kinpay does not hold customer funds. |
| A3 | Identity checks go through an approved partner and follow local rules. |
| A4 | Contact import needs the user's permission. |
| D1 | Partner bank or payment provider ready by October 2025. |
| D2 | Identity partner integrated by October 2025. |
| D3 | Support tool with chat ready before launch. |

## 15. Risks

| Risk | Likelihood | Impact | What we do about it |
|---|---|---|---|
| Fraud through payments to new recipients | Medium | High | Trust warning, limits on new accounts, monitoring |
| Users expect chat and unequal splits | High | Medium | Say what's coming in onboarding and collect feedback in the app |
| People drop out at the identity check | Medium | High | Clear photo guidance, easy retake, track each step |
| Link requests get ignored | High | Medium | Show the expiry, notify before it ends |
| Partner downtime | Low | High | Clear status messages and retry |

## 16. Release plan

| Phase | Date | Content | Exit criteria |
|---|---|---|---|
| Internal test | September 2025 | Signup, send, history | No open P0 bugs |
| Closed beta | November 2025 | Request links, scheduling, invites | Payment error rate below 3% |
| Public launch | January 2026 | Basic groups, notifications, support | All P0 and P1 pass QA, Compliance signs off |

If something goes wrong after launch, groups and scheduling sit behind feature flags and can be switched off. A partner outage puts Send and Request into a read-only state with a clear message.

## 17. Open questions

1. Is equal split enough for the first release, or will people ask for amount-based splits straight away?
2. Should link requests work in more than one currency?
3. How long should a request stay open by default? 9 days is a guess.

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
