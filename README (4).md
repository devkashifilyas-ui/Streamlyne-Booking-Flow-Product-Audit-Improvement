# ISI® Platform Architecture Simulation  
### Mindbody API • Multi-Location Scaling • Caching Strategy • Failure Handling

---

## 🚀 What This Is

This is not a UI demo.

This is a **working simulation of how a production-grade multi-location fitness platform behaves under real conditions** — including API latency, failures, caching, and traffic spikes.

Built to demonstrate how a system like ISI® Elite Training can scale across **60+ locations** without breaking under load or dependency failures.

---

## 🎯 What This Demonstrates

### 1. API Rate Limiting & Stability
- Simulated Mindbody API with:
  - 300–800ms latency
  - ~12% failure rate
- Retry logic with exponential backoff
- Graceful fallback when API fails

👉 Result: No broken UI, no blocked user flow

---

### 2. Smart Caching Strategy
- In-memory cache with 60s TTL
- Cache states:
  - HIT
  - MISS
  - EXPIRED
  - FALLBACK
- Per-location cache isolation

👉 Result: Reduced API load + near real-time experience

---

### 3. Multi-Location Architecture
- 8 simulated locations
- Independent data flow per location
- Presales vs Open state handling

👉 Result: Scales cleanly from 1 → 100+ locations

---

### 4. Traffic Spike Handling
- “Traffic Spike” button simulates 20 parallel requests
- Throttled to max 6 concurrent requests
- Queue system prevents API overload

👉 Result: No API hammering during campaign spikes

---

### 5. Failure Handling (Critical)
- API failures do NOT break UI
- System serves fallback data
- Logs + alerts triggered

👉 Result: System remains usable under failure

---

### 6. CMS Behavior Simulation
- Editable location data (name, city, tier, status)
- Cache auto-invalidates on update

👉 Result: HQ can manage content without dev dependency

---

### 7. Tracking Layer Simulation
- Events fired:
  - location_view
  - schedule_load
  - booking_click
- Displayed as real-time GA4-style logs

👉 Result: Clean tracking across full funnel

---

## 🖥️ How to Use

1. Download or clone this repo  
2. Open `index.html` in any browser  
3. No install. No setup. No server required  

---

## 🧪 How to Test (Important)

### Test 1 — Caching
- Click a location → fetch schedule  
- Click again within 60 seconds  

✅ Second request = instant (cache HIT)

---

### Test 2 — Failure Handling
- Click multiple locations repeatedly  

✅ Occasionally API fails → fallback data shown  
✅ UI remains stable

---

### Test 3 — Traffic Spike
- Click **“Traffic Spike”**

✅ 20 requests fired  
✅ Only 6 run concurrently  
✅ Others queued  
✅ No system overload

---

### Test 4 — CMS Update
- Click **“Update CMS Data”**  
- Change location info  

✅ Cache invalidates  
✅ UI updates instantly  

---

## 🧠 Why This Matters

Most implementations:
- Call APIs directly from frontend
- Break under load
- Fail silently
- Fix performance after launch

This approach:
- Controls API access through an internal layer
- Uses caching + throttling from day one
- Handles failure as a system feature (not an edge case)

---

## ⚙️ Architecture Mindset

This demo represents a production approach:

- **Internal API Layer** → controls all external requests  
- **Caching Layer** → reduces load + improves speed  
- **Queue + Throttle** → protects against spikes  
- **Fallback Strategy** → ensures continuity  
- **Tracking Layer** → consistent analytics across flows  

---

## 🔥 Key Takeaway

This is not about rendering pages.

This is about building a system that:
- Doesn’t break under pressure  
- Doesn’t overload external APIs  
- Doesn’t lose tracking data  
- Doesn’t depend on constant developer intervention  

---

## 📩 If You’re Reviewing This

If this reflects how you expect your production system to behave,  
I can map this exact simulation directly into your live architecture.

---

**Built to simulate real-world behavior — not just frontend output.**
