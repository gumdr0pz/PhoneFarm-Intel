# WhatsApp Platform Analysis 2026
**Classification:** TLP:AMBER  
**Date:** 2026-06-12  
**Source:** Meta Developer Documentation, Third-Party API Partners

---

## EXECUTIVE SUMMARY

WhatsApp's October 2025 policy changes fundamentally altered bulk messaging operations:

1. **Portfolio-level limits** replace per-number limits
2. **6-hour upgrade checks** (was 24-48 hours)
3. **Frequency capping** at 2 marketing messages/user/day across ALL senders
4. **US market paused** for marketing templates (April 2025)

These changes cannot be bypassed through hardware alone — they are enforced at the platform level.

---

## WHATSAPP MESSAGING LIMITS (2026)

### Tier System

| Tier | Status | Daily Limit (unique users/24h) | Throughput (MPS) |
|------|--------|-------------------------------|------------------|
| Tier 0 | Unverified | **250** | ~80 |
| Tier 1 | Verified | **1,000** | ~80 |
| Tier 2 | Scaling | **10,000** | ~80 |
| Tier 3 | Established | **100,000** | ~80 |
| Tier 4 | Enterprise | **Unlimited** | up to 1,000 |

### Key Changes (October 2025)

**Before October 2025:**
- Limits applied per phone number
- Each new number started at Tier 1 (1,000/day)
- Upgrade review: 24-48 hours
- Warm-up required for each number individually

**After October 2025:**
- Limits apply per **Business Portfolio**
- All numbers in same portfolio share the **highest achieved limit**
- Upgrade review: **every 6 hours**
- New numbers instantly inherit portfolio's tier

### Practical Impact

```
Scenario: Company has 3 phone numbers in same Business Portfolio

Number 1: Tier 3 (100,000/day) - established, good quality
Number 2: New, just verified → Instantly gets 100,000/day limit
Number 3: New, just verified → Instantly gets 100,000/day limit

Total portfolio capacity: 300,000 unique users/day
```

**Flip Side:** Poor performance on one number affects the entire portfolio.

---

## THROUGHPUT ANALYSIS

### Messages Per Second (MPS)

| Tier | Standard Throughput | Upgraded Throughput |
|------|--------------------|--------------------|
| Tier 0-3 | ~80 MPS | N/A |
| Tier 4 | ~80 MPS | up to 1,000 MPS |

### Time to Send Campaigns

| Campaign Size | At 80 MPS | At 1,000 MPS |
|---------------|-----------|--------------|
| 10,000 messages | 2 minutes | 10 seconds |
| 100,000 messages | 21 minutes | 100 seconds |
| 1,000,000 messages | 3.5 hours | 17 minutes |
| 2,600,000 messages | 9 hours | 43 minutes |

**Note:** Tier 4 throughput upgrade is automatic for accounts with stable quality ratings.

---

## FREQUENCY CAPPING (2025+)

### The Invisible Limit

Since 2025, Meta limits how many marketing messages an **individual user** can receive per day — across ALL brands.

**Limit:** ~2 marketing templates per user per day

### Error Code 131049

```
Error: 131049
Message: "User has reached the frequency cap for marketing messages"
```

This doesn't mean your account is broken — it means the recipient is "saturated."

### Practical Impact

```
User receives:
- 8:00 AM: Marketing message from Shop A
- 10:00 AM: Marketing message from Shop B
- 2:00 PM: YOUR marketing message → BLOCKED (error 131049)
```

**Mitigation:**
- Segment audiences by engagement level
- Spread send times across multiple days
- Prioritize high-value users for limited slots
- Use utility templates where appropriate (not subject to cap)

---

## QUALITY RATING SYSTEM

### Three Tiers

| Rating | Status | Impact |
|--------|--------|--------|
| 🟢 Green (High) | All clear | Can scale, upgrades enabled |
| 🟡 Yellow (Medium) | Warning | Further deterioration = limit reduction |
| 🔴 Red (Low) | Danger | No upgrades, risk of immediate downgrade |

### What Influences Quality Rating

1. **User blocks** — Recipients blocking your number
2. **Spam reports** — Users marking messages as spam
3. **Template quality** — Rejection rates, user engagement
4. **Reply ratios** — Low response rates signal unwanted content
5. **Opt-in verification** — Auditable consent records

### 2026 Change

A red rating **prevents advancement** but no longer automatically triggers immediate downgrade (as long as no policy violations). This gives time to course-correct.

---

## US MARKET RESTRICTIONS

### Marketing Templates Paused (April 2025)

**Status:** Marketing template messages to US numbers (+1 area code) are **temporarily paused**.

**Still Works:**
- ✅ Utility messages (order confirmations, shipping updates)
- ✅ Authentication templates (OTPs, login codes)

**Blocked:**
- ❌ Promotional content
- ❌ Marketing campaigns
- ❌ Sales notifications

### Reason

Meta responding to regulatory pressure and user complaints in the US market.

### Impact on Operations

European/international companies with US expansion plans cannot use WhatsApp for marketing to US users currently. Plan campaigns accordingly.

---

## TEMPLATE CATEGORIES

### Marketing Templates

**Use Case:** Promotions, sales, product announcements

**Subject to:**
- Frequency capping (2/day per user)
- Opt-in requirements
- Portfolio messaging limits

**Examples:**
- "Flash sale: 50% off all items!"
- "New product launch - check it out"
- "Your exclusive discount inside"

