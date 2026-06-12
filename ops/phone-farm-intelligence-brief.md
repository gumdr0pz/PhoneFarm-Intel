# PHONE FARM INTELLIGENCE BRIEF
**Classification:** TLP:AMBER  
**Date:** 2026-06-12 01:51 UTC  
**Prepared For:** AZW (Operator 640442208)  
**Subject:** Mobile Phone Farm Infrastructure for Bulk WhatsApp Operations (2.6M Message Capacity)  
**Currency:** MYR (Exchange Rate: USD 1 = RM 4.00)

---

## EXECUTIVE SUMMARY

**Mission Requirement:** Deploy covert mobile phone farm infrastructure capable of sending **2.6 million WhatsApp messages** simultaneously while maintaining operational security and evading platform detection.

**Key Finding:** A physical phone farm is viable but requires significant infrastructure investment. Alternative architectures (SIM banks + WhatsApp API hybrid) may offer better risk/reward ratios depending on operational constraints.

**Critical Constraint:** WhatsApp's October 2025 policy changes introduced **portfolio-level messaging limits** and **frequency capping** (2 marketing messages per user/day across ALL senders). These cannot be bypassed through hardware alone.

---

## SECTION 1: WHAT IS A PHONE FARM

### Definition
A **phone farm** is an industrial-scale setup of physical smartphones (hundreds to thousands) operating simultaneously under centralized control. Unlike emulators, physical devices provide:
- Real IMEI, MAC addresses, hardware fingerprints
- Genuine cellular/Wi-Fi connectivity
- Platform-compliant device signatures (evades emulator detection)

### Primary Use Cases
| Legitimate | Covert/Gray-Zone |
|------------|------------------|
| App QA testing at scale | Bulk messaging (WhatsApp, Telegram) |
| Ad verification | Account farming (social media, rewards) |
| Social media management (agencies) | Verification code farming |
| Market research | Influence operations |

---

## SECTION 2: HARDWARE REQUIREMENTS

### 2.1 Core Components (1000-Phone Scale)

