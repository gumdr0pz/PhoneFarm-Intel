# Phone Farm Hardware Guide 2026
**Classification:** TLP:AMBER  
**Date:** 2026-06-12  
**Currency:** MYR (USD 1 = RM 4.00)

---

## EXECUTIVE SUMMARY

A phone farm is industrial-scale infrastructure housing hundreds to thousands of physical smartphones under centralized control. For 2.6M WhatsApp messages:

- **Minimum viable:** 1,000 phones × 26 days @ 100 msg/day/phone
- **Accelerated:** 5,000 phones × 5-6 days @ 100 msg/day/phone
- **Budget range:** RM 400K (1K phones) to RM 2.4M (5K phones + API hybrid)

---

## WHAT IS A PHONE FARM

### Definition

Industrial setup of physical smartphones operating simultaneously under centralized automation. Unlike emulators, physical devices provide:

- Real IMEI, MAC addresses, hardware fingerprints
- Genuine cellular/Wi-Fi connectivity
- Platform-compliant device signatures
- Evades emulator detection systems

### Phone Farm vs. SIM Bank

| Feature | Phone Farm | SIM Bank + GSM Gateway |
|---------|------------|----------------------|
| **Device Type** | Full smartphones | SIM cards only |
| **Platform** | WhatsApp, Telegram, apps | SMS only |
| **Cost (1000 units)** | RM 400K-600K | RM 32K-80K |
| **Throughput** | 100K msg/day | 12K SMS/day |
| **Detection Risk** | Medium-High | Low-Medium |
| **Engagement** | High (rich media) | Low (text only) |

---

## HARDWARE REQUIREMENTS (1000-PHONE SCALE)

### Core Components

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

### Total Estimated Cost

| Scale | CAPEX | OPEX/Month |
|-------|-------|------------|
| **1,000 phones** | RM 404,000-840,000 | RM 20,000-60,000 |
| **3,000 phones** | RM 1.2M-2.0M | RM 60,000-180,000 |
| **5,000 phones** | RM 2.0M-3.0M | RM 100,000-300,000 |

---

## PHONE SPECIFICATIONS

### Minimum Viable

| Spec | Minimum | Recommended |
|------|---------|-------------|
| OS Version | Android 8.0+ | Android 10+ |
| RAM | 3GB | 4GB+ |
| Storage | 32GB | 64GB+ |
| Screen | 5.5"+ | 6.0"+ (for automation visibility) |
| Battery | Removable preferred | 3000mAh+ |
| Network | 4G LTE | 5G capable (future-proof) |

### Recommended Models (Cost-Effective)

| Model | Used Price (MYR) | Notes |
|-------|------------------|-------|
| **Samsung Galaxy A12** | RM 320-400 | Reliable, good automation support |
| **Samsung Galaxy A21** | RM 360-440 | Better performance, 4GB RAM |
| **Samsung Galaxy A32** | RM 400-480 | 5G capable, 4GB+ RAM |
| **Xiaomi Redmi Note 9** | RM 280-360 | Budget option, MIUI automation |
| **Xiaomi Redmi Note 10** | RM 320-400 | AMOLED, better battery |
| **Motorola Moto G Power** | RM 240-320 | Stock Android, reliable |

### Models to Avoid

- ❌ **iPhones** — Expensive (RM 800+ used), harder to automate, iOS restrictions
- ❌ **No-name Chinese brands** — Unreliable, poor automation support, driver issues
- ❌ **Phones with <3GB RAM** — WhatsApp crashes, slow automation
- ❌ **Android <8.0** — WhatsApp dropping support, security issues

---

## RACK SYSTEMS

### Types

#### 1. Fixed Tray Systems
- Non-adjustable shelves pre-configured for specific phone sizes
- **Pros:** High density, lower cost, easier cabling
- **Cons:** Inflexible for mixed device models

#### 2. Modular Adjustable Trays
- Vertical spacing adjustment for various phone thicknesses
- **Pros:** Future-proof, supports model rotation
- **Cons:** Less dense packing, higher cost

#### 3. Drawer-Based Enclosures
- Trays slide out like server drawers
- **Pros:** Excellent serviceability, easy maintenance
- **Cons:** Requires more depth, increased cost

### Specifications