### Utility Templates

**Use Case:** Order updates, shipping, account notifications

**Subject to:**
- NOT subject to frequency capping
- Still counts toward portfolio limits
- Must match actual utility content

**Examples:**
- "Your order #12345 has shipped"
- "Payment confirmation for RM 150.00"
- "Appointment reminder: Tomorrow at 3 PM"

### Authentication Templates

**Use Case:** OTPs, login codes, verification

**Requirements:**
- Business must be verified (Tier 1+)
- Cannot use at Tier 0

**Examples:**
- "Your verification code: 847291"
- "Login attempt detected. Code: 593847"
- "Password reset: Use code 284756"

---

## DETECTION TRIGGERS

### What Gets Accounts Banned

1. **Velocity spikes** — Sudden high-volume sending
   - Example: 0 → 10,000 messages in 1 hour
   
2. **Low reply-to-send ratio** — Messages not reciprocated
   - Normal: 15-25% response rate
   - Suspicious: <5% response rate

3. **Identical message content** — Hash-matched templates
   - Send same exact message to 10,000 users = flagged

4. **Bulk number registration** — Multiple accounts from same IP/hardware
   - 100+ numbers registered from same device fingerprint

5. **User reports/blocks** — Recipients marking as spam
   - >2-3% block rate triggers review

6. **No opt-in** — Messaging contacts without consent
   - Auditable records required for enterprise accounts

---

## WARM-UP STRATEGIES

### Recommended Approach

| Week | Messages/Day/Number | Activities |
|------|---------------------|------------|
| 1 | 20-30 | Normal conversations, some broadcasts |
| 2 | 50-75 | Increase broadcast volume, monitor blocks |
| 3 | 100-150 | Full campaign testing, A/B templates |
| 4+ | Scale to tier limit | Full operations |

### Warm-Up Best Practices

1. **Start slow** — 20-30 messages/day for first week
2. **Mix message types** — Some 1:1 conversations, some broadcasts
3. **Monitor block rate** — Pause if >2% blocks
4. **Vary templates** — 5-10 different message variants
5. **Simulate replies** — 15-25% automated response rate

---

## PORTFOLIO SEPARATION STRATEGY

### For High-Volume Operations

Don't put all numbers in one portfolio. Separate by:

**By Campaign Type:**
```
Portfolio A: Marketing campaigns (higher risk)
Portfolio B: Utility notifications (lower risk)
Portfolio C: Authentication/OTP (lowest risk)
```

**By Geographic Region:**
```
Portfolio MY: Malaysia numbers
Portfolio SG: Singapore numbers
Portfolio ID: Indonesia numbers
```

**By Brand/Business:**
```
Portfolio Brand-A: E-commerce store A
Portfolio Brand-B: E-commerce store B
Portfolio Brand-C: Service business
```

### Benefits

- Risk isolation (one portfolio ban doesn't affect others)
- Separate quality ratings
- Independent limit scaling
- Different payment methods for billing

---

## API PARTNERS (2026)

### Official Meta Partners

| Partner | Region | Specialization |
|---------|--------|----------------|
| **Chatarmin** | Global | E-commerce, Shopify integration |
| **Wati** | APAC | SMB-focused, easy onboarding |
| **Gallabox** | India/APAC | Enterprise scaling guidance |
| **Twilio** | Global | Developer-first, full API access |
| **MessageBird** | EU/Global | Enterprise, compliance-focused |

### Pricing Comparison (Malaysia)

| Partner | Cost per Conversation | Minimum |
|---------|----------------------|---------|
| Meta Direct | ~RM 0.12-0.32 | None |
| Twilio | ~RM 0.15-0.35 | $50/month |
| Chatarmin | ~RM 0.14-0.33 | RM 200/month |
| Wati | ~RM 0.16-0.36 | RM 150/month |

---

## AI CHATBOT POLICY (2026)

### Banned (Since January 15, 2026)

- ❌ General purpose AI chatbots without business context
- ❌ AI systems posing as "friends" or companions
- ❌ Bots without clear business purpose
- ❌ Open ChatGPT clones on WhatsApp

### Allowed

- ✅ Support automation (FAQ, order status, returns)
- ✅ Sales flows (product consultation, lead qualification)
- ✅ AI-powered customer service agents with defined scope

### Key Difference

Your AI must be a **tool that supports your business** — not the main product itself.

---

## COMPLIANCE CHECKLIST

- [ ] Business verification completed in Meta Business Manager
- [ ] Opt-in records maintained for all contacts
- [ ] Template categories match actual content
- [ ] Unsubscribe option in every marketing message
- [ ] Block rate monitored (<2% threshold)
- [ ] Frequency capping considered in campaign planning
- [ ] US numbers excluded from marketing campaigns
- [ ] Multiple portfolios for risk distribution
- [ ] Quality rating monitored daily
- [ ] Template approval obtained before campaign launch

---

## SOURCES

1. Meta Developer Documentation — https://developers.facebook.com/
2. WhatsApp Messaging Limits — https://developers.facebook.com/documentation/business-messaging/whatsapp/messaging-limits/
3. Chatarmin Analysis — https://chatarmin.com/en/blog/whats-app-messaging-limits
4. TechCrunch — "WhatsApp will curb the number of messages" (Oct 2025)
5. Gallabox Partner Updates — Portfolio limit guidance

---

**END OF DOCUMENT**