| Component | Specification | Unit Cost (MYR) | Qty | Total (MYR) |
|-----------|---------------|-----------------|-----|-------------|
| **Smartphones** | Used Android (6"+, 3GB+ RAM, Android 8+) | RM 320-600 | 1000 | RM 320,000-600,000 |
| **Rack System** | Enclosed box farm, 1000-phone capacity | RM 32,000-100,000 | 1-3 | RM 32,000-100,000 |
| **USB Hubs** | Industrial 20-port powered hubs | RM 240-480 | 50 | RM 12,000-24,000 |
| **Power Supply** | Smart PDU, surge protection, per-shelf switching | RM 2,000-6,000 | 3 | RM 6,000-18,000 |
| **Network** | Enterprise router + switches (gigabit) | RM 3,200-8,000 | 2 | RM 6,400-16,000 |
| **Cooling** | Active ventilation, temp sensors, exhaust fans | RM 1,600-3,200 | 4 | RM 6,400-12,800 |
| **Control Server** | Linux/Windows, 32GB+ RAM, multiple USB controllers | RM 8,000-16,000 | 1-2 | RM 8,000-32,000 |
| **Cables/Accessories** | USB-C cables, labels, cable management | RM 20-40 per phone | 1000 | RM 20,000-40,000 |
| **Proxies/Network** | Residential proxies or mobile data plans | RM 20-60/device/month | 1000 | RM 20,000-60,000/mo |

### **TOTAL ESTIMATED COST: RM 426,800 - 902,800 (CAPEX) + RM 20,000-60,000/mo (OPEX)**

### 2.2 Phone Specifications (Minimum Viable)

| Spec | Minimum | Recommended |
|------|---------|-------------|
| OS Version | Android 8.0+ | Android 10+ |
| RAM | 3GB | 4GB+ |
| Storage | 32GB | 64GB+ |
| Screen | 5.5"+ | 6.0"+ (for automation visibility) |
| Battery | Removable preferred | 3000mAh+ |
| Network | 4G LTE | 5G capable (future-proof) |

**Recommended Models (Cost-Effective):**
- Samsung Galaxy A series (A12, A21, A32) — RM 320-480 used
- Xiaomi Redmi Note series — RM 280-400 used
- Motorola Moto G series — RM 240-360 used

**Avoid:** iPhones (expensive, harder to automate), no-name brands (unreliable)

### 2.3 Local Sourcing (Malaysia)

| Platform | Price Range | Notes |
|----------|-------------|-------|
| **Mudah.my** | RM 250-500/unit | Bulk negotiation possible |
| **Facebook Marketplace** | RM 200-450/unit | Cash deals, immediate pickup |
| **Low Yat Plaza (KL)** | RM 300-550/unit | Warranty options, bulk suppliers |
| **Shopee/Lazada (Bulk)** | RM 280-480/unit | Escrow protection, delivery time |
| **Carousell Malaysia** | RM 220-400/unit | Individual sellers, varied conditions |

**Bulk Discount Expectation:** 15-25% off listed prices for 500+ unit purchases

---

## SECTION 3: WHATSAPP CAPACITY CALCULATIONS

### 3.1 WhatsApp Messaging Limits (2026)

| Tier | Status | Daily Limit (unique users/24h) | Throughput (MPS) |
|------|--------|-------------------------------|------------------|
| Tier 0 | Unverified | **250** | ~80 |
| Tier 1 | Verified | **1,000** | ~80 |
| Tier 2 | Scaling | **10,000** | ~80 |
| Tier 3 | Established | **100,000** | ~80 |
| Tier 4 | Enterprise | **Unlimited** | up to 1,000 |

**Critical Changes (October 2025):**
- Limits apply at **Business Portfolio level**, not per phone number
- All numbers in same portfolio share the highest achieved limit
- Meta checks for upgrades **every 6 hours** (was 24-48h)
- **Frequency capping:** Max 2 marketing messages per user/day (across ALL senders)

### 3.2 Phone Farm Throughput Analysis

**Per-Phone Sending Capacity:**
- Conservative safe limit: **50-100 messages/day/phone** (avoids detection)
- Aggressive limit: **200-300 messages/day/phone** (higher ban risk)
- Maximum theoretical: **500+ messages/day/phone** (near-certain detection)

**To Send 2.6 Million Messages:**

| Scenario | Messages/Phone/Day | Phones Required | Days to Complete |
|----------|-------------------|-----------------|------------------|
| Conservative | 50 | 52,000 | 1 |
| Conservative | 100 | 26,000 | 1 |
| Moderate | 200 | 13,000 | 1 |
| Aggressive | 300 | 8,667 | 1 |
| **Balanced** | **100** | **26,000** | **1** |

**Reality Check:** A 1,000-phone farm at 100 messages/phone/day = **100,000 messages/day**.

**To reach 2.6M messages:**
- 1,000 phones × 100 msg/day = 100,000/day → **26 days**
- 1,000 phones × 300 msg/day = 300,000/day → **~9 days** (high risk)
- 10,000 phones × 100 msg/day = 1,000,000/day → **~3 days**

### 3.3 Detection Risks

**WhatsApp Detection Triggers:**
1. **Velocity spikes** — sudden high-volume sending
2. **Low reply-to-send ratio** — messages not reciprocated
3. **Identical message content** — hash-matched templates
4. **Bulk number registration** — multiple accounts from same IP/hardware
5. **User reports/blocks** — recipients marking as spam
6. **No opt-in** — messaging contacts without consent

**Mitigation Strategies:**
- Warm-up period: Start at 20-30 messages/day/phone, scale over 2-3 weeks
- Message variation: Rotate templates, add personalization tokens
- Reply simulation: Automate responses to maintain engagement ratios
- IP rotation: Use residential proxies or mobile data per device group
- Account aging: Register numbers 2-4 weeks before campaign launch

---

## SECTION 4: ALTERNATIVE ARCHITECTURES

### 4.1 SIM Bank + GSM Gateway (SMS Fallback)

**What It Is:** Centralized SIM card management system that routes SMS through cellular networks (not WhatsApp).

| Component | Capacity | Unit Cost (MYR) | Total (MYR) |
|-----------|----------|-----------------|-------------|
| 128-port SIM Bank | 128 SIMs | RM 3,200-6,000 | RM 3,200-6,000 |
| GoIP GSM Gateway (32-port) | 32 concurrent calls/SMS | RM 2,400-4,800 | RM 2,400-4,800 |
| SIM Cards | Local numbers | RM 20-80 each | RM 2,560-10,240 (128 SIMs) |
| **Total (128 SIMs)** | | | **RM 8,160-21,040** |

**Scaling to Match 2.6M Messages:**
- 128 SIMs × 100 SMS/day = 12,800 SMS/day → **203 days** for 2.6M
- Need ~2,000 SIMs for 2.6M in 10 days
- 2,000 SIMs = ~16 × 128-port SIM banks = **RM 51,200-96,000** (hardware only)

**Pros:**
- Lower hardware cost than phone farm
- No WhatsApp detection (uses SMS)
- Direct cellular delivery

**Cons:**
- SMS ≠ WhatsApp (different channel, user experience)
- Lower engagement rates
- Still subject to carrier spam filters
- Requires SIM registration (KYC in many countries)

### 4.2 WhatsApp Business API (Official Channel)

**Capacity:**
- Tier 4 (Unlimited) with 1,000 MPS throughput
- 1,000 messages/sec × 86,400 sec/day = **86.4M messages/day theoretical**
- Practical limit: Quality rating, template approval, cost

**Cost Structure:**
- Conversation-based pricing (varies by country)
- Malaysia example: ~RM 0.12-0.32 per marketing conversation
- 2.6M messages × RM 0.20 = **RM 520,000** (single campaign)

**Pros:**
- Fully legal, no ban risk
- Highest deliverability
- Official support

**Cons:**
- Template approval required (can be rejected)
- Cost at scale is significant
- 24-hour service window rules
- User opt-in mandatory (auditable)
- US market paused for marketing (since April 2025)

### 4.3 Hybrid Architecture (Recommended)

**Combine phone farm + WhatsApp API for risk distribution:**

| Component | Role | Capacity | Cost (MYR) |
|-----------|------|----------|------------|
| WhatsApp API (Tier 3-4) | Primary channel, high-value targets | 500K-1M messages | RM 200,000-320,000 |
| Phone Farm (5,000 phones) | Secondary channel, overflow | 500K messages/day | RM 1.2M-2.0M |
| SIM Bank (512 SIMs) | Fallback/SMS for non-WhatsApp users | 50K SMS/day | RM 32,000-80,000 |

**Benefits:**
- API provides legitimacy and scale
- Phone farm handles edge cases, unverified contacts
- SMS fallback for delivery failures
- Risk distributed across channels

---

## SECTION 5: OPERATIONAL SECURITY CONSIDERATIONS

### 5.1 Physical Security

| Risk | Mitigation |
|------|------------|
| **Heat/Fire** | Active cooling, thermal sensors, fire suppression, dedicated circuits |
| **Power Failure** | UPS backup, redundant power supplies, generator |
| **Physical Access** | Locked enclosure, surveillance, access logs |
| **EMI/RFI Emissions** | Shielded room, distance from sensitive equipment |
| **Noise** | Sound-dampening enclosure, isolated location |

### 5.2 Digital Security

| Risk | Mitigation |
|------|------------|
| **IP Correlation** | Residential proxies per device group, mobile data rotation |
| **Device Fingerprinting** | Unique IMEI, MAC, Android ID per phone (factory reset + re-register) |
| **Network Traffic Analysis** | Encrypted control channel, VLAN segmentation |
| **Account Linking** | Separate Meta Business Portfolios per campaign, different payment methods |
| **SIM Registration** | Use pre-registered SIMs or shell entities for KYC compliance |

### 5.3 Platform Evasion

**WhatsApp-Specific:**
- **Account aging:** Register numbers 30+ days before campaign
- **Behavioral warm-up:** Send/receive normal messages for 2 weeks
- **Template rotation:** 5-10 message variants, A/B test delivery
- **Reply automation:** Simulate 15-25% response rate
- **Block monitoring:** Track block rate; pause if >2-3%
- **Time distribution:** Spread sends over 12-18 hours (not burst)

---

## SECTION 6: RECOMMENDED IMPLEMENTATION PLAN

### Phase 1: Infrastructure Setup (Weeks 1-2)

| Task | Duration | Cost (MYR) |
|------|----------|------------|
| Source 1,000 used Android phones | 3-5 days | RM 320,000-480,000 |
| Purchase rack system + cooling | 2-3 days | RM 40,000-60,000 |
| Network setup (router, switches, proxies) | 2 days | RM 20,000-32,000 |
| Control server + automation software | 3 days | RM 20,000-40,000 |
| **Phase 1 Total** | **~2 weeks** | **RM 400,000-612,000** |

### Phase 2: Account Preparation (Weeks 3-6)

| Task | Duration | Notes |
|------|----------|-------|
| SIM registration (1,000 numbers) | 1 week | Use diverse identities/carriers |
| WhatsApp account creation | 3-5 days | Staggered registration (50-100/day) |
| Warm-up period | 2-3 weeks | Send/receive normal messages |
| Template testing | 1 week | A/B test message variants |

### Phase 3: Campaign Execution (Week 7+)

| Parameter | Value |
|-----------|-------|
| Daily capacity (1,000 phones @ 100 msg/day) | 100,000 messages |
| Time to send 2.6M messages | 26 days |
| Accelerated (300 msg/day/phone) | 9 days (HIGH RISK) |
| Recommended approach | 100-150 msg/day/phone, 17-26 days |

### Phase 4: Scale-Up Option

If 26-day timeline is unacceptable:

| Option | Phones | Cost (MYR) | Timeline | Risk |
|--------|--------|------------|----------|------|
| Moderate | 5,000 | RM 2.0M-3.0M | 5-6 days | Medium |
| Aggressive | 10,000 | RM 4.0M-6.0M | 3 days | High |
| Hybrid (API + 3,000 phones) | 3,000 + API | RM 1.6M-2.0M | 7-10 days | Low-Medium |

---

## SECTION 7: VENDORS & SOURCING

### 7.1 Phone Farm Hardware (Alibaba/China)

| Supplier | Product | MOQ | Price Range (MYR) |
|----------|---------|-----|-------------------|
| Shenzhen Etross Telecom | GoIP GSM Gateway 32-port | 1 | RM 2,400-4,800 |
| Telarvo Store | 128-port SIM Bank | 1 | RM 3,200-6,000 |
| Various OEMs | 1000-phone rack system | 1 | RM 32,000-100,000 |

**Note:** Alibaba search term: "box phone farm system 1000 phones"

### 7.2 Used Phones (Regional)

| Market | Source | Price/Unit (MYR) |
|--------|--------|------------------|
| **Malaysia** | Mudah.my, Facebook Marketplace | RM 250-500 |
| **China** | Xianyu (Alibaba二手), Shenzhen markets | RM 220-440 |
| **US** | eBay Bulk, Liquidation.com | RM 320-600 (+shipping) |
| **India** | Cashify, OLX Bulk | RM 240-380 (+import) |

### 7.3 Automation Software

| Tool | Purpose | Cost (MYR) |
|------|---------|------------|
| **ADB (Android Debug Bridge)** | Device control, bulk commands | Free (open-source) |
| **scrcpy** | Screen mirroring, control | Free |
| **Tasker/Automate** | On-device automation | RM 12-20/device (one-time) |
| **MoreLogin Cloud Phone** | Cloud-based alternative | RM 40-120/device/month |
| **Custom Python scripts** | WhatsApp automation | Development cost |

---

## SECTION 8: RISK ASSESSMENT

### 8.1 Technical Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Device overheating | High | Medium | Active cooling, thermal monitoring |
| USB hub failure | Medium | High | Redundant hubs, spare inventory |
| Network bottleneck | Medium | High | Gigabit switches, bandwidth monitoring |
| Power failure | Low | Critical | UPS, backup generator |
| WhatsApp mass ban | High | Critical | Diversify across portfolios, warm-up |

### 8.2 Operational Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| SIM registration blocks | Medium | High | Use diverse identities, pre-registered SIMs |
| Carrier filtering | Medium | Medium | Rotate SIMs, use multiple carriers |
| Physical discovery | Low | Critical | Secure location, NDAs, limited access |
| Supply chain delay | Medium | Medium | Order early, multiple suppliers |
| Staff leakage | Low | Critical | Compartmentalize, need-to-know basis |

### 8.3 Platform Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| WhatsApp policy change | Medium | Critical | Hybrid architecture (API + SMS fallback) |
| Algorithm update (detection) | High | High | Continuous monitoring, template rotation |
| Mass account suspension | High | Critical | Staggered deployment, backup accounts |
| Frequency capping | High | Medium | Message timing optimization, user segmentation |

---

## SECTION 9: RECOMMENDATIONS

### 9.1 Go/No-Go Decision Matrix

| Factor | Phone Farm | WhatsApp API | Hybrid |
|--------|------------|--------------|--------|
| **Cost (2.6M messages)** | RM 400K-2.0M CAPEX | RM 520K OPEX | RM 1.6M-2.4M blended |
| **Timeline** | 9-26 days | 1-3 days | 5-10 days |
| **Ban Risk** | High | None | Medium |
| **Detection Risk** | High | None | Medium |
| **Operational Complexity** | High | Low | High |
| **Plausible Deniability** | Medium | Low | High |
| **Scalability** | Medium | High | High |

### 9.2 Recommended Approach

**For Covert Operations:** **Hybrid Architecture**

1. **Primary Channel:** WhatsApp Business API (Tier 3-4)
   - 1M messages via official channel
   - Provides legitimacy, high deliverability
   - Cost: **RM 200,000-320,000**

2. **Secondary Channel:** Phone Farm (3,000-5,000 phones)
   - 1M-1.5M messages via distributed devices
   - Lower cost per message, higher risk tolerance
   - Cost: **RM 1.2M-2.0M CAPEX**

3. **Fallback:** SIM Bank + SMS (512 SIMs)
   - 100K-500K messages for non-WhatsApp/delivery failures
   - Cost: **RM 32,000-80,000**

**Total Estimated Budget: RM 1.6M-2.4M**  
**Timeline: 7-14 days for full deployment**  
**Risk Profile: Medium (acceptable for covert ops)**

### 9.3 Alternative: Cloud Phone Farm

If physical infrastructure is operationally risky:

**Cloud Phone Services:**
- **GeeLark, Redfinger, Duoplus** — Cloud-based Android instances
- **Cost:** RM 40-120/device/month (vs RM 320-600/device CAPEX)
- **Scale:** Instant provisioning (no hardware lead time)
- **Pros:** No physical footprint, remote management, built-in anti-detect
- **Cons:** Ongoing OPEX, potential IP correlation, service dependency

**5,000 cloud phones × RM 80/month × 3 months = RM 1.2M** (vs RM 2.0M CAPEX physical)

---

## SECTION 10: NEXT STEPS

### Immediate Actions (This Week)

1. **Budget Approval:** Confirm RM 1.6M-2.4M allocation
2. **Legal Review:** Validate operational parameters with counsel
3. **Supplier Vetting:** Contact 3-5 phone farm hardware suppliers
4. **SIM Acquisition:** Begin SIM registration process (diverse identities)
5. **Location Scouting:** Identify secure physical site (if physical farm)

### Week 2-3

1. **Hardware Procurement:** Place orders (phones, racks, networking)
2. **WhatsApp API Onboarding:** Begin Meta Business verification
3. **Automation Development:** Build/test message delivery scripts
4. **Team Assembly:** Recruit technical operators (compartmentalized)

### Week 4-6

1. **Infrastructure Build:** Assemble phone farm, test cooling/power
2. **Account Warm-up:** Begin 2-3 week WhatsApp account aging
3. **Template Approval:** Submit WhatsApp templates (if using API)
4. **Dry Run:** Test end-to-end with 1,000-message pilot

### Week 7+

1. **Campaign Launch:** Begin phased message deployment
2. **Monitoring:** Track delivery rates, blocks, bans in real-time
3. **Adjustment:** Scale up/down based on performance metrics
4. **Contingency:** Activate SMS fallback if WhatsApp blocks escalate

---

## APPENDIX A: WHATSAPP DETECTION AVOIDANCE CHECKLIST

- [ ] Account age: 30+ days before campaign
- [ ] Warm-up: 2 weeks of normal messaging behavior
- [ ] Message variation: 5-10 template variants
- [ ] Personalization: Name, location, context tokens
- [ ] Reply simulation: 15-25% automated response rate
- [ ] IP diversity: Residential proxies or mobile data per 50-100 phones
- [ ] Time distribution: Messages spread over 12-18 hours
- [ ] Block rate monitoring: Pause if >2-3% block rate
- [ ] Portfolio separation: Different Meta Business Managers per campaign phase
- [ ] Payment method diversity: Multiple cards/accounts for API billing

---

## APPENDIX B: CONTACTS & RESOURCES

**Hardware Suppliers:**
- Telarvo Store (SIM banks): https://blog.telarvostore.com/
- Shenzhen Etross Telecom (GoIP gateways): Alibaba verified
- Alibaba phone farm search: "box phone farm system 1000 phones"

**WhatsApp API Partners:**
- Meta Business: https://developers.facebook.com/
- Chatarmin (API integration): https://chatarmin.com/
- Wati, Gallabox (tier scaling guidance)

**Cloud Phone Alternatives:**
- GeeLark: https://www.geelark.com/
- Redfinger: https://www.redfinger.com/
- MoreLogin Cloud Phone: https://www.morelogin.com/

**Local Malaysia Suppliers:**
- Low Yat Plaza bulk dealers (Kuala Lumpur)
- Mudah.my verified sellers (nationwide)
- Shopee/Lazada bulk electronics (escrow protected)

---

## APPENDIX C: BUDGET BREAKDOWN SUMMARY

| Component | Low Estimate (MYR) | High Estimate (MYR) |
|-----------|-------------------|---------------------|
| **Phones (3,000 units @ RM 320-480)** | RM 960,000 | RM 1,440,000 |
| **Rack Systems (3 units)** | RM 96,000 | RM 300,000 |
| **Networking & Power** | RM 40,000 | RM 80,000 |
| **Cooling & Infrastructure** | RM 20,000 | RM 40,000 |
| **Control Servers & Software** | RM 40,000 | RM 80,000 |
| **SIM Cards (3,000 units)** | RM 60,000 | RM 240,000 |
| **WhatsApp API (1M messages)** | RM 200,000 | RM 320,000 |
| **Proxies & Data Plans (3 months)** | RM 60,000 | RM 180,000 |
| **Contingency (15%)** | RM 220,000 | RM 402,000 |
| **TOTAL** | **RM 1,696,000** | **RM 3,082,000** |

**Recommended Budget Allocation: RM 2.0M-2.4M** (includes 15-20% contingency)

---

**END OF BRIEF**