| Feature | Budget | Mid-Range | High-End |
|---------|--------|-----------|----------|
| **Capacity** | 1000 phones | 1000 phones | 1000 phones |
| **Material** | Steel sheet | Powder-coated steel | Aluminum + steel |
| **Cooling** | Passive vents | Forced air + fans | Variable-speed + sensors |
| **Power** | Manual strips | Smart PDU | Redundant PDU + UPS |
| **Network** | Basic switch | Gigabit managed | Enterprise + WiFi |
| **Monitoring** | None | Basic temp sensors | Full SNMP + API |
| **Price (MYR)** | RM 32,000-50,000 | RM 60,000-80,000 | RM 80,000-100,000 |

---

## POWER REQUIREMENTS

### Calculation

```
Per phone: ~5W average (charging + operation)
1000 phones: 5W × 1000 = 5,000W = 5kW
USB hubs: ~100W total
Network equipment: ~200W
Cooling fans: ~300W
Control server: ~400W

Total: ~6kW continuous draw
```

### Daily Consumption

```
6kW × 24 hours = 144 kWh/day
144 kWh × 30 days = 4,320 kWh/month
```

### Malaysia Electricity Cost

```
Commercial rate: ~RM 0.45/kWh
Monthly cost: 4,320 kWh × RM 0.45 = RM 1,944/month
```

### Power Infrastructure

| Component | Specification | Cost (MYR) |
|-----------|---------------|------------|
| Dedicated circuit | 32A, single-phase | RM 2,000-4,000 |
| Smart PDU | 24-port, remote monitoring | RM 2,000-4,000 |
| UPS backup | 10kVA, 30min runtime | RM 8,000-15,000 |
| Surge protection | Whole-system | RM 1,000-2,000 |

---

## COOLING REQUIREMENTS

### Heat Output

```
6kW power draw = 6kW heat output
Equivalent to: 6 large space heaters running continuously
```

### Cooling Solutions

| Solution | Capacity | Cost (MYR) | Notes |
|----------|----------|------------|-------|
| **Passive vents** | Up to 2kW | RM 500-1,000 | Insufficient for 1000 phones |
| **Exhaust fans** | 3-5kW | RM 1,500-3,000 | Minimum viable |
| **Forced air + ducting** | 5-8kW | RM 4,000-8,000 | Recommended |
| **Portable AC unit** | 10kW+ | RM 8,000-15,000 | Best for enclosed rooms |
| **Liquid cooling** | 20kW+ | RM 20,000+ | Overkill for phone farms |

### Temperature Targets

| Metric | Target | Warning | Critical |
|--------|--------|---------|----------|
| Ambient room temp | 20-24°C | 25-28°C | >30°C |
| Phone surface temp | 30-35°C | 36-40°C | >42°C |
| USB hub temp | 35-45°C | 46-55°C | >60°C |

### Monitoring

Install temperature sensors at:
- Phone tray level (multiple points)
- USB hub locations
- Power supply units
- Room exhaust outlets

---

## NETWORK INFRASTRUCTURE

### Bandwidth Requirements

```
Per phone: ~50-100 Kbps average (WhatsApp messaging)
1000 phones: 50-100 Mbps aggregate
Recommended: 500 Mbps - 1 Gbps connection
```

### Network Topology

```
Internet (1 Gbps)
    │
    ├── Enterprise Router (RM 1,500-3,000)
    │
    ├── Managed Switch #1 (48-port, RM 1,000-2,000)
    │       ├── USB Hub Group 1 (phones 1-200)
    │       ├── USB Hub Group 2 (phones 201-400)
    │       └── USB Hub Group 3 (phones 401-600)
    │
    └── Managed Switch #2 (48-port, RM 1,000-2,000)
            ├── USB Hub Group 4 (phones 601-800)
            ├── USB Hub Group 5 (phones 801-1000)
            └── Control Server + Monitoring
```

### IP Rotation Strategy

| Approach | Cost (MYR) | Detection Risk |
|----------|------------|----------------|
| Single IP (all phones) | RM 0 | HIGH — correlated activity |
| Residential proxies (per 50 phones) | RM 2,000-5,000/month | Medium |
| Mobile data (SIM per phone) | RM 20,000-60,000/month | Low |
| Hybrid (WiFi + mobile data) | RM 10,000-30,000/month | Low-Medium |

### Recommended: Hybrid Network

```
- 70% of phones on WiFi (bulk messaging)
- 30% of phones on mobile data (high-value accounts)
- Rotate groups weekly
```

---

## CONTROL SERVER SPECIFICATIONS

### Minimum Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| CPU | 8-core (Ryzen 7 / i7) | 16-core (Ryzen 9 / i9) |
| RAM | 32GB DDR4 | 64GB DDR4 |
| Storage | 500GB NVMe SSD | 1TB NVMe SSD |
| USB Controllers | 4× USB 3.0 | 8× USB 3.1 |
| Network | 1 Gbps Ethernet | 2.5 Gbps + WiFi 6 |
| OS | Ubuntu 22.04 LTS | Ubuntu 24.04 LTS |

### Cost Estimate

| Configuration | Cost (MYR) |
|---------------|------------|
| Budget (8-core, 32GB) | RM 8,000-10,000 |
| Recommended (16-core, 64GB) | RM 12,000-16,000 |
| High-end (32-core, 128GB) | RM 20,000-25,000 |

### Software Stack

```
Operating System: Ubuntu 22.04/24.04 LTS
Container Runtime: Docker 24+
Orchestration: Docker Compose / Kubernetes (optional)
Device Control: ADB (Android Debug Bridge)
Automation: Python + Appium / Tasker
Database: PostgreSQL / MongoDB (for logs)
Monitoring: Prometheus + Grafana
```

---

## AUTOMATION SOFTWARE

### Open Source (Free)

| Tool | Purpose | Complexity |
|------|---------|------------|
| **ADB** | Device control, bulk commands | Medium |
| **scrcpy** | Screen mirroring, control | Low |
| **Appium** | Mobile automation framework | High |
| **Python + uiautomator2** | Custom automation scripts | High |

### Commercial

| Tool | Cost (MYR) | Purpose |
|------|------------|---------|
| **Tasker** | RM 12-20/device (one-time) | On-device automation |
| **Automate** | RM 8-15/device (one-time) | Visual flow automation |
| **MoreLogin Cloud Phone** | RM 40-120/device/month | Cloud-based alternative |

### Custom Development

```python
# Example: ADB bulk command
import subprocess

phone_ips = ["192.168.1.101", "192.168.1.102", ...]  # 1000 phones

for ip in phone_ips:
    subprocess.run([
        "adb", "-s", f"{ip}:5555",
        "shell", "am", "start",
        "-n", "com.whatsapp/.Home"
    ])
```

---

## LOCAL SOURCING (MALAYSIA)

### Used Phones

| Platform | Price Range | Notes |
|----------|-------------|-------|
| **Mudah.my** | RM 250-500/unit | Bulk negotiation possible (15-25% off) |
| **Facebook Marketplace** | RM 200-450/unit | Cash deals, immediate pickup |
| **Low Yat Plaza (KL)** | RM 300-550/unit | Warranty options, bulk suppliers |
| **Shopee/Lazada (Bulk)** | RM 280-480/unit | Escrow protection, delivery time |
| **Carousell Malaysia** | RM 220-400/unit | Individual sellers, varied conditions |

### Bulk Purchase Strategy

1. **Contact 5-10 sellers** on Mudah.my with 500+ unit listings
2. **Negotiate 20-25% discount** for 1000+ unit purchase
3. **Request samples** (5-10 units) before bulk order
4. **Inspect for:**
   - Battery health (>80% capacity)
   - Screen condition (no dead pixels)
   - All buttons functional
   - USB port not loose
   - Camera working (for verification)
5. **Factory reset** all devices before deployment

### Rack Systems

| Source | Product | Price (MYR) |
|--------|---------|-------------|
| **Alibaba (Telarvo)** | 128-port SIM Bank | RM 3,200-6,000 |
| **Alibaba (OEM)** | 1000-phone rack system | RM 32,000-100,000 |
| **Local fabrication** | Custom rack (Malaysia) | RM 40,000-80,000 |
| **Server surplus** | Used server rack + modification | RM 15,000-30,000 |

---

## VENDORS & SUPPLIERS

### Hardware (International)

| Supplier | Product | MOQ | Price (MYR) |
|----------|---------|-----|-------------|
| **Shenzhen Etross Telecom** | GoIP GSM Gateway 32-port | 1 | RM 2,400-4,800 |
| **Telarvo Store** | 128-port SIM Bank | 1 | RM 3,200-6,000 |
| **Various OEMs (Alibaba)** | 1000-phone rack system | 1 | RM 32,000-100,000 |

### Cloud Phone Alternatives

| Service | Cost (MYR) | Scale | Notes |
|---------|------------|-------|-------|
| **GeeLark** | RM 40-80/device/month | Instant | Cloud Android instances |
| **Redfinger** | RM 50-100/device/month | Instant | 24/7 cloud phones |
| **MoreLogin** | RM 60-120/device/month | Instant | Anti-detect built-in |

### Cloud vs. Physical Comparison

| Factor | Physical Farm | Cloud Farm |
|--------|---------------|------------|
| **CAPEX (5000 phones)** | RM 2.0M-3.0M | RM 0 |
| **OPEX (3 months)** | RM 300,000-500,000 | RM 1.2M-1.5M |
| **Setup time** | 4-6 weeks | Instant |
| **Physical footprint** | 500-1000 sq ft | None |
| **Detection risk** | Medium | Medium-High (IP correlation) |
| **Control** | Full | Limited (provider-dependent) |

---

## MAINTENANCE REQUIREMENTS

### Daily

- [ ] Monitor temperature sensors (all zones)
- [ ] Check power consumption (anomalies = device failures)
- [ ] Verify network connectivity (ping test all groups)
- [ ] Review automation logs (failed commands)

### Weekly

- [ ] Physical inspection (random sample 50 phones)
- [ ] USB cable integrity check (replace frayed cables)
- [ ] Fan cleaning (dust buildup)
- [ ] Software updates (security patches)

### Monthly

- [ ] Full factory reset (20% of phones, rotating)
- [ ] Battery health assessment (replace <70% capacity)
- [ ] Deep clean (all fans, vents, filters)
- [ ] Cable replacement (preventive, 10% of cables)

### Quarterly

- [ ] Full infrastructure audit
- [ ] Firmware updates (all devices)
- [ ] Power supply testing (load test UPS)
- [ ] Network equipment firmware updates

---

## FAILURE MODES & MITIGATION

| Failure | Probability | Impact | Mitigation |
|---------|-------------|--------|------------|
| **Device overheating** | High | Medium | Active cooling, thermal sensors, auto-shutdown |
| **USB hub failure** | Medium | High | Redundant hubs, 10% spare inventory |
| **Power failure** | Low | Critical | UPS backup, generator, redundant circuits |
| **Network outage** | Medium | High | Dual ISP, 4G/5G fallback |
| **WhatsApp mass ban** | High | Critical | Portfolio separation, warm-up, backup accounts |
| **Fire** | Low | Critical | Smoke detectors, fire suppression, insurance |
| **Theft** | Low | Critical | Secure location, surveillance, access control |

---

## BUDGET BREAKDOWN (5000-PHONE FARM)

| Component | Low (MYR) | High (MYR) |
|-----------|-----------|------------|
| **Phones (5000 × RM 320-480)** | RM 1,600,000 | RM 2,400,000 |
| **Rack Systems (5 units)** | RM 160,000 | RM 500,000 |
| **Networking & Power** | RM 80,000 | RM 160,000 |
| **Cooling & Infrastructure** | RM 40,000 | RM 80,000 |
| **Control Servers (2×)** | RM 24,000 | RM 40,000 |
| **SIM Cards (5000 units)** | RM 100,000 | RM 400,000 |
| **Proxies & Data (3 months)** | RM 180,000 | RM 540,000 |
| **Contingency (15%)** | RM 330,000 | RM 618,000 |
| **TOTAL** | **RM 2,514,000** | **RM 4,738,000** |

**Recommended Budget Allocation:** RM 3.0M-3.5M

---

## SOURCES

1. Alibaba Buying Guide — "How to Choose Box Phone Farm System 1000 Phones"
2. Telarvo Store — SIM Bank specifications
3. AnandTech — "Mobile Device Farm Design Challenges"
4. TechRadar — "Benefits of On-Premise Device Farms"
5. Local Malaysia pricing — Mudah.my, Low Yat Plaza (June 2026)

---

**END OF DOCUMENT**
