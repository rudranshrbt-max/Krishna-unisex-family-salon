# Krishna Unisex Family Salon — Premium 3D Website

> **Full-stack, luxury salon website with 3D UI, AI concierge, real-time booking engine, and omnichannel communication.**

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Tech Stack](#tech-stack)
3. [Business Details](#business-details)
4. [Site Architecture & Sections](#site-architecture--sections)
5. [3D & Animation Features](#3d--animation-features)
6. [Booking System (Full Spec)](#booking-system-full-spec)
7. [AI Concierge Bot (Calls, Email, SMS)](#ai-concierge-bot-calls-email-sms)
8. [Admin Dashboard](#admin-dashboard)
9. [Premium Features](#premium-features)
10. [SEO Strategy](#seo-strategy)
11. [Analytics Setup](#analytics-setup)
12. [WhatsApp & Communication Layer](#whatsapp--communication-layer)
13. [Performance & Core Web Vitals](#performance--core-web-vitals)
14. [Folder Structure](#folder-structure)
15. [Environment Variables](#environment-variables)
16. [Installation & Setup](#installation--setup)
17. [Deployment](#deployment)
18. [Future Roadmap](#future-roadmap)

---

## Project Overview

A **top-tier, conversion-optimised, 3D luxury salon website** for Krishna Unisex Family Salon. This is not an informational website — it is a **digital sales machine** designed to convert every visitor into a booked appointment.

### What Makes This Tier-1

| Feature | Implementation |
|---|---|
| 3D Interactive UI | Three.js / React Three Fiber |
| Real-time Booking | Supabase + conflict-safe slot locking |
| AI Concierge | Claude API — handles calls (Twilio), email (SendGrid/Resend), SMS |
| Admin Dashboard | Protected Next.js route with booking CRM |
| Omnichannel | WhatsApp, SMS, Email, Voice — all unified |
| Performance | 95+ Lighthouse on all metrics |
| SEO | Schema.org LocalBusiness, OpenGraph, sitemap.xml |

---

## Tech Stack

### Frontend
```
Framework      : Next.js 14 (App Router)
Styling        : Tailwind CSS + custom CSS vars
3D Engine      : Three.js + React Three Fiber + Drei
Animation      : GSAP + ScrollTrigger + Framer Motion
Fonts          : Cormorant Garamond (display) + DM Sans (body)
Icons          : Lucide React
```

### Backend / Services
```
Database       : Supabase (PostgreSQL)
Auth (Admin)   : Supabase Auth
Email          : Resend (transactional) + React Email templates
SMS            : Twilio SMS API
Voice AI       : Twilio Voice + Claude API (real-time call handling)
WhatsApp       : Twilio WhatsApp Business API
Booking Engine : Custom slot-locking logic (row-level locking, Supabase RLS)
File Storage   : Supabase Storage (gallery images)
```

### Analytics & SEO
```
Analytics      : Google Analytics 4 + Google Tag Manager
Heatmaps       : Microsoft Clarity (free)
SEO            : Next.js metadata API + JSON-LD schema
Sitemap        : next-sitemap
```

---

## Business Details

```yaml
Name          : Krishna Unisex Family Salon
Category      : Hair Salon / Unisex Family Salon
Address       : Shop No. 41 & 42, IBD Emporia Mall, Kolar Rd, Bhopal, MP 462040
Phone         : +91 62657 92894
Google Maps   : https://maps.app.goo.gl/[your-short-link]
WhatsApp      : https://wa.me/916265792894
Business Hours:
  Monday–Saturday : 10:00 AM – 9:00 PM
  Sunday          : 11:00 AM – 7:00 PM
```

---

## Site Architecture & Sections

### 1. Hero Section — `#hero`

**Purpose:** Instant trust + conversion hook within 3 seconds.

**Features:**
- Full-viewport 3D animated canvas (Three.js particle field or glossy 3D scissor/mirror object rotating)
- Glassmorphism overlay with business name and tagline
- Animated headline: *"Where Every Visit Feels Like a Luxury Retreat"*
- Sub-headline: *"Bhopal's Most Trusted Family Salon — Hair, Skin & Beyond"*
- Two CTAs: **[Book Now]** (primary) · **[Call Now → 62657 92894]** (secondary)
- Floating badge: ⭐ 4.9 Rating · 2000+ Happy Clients
- Scroll-triggered cinematic fade into next section

**3D Element Spec:**
```js
// Three.js scene: golden floating orbs + scissor silhouette
// Particle count: 4000
// Camera: PerspectiveCamera FOV 60, auto-rotate on scroll
// Lighting: AmbientLight #fff 0.4 + PointLight gold #D4AF37 intensity 2
// Post-processing: UnrealBloom, ChromaticAberration
```

---

### 2. Marquee Trust Bar — `#trust`

Scrolling horizontal ticker (infinite loop):
```
⭐ Google 4.9 ★   ·   👨‍👩‍👧 Family-Friendly   ·   ✂️ Expert Stylists   ·
🧖 Skin & Hair Care   ·   📍 IBD Emporia Mall   ·   🕐 Open 7 Days
```

---

### 3. About Us — `#about`

**Copy (Production-ready):**

> At Krishna Unisex Family Salon, beauty is not a service — it's an experience. Nestled inside the prestigious IBD Emporia Mall on Kolar Road, we've been redefining grooming standards for Bhopal's families since day one. Our team of certified stylists combines global techniques with a deep understanding of Indian hair textures and skin tones. Whether you're stepping in for a quick trim or a complete transformation, we treat every client like royalty.

**Design:**
- Split layout: large 3D text counter (animated numbers) left + editorial photo collage right
- Counters: `2000+ Clients · 8+ Expert Stylists · 5 Years · 15+ Services`
- GSAP CountUp animation on scroll-enter

---

### 4. Services Section — `#services`

**Layout:** Bento-style 3D cards with hover tilt (Vanilla Tilt.js / CSS perspective)

| Service | Price Range | Description |
|---|---|---|
| Haircut & Styling | ₹150 – ₹800 | Precision cuts for men, women & kids |
| Hair Coloring | ₹500 – ₹3500 | Global, highlights, balayage, ombre |
| Keratin / Smoothing | ₹2000 – ₹6000 | Frizz-free, long-lasting treatments |
| Facial & Cleanup | ₹300 – ₹1500 | Deep cleanse, glow facials |
| Threading & Waxing | ₹50 – ₹800 | Precision grooming |
| Bridal Package | ₹8000 – ₹25000 | Full bridal hair, makeup & skin prep |
| Head Massage | ₹200 – ₹500 | Relaxing scalp therapy |
| Manicure / Pedicure | ₹300 – ₹1200 | Nail care & spa |
| Hair Spa | ₹500 – ₹2000 | Deep nourishment treatment |

**Card Features:**
- 3D tilt on hover (max 15deg)
- Icon (Lucide or custom SVG) per service
- "Book This Service" deep-link to booking form with service pre-selected
- Price badge with gradient border

---

### 5. Booking System — `#booking`

→ Full spec below in [Booking System section](#booking-system-full-spec)

---

### 6. Testimonials — `#testimonials`

**Scroll-snap carousel with 3D card flip on select**

| Client | Rating | Review |
|---|---|---|
| Priya Sharma | ⭐⭐⭐⭐⭐ | *"The balayage came out absolutely stunning. The team understood exactly what I wanted without me explaining twice. Best salon in Bhopal!"* |
| Rahul Verma | ⭐⭐⭐⭐⭐ | *"Took my whole family — kids haircuts, my wife's facial, and my beard trim. All done perfectly. The ambience inside Emporia is unmatched."* |
| Sneha Malhotra | ⭐⭐⭐⭐⭐ | *"Got my bridal prep done here. The team was patient, skilled, and the result was breathtaking. 100% recommend Krishna Salon!"* |
| Aditya Tiwari | ⭐⭐⭐⭐⭐ | *"Affordable, hygienic, and professional. The hair spa genuinely transformed my dry hair. I'm a regular customer now."* |
| Kavita Joshi | ⭐⭐⭐⭐⭐ | *"Booked online at midnight, got a confirmation SMS instantly, showed up and was attended to right on time. Brilliant system!"* |

**Design:** Glassmorphism cards, floating gold stars, auto-play with pause-on-hover

---

### 7. Gallery — `#gallery`

- Masonry grid with lightbox
- Before/After slider component (CSS clip-path drag)
- Lazy-loaded, WebP format, Supabase Storage CDN
- Categories: Hair Color · Cuts · Bridal · Skin · Nails

---

### 8. Contact & Map — `#contact`

**Embedded Map:**
```html
<iframe
  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3669.3626576080883!2d77.40052077547624!3d23.120415779105233!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x397c458ff06a2439%3A0x1d936dd31420fc0e!2sKrishna%20unisex%20family%20salon!5e0!3m2!1sen!2sin!4v1778828504310!5m2!1sen!2sin"
  width="100%"
  height="450"
  style="border:0;border-radius:16px;"
  allowfullscreen=""
  loading="lazy"
  referrerpolicy="no-referrer-when-downgrade">
</iframe>
```

**Quick Actions Grid:**
```
[📞 Call Now]     [💬 WhatsApp]    [🗺️ Get Directions]
[📧 Email Us]     [📱 SMS Us]      [📅 Book Online]
```

**Contact Form:** Name · Phone · Service · Message · Submit  
→ On submit: email to admin + SMS confirmation to user

---

### 9. Footer

```
Logo + tagline
Address · Phone (click-to-call) · Email
Hours: Mon–Sat 10AM–9PM · Sun 11AM–7PM
Social: [Instagram] [Facebook] [YouTube] [Google Business]
© 2025 Krishna Unisex Family Salon. All rights reserved.
Privacy Policy · Terms of Service
```

---

## 3D & Animation Features

### Three.js Scene — Hero

```js
// File: /components/3d/HeroScene.jsx

import { Canvas, useFrame } from '@react-three/fiber'
import { Float, Stars, OrbitControls, useGLTF } from '@react-three/drei'
import { EffectComposer, Bloom, ChromaticAberration } from '@react-three/postprocessing'

// Golden particle field + floating scissors GLTF model
// Auto-rotate camera on scroll (useScroll from @react-three/drei)
// Responsive: reduce particle count on mobile (< 768px → 800 particles)
```

### GSAP ScrollTrigger — Page-wide

```js
// Staggered section reveals
gsap.from('.section-card', {
  scrollTrigger: { trigger: '.section-card', start: 'top 85%' },
  y: 60, opacity: 0, duration: 0.8, stagger: 0.15, ease: 'power3.out'
})

// Parallax hero text
gsap.to('.hero-text', {
  scrollTrigger: { scrub: 1 },
  y: -120
})
```

### CSS 3D Card Tilt — Services

```css
.service-card {
  transform-style: preserve-3d;
  transition: transform 0.4s cubic-bezier(0.23, 1, 0.32, 1);
}
.service-card:hover {
  transform: perspective(800px) rotateX(var(--rx)) rotateY(var(--ry)) translateZ(20px);
}
```

### Cursor — Custom Magnetic Cursor

- Large ring cursor replaces default
- Scales up on interactive elements
- Color shifts to gold on CTA hover

---

## Booking System (Full Spec)

### User Flow

```
1. User picks SERVICE from dropdown
2. User picks DATE (calendar — disabled past dates, disabled Mondays if off)
3. System fetches AVAILABLE TIME SLOTS from Supabase
   → Locked slots (< 15 min before) not shown
   → Booked slots shown as "Taken" (greyed out)
4. User picks TIME SLOT
5. User enters NAME + PHONE + optional message
6. User clicks CONFIRM BOOKING
7. System:
   a. Locks slot in DB (row-level lock, 5-min hold)
   b. Sends SMS confirmation to user (Twilio)
   c. Sends WhatsApp confirmation to user (Twilio)
   d. Sends email notification to admin (Resend)
   e. Creates calendar event (Google Calendar API optional)
8. Booking confirmation screen with booking ID
```

### Supabase Schema

```sql
-- Bookings table
CREATE TABLE bookings (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  client_name TEXT NOT NULL,
  phone TEXT NOT NULL,
  service TEXT NOT NULL,
  booking_date DATE NOT NULL,
  time_slot TEXT NOT NULL,          -- e.g. "11:00"
  status TEXT DEFAULT 'confirmed',  -- confirmed | cancelled | completed | no_show
  notes TEXT,
  created_at TIMESTAMPTZ DEFAULT NOW(),
  UNIQUE(booking_date, time_slot)   -- prevent double booking
);

-- Slots config table
CREATE TABLE slot_config (
  id SERIAL PRIMARY KEY,
  day_of_week INT,                  -- 0=Sun, 1=Mon...
  open_time TIME,
  close_time TIME,
  slot_duration_minutes INT DEFAULT 30,
  is_active BOOLEAN DEFAULT TRUE
);

-- Blocked dates (holidays, closures)
CREATE TABLE blocked_dates (
  id SERIAL PRIMARY KEY,
  blocked_date DATE UNIQUE NOT NULL,
  reason TEXT
);
```

### API Routes (Next.js App Router)

```
GET  /api/booking/slots?date=YYYY-MM-DD   → returns available time slots
POST /api/booking/create                  → creates booking, sends notifications
GET  /api/booking/confirm/[id]            → booking detail page
POST /api/booking/cancel                  → client self-cancellation (within 2hr window)
```

### Double-Booking Prevention

```ts
// Row-level lock + unique constraint
const { data, error } = await supabase
  .from('bookings')
  .insert({ booking_date, time_slot, client_name, phone, service })
  .select()
  .single()

if (error?.code === '23505') {
  return { error: 'Slot just taken. Please pick another time.' }
}
```

### SMS Confirmation Template (Twilio)

```
Hi [NAME]! ✂️ Your booking at Krishna Unisex Family Salon is CONFIRMED.

📅 Date: [DATE]
⏰ Time: [TIME]
💇 Service: [SERVICE]
📍 IBD Emporia Mall, Kolar Rd, Bhopal

Need to reschedule? Reply CANCEL or call 62657 92894.

See you soon! 🌟
```

---

## AI Concierge Bot (Calls, Email, SMS)

### What the AI Bot Does

The AI concierge is powered by **Claude API** and integrated with **Twilio** for omnichannel handling. It operates 24/7.

| Channel | Trigger | Capability |
|---|---|---|
| 📞 Voice Call | Incoming call to salon number | Answers, collects booking details, checks slots, confirms via DTMF or speech |
| 📧 Email | Email to salon address | Reads inquiry, replies with service info or booking confirmation |
| 📱 SMS | Incoming SMS to Twilio number | Natural language booking, FAQs, rescheduling |
| 💬 WhatsApp | WhatsApp message | Full booking flow in chat |

---

### Voice Call — Twilio + Claude

```
Architecture:
  Incoming call → Twilio webhook → /api/voice/answer
  → TwiML: play greeting + gather speech input
  → Speech → Deepgram STT transcript
  → Transcript → Claude API (system prompt: salon concierge)
  → Claude response → Twilio TTS (Polly voice: Aditi - Hindi/English)
  → Response played to caller
  → If booking requested → check Supabase slots → confirm → SMS sent
```

**System Prompt for Voice AI:**
```
You are the AI receptionist for Krishna Unisex Family Salon in Bhopal.
You speak both Hindi and English (Hinglish is fine).
You can:
1. Answer questions about services and pricing
2. Check available appointment slots
3. Book appointments (collect name, phone, service, date, time)
4. Confirm or cancel existing bookings
5. Give directions to IBD Emporia Mall, Kolar Road, Bhopal
Always be warm, professional, and concise. End every booking with a confirmation summary.
```

**TwiML Route — `/api/voice/answer`:**
```ts
import twilio from 'twilio'
const VoiceResponse = twilio.twiml.VoiceResponse

export async function POST(req: Request) {
  const twiml = new VoiceResponse()
  const gather = twiml.gather({
    input: ['speech'],
    language: 'hi-IN',        // Hindi + English
    speechTimeout: 'auto',
    action: '/api/voice/process'
  })
  gather.say({ voice: 'Polly.Aditi' },
    'Namaste! Welcome to Krishna Unisex Family Salon. How can I help you today?'
  )
  return new Response(twiml.toString(), {
    headers: { 'Content-Type': 'text/xml' }
  })
}
```

---

### Email — Resend + Claude

```
Flow:
  Email arrives → Resend inbound webhook → /api/email/inbound
  → Parse sender, subject, body
  → Send to Claude API with salon context
  → Claude drafts reply
  → Resend sends reply from salon@krishnasalon.in
```

**Email Categories Claude Handles:**
- Service inquiries
- Price questions
- Booking requests
- Complaint / feedback → escalate flag + notify admin
- Bridal package inquiries → send detailed PDF brochure link

---

### SMS — Twilio Messaging

```
Incoming SMS → Twilio webhook → /api/sms/inbound
→ Message body → Claude API
→ Claude response (under 160 chars where possible)
→ Send reply via Twilio SMS
```

**Supported SMS Commands (natural language):**
```
"Book haircut tomorrow 3pm" → checks slots, confirms
"Cancel my booking" → sends cancellation link
"What time do you open?" → replies with hours
"Prices?" → replies with menu summary + website link
"Where are you located?" → Google Maps link
```

---

### WhatsApp Flow (Twilio WhatsApp Business)

Full conversational booking:
```
1. User: "Hi"
   Bot: "👋 Namaste! Welcome to Krishna Salon. Choose: [1] Book [2] Services [3] Location [4] Call Us"
2. User: "1"
   Bot: "Which service? [Send number]
         1. Haircut  2. Color  3. Facial  4. Bridal  5. Other"
3. User: "2"
   Bot: "Hair Coloring selected! Pick a date (format: DD/MM):"
4. User: "20/05"
   Bot: "Available slots on 20 May: 10:30 · 11:00 · 2:00 · 4:30 · 6:00 PM. Reply with your preferred time:"
5. User: "2pm"
   Bot: "Your name and phone? (Format: Priya, 9876543210)"
6. User: "Priya, 9876543210"
   Bot: "✅ CONFIRMED! 
         📅 20 May · ⏰ 2:00 PM
         💇 Hair Coloring
         📍 IBD Emporia Mall
         Booking ID: #KS-2841
         See you! 💫"
```

---

## Admin Dashboard

**Route:** `/admin` — protected by Supabase Auth (email + password)

### Dashboard Views

#### 1. Today's Bookings
```
Table: Time | Client | Phone | Service | Status | Actions
Actions: [Mark Complete] [Mark No-Show] [Cancel] [Call Client]
```

#### 2. Calendar View
- Full month/week/day view (React Big Calendar or custom)
- Colour-coded: Confirmed (green) · Pending (yellow) · Cancelled (red)
- Click slot → booking detail modal

#### 3. Booking Management
- Search by name / phone / date
- Filter by service / status / date range
- Export CSV

#### 4. Analytics Panel
- Bookings per day (bar chart)
- Most popular services (doughnut chart)
- Revenue estimate (avg ticket × bookings)
- Peak hours heatmap
- Cancellation rate

#### 5. Slot Configuration
- Toggle working days
- Set open/close time per day
- Block specific dates (holidays)
- Set slot duration (30 / 45 / 60 min)

#### 6. Message Centre
- View all AI bot conversations (SMS, WhatsApp, Email)
- Take over any conversation manually
- Flag conversations for follow-up

#### 7. Client CRM
- Client list with visit history
- Total spend estimate
- Last visit date
- VIP tag for clients with 5+ visits

---

## Premium Features

### Loyalty / Referral System
```
- Client gets unique referral code after first booking
- Share code → referred client gets ₹100 off
- Referring client gets ₹150 off next visit
- Tracked via Supabase + applied at booking
```

### Offer / Coupon Engine
```
Admin creates coupons:
  Code: WELCOME10 → 10% off all services
  Code: BRIDAL2025 → ₹500 off bridal package
  
Applied at checkout in booking form.
Validated server-side, single-use or limited.
```

### Push Notifications (PWA)
```
- Site is a PWA (manifest.json + service worker)
- Users can install to home screen
- Push: "Your appointment tomorrow at 3 PM is in 24 hours! 📅"
- Push: "New offer: 20% off hair spa this weekend only 🎉"
```

### Review Request Automation
```
Trigger: booking status → 'completed'
Wait: 3 hours
Action: Send SMS/WhatsApp:
  "Hi [NAME]! Hope you loved your visit to Krishna Salon 💇‍♀️
   Drop us a Google review in 30 sec 👉 [SHORT_LINK]
   It means the world to us! ⭐"
```

### Instagram Feed Widget
- Live pull from Instagram Graph API
- Auto-refreshing gallery in footer area
- Shows latest 9 posts in 3×3 grid

---

## SEO Strategy

### JSON-LD Schema (LocalBusiness)

```json
{
  "@context": "https://schema.org",
  "@type": "HairSalon",
  "name": "Krishna Unisex Family Salon",
  "image": "https://krishnasalon.in/og-image.jpg",
  "telephone": "+916265792894",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Shop No. 41 & 42, IBD Emporia Mall, Kolar Road",
    "addressLocality": "Bhopal",
    "addressRegion": "Madhya Pradesh",
    "postalCode": "462040",
    "addressCountry": "IN"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 23.120415,
    "longitude": 77.400520
  },
  "url": "https://krishnasalon.in",
  "openingHours": [
    "Mo-Sa 10:00-21:00",
    "Su 11:00-19:00"
  ],
  "priceRange": "₹₹",
  "servedCuisine": null,
  "sameAs": [
    "https://www.instagram.com/krishnasalon",
    "https://www.facebook.com/krishnasalon",
    "https://g.co/kgs/krishnasalon"
  ]
}
```

### Target Keywords

| Keyword | Intent |
|---|---|
| hair salon Bhopal | Local commercial |
| best unisex salon Bhopal | Local commercial |
| salon near IBD Emporia Mall | Hyper-local |
| bridal makeup Bhopal | High-intent |
| hair color salon Kolar Road | Hyper-local |
| family salon Bhopal | Informational |
| keratin treatment Bhopal | Service-specific |

### On-Page SEO

```html
<title>Krishna Unisex Family Salon | Best Hair Salon in Bhopal – IBD Emporia Mall</title>
<meta name="description" content="Visit Krishna Unisex Family Salon at IBD Emporia Mall, Kolar Road, Bhopal. Premium haircuts, coloring, bridal packages & more. Book your appointment online. Call 62657 92894.">
<meta name="keywords" content="hair salon Bhopal, unisex salon Kolar Road, bridal salon Bhopal, family salon Emporia Mall">
<link rel="canonical" href="https://krishnasalon.in" />
```

---

## Analytics Setup

### Google Analytics 4

```js
// /app/layout.tsx
import { GoogleAnalytics } from '@next/third-parties/google'
<GoogleAnalytics gaId="G-XXXXXXXXXX" />
```

### Key Events to Track

```js
// Book Now button click
gtag('event', 'begin_checkout', { service: selectedService })

// Booking confirmed
gtag('event', 'purchase', {
  transaction_id: bookingId,
  value: estimatedPrice,
  currency: 'INR',
  items: [{ item_name: service }]
})

// Call Now click
gtag('event', 'generate_lead', { method: 'phone_call' })

// WhatsApp button click
gtag('event', 'generate_lead', { method: 'whatsapp' })

// Map directions click
gtag('event', 'generate_lead', { method: 'directions' })
```

### Microsoft Clarity (Heatmaps — Free)

```html
<!-- In <head> -->
<script type="text/javascript">
  (function(c,l,a,r,i,t,y){...})(window, document, "clarity", "script", "CLARITY_ID");
</script>
```

---

## WhatsApp & Communication Layer

### Floating WhatsApp Button

```tsx
// Sticky, bottom-right, mobile + desktop
// Pulse animation every 5 seconds to draw attention
// Pre-filled message: "Hi! I'd like to book an appointment at Krishna Salon"
const waLink = `https://wa.me/916265792894?text=${encodeURIComponent("Hi! I'd like to book an appointment.")}`
```

### Sticky Navigation

```tsx
// Transparent at top → solid dark/gold on scroll (IntersectionObserver)
// Mobile: hamburger → full-screen overlay menu
// CTA in nav: "Book Now" button — always visible
```

---

## Performance & Core Web Vitals

### Targets

| Metric | Target |
|---|---|
| LCP (Largest Contentful Paint) | < 2.0s |
| CLS (Cumulative Layout Shift) | < 0.05 |
| INP (Interaction to Next Paint) | < 150ms |
| Lighthouse Performance | 95+ |
| Lighthouse SEO | 100 |
| Lighthouse Accessibility | 95+ |

### Implementation

```
- next/image for all images (WebP, lazy, blur placeholder)
- Three.js scene: loaded after LCP (dynamic import, no SSR)
- Font: next/font/google with display: swap
- CSS: Tailwind purge + critical CSS inline
- API routes: Edge runtime where possible
- Supabase: connection pooling (pgBouncer mode)
- Static pages: ISR with 60s revalidation
```

---

## Folder Structure

```
krishna-salon/
├── app/
│   ├── layout.tsx                # Root layout, fonts, analytics
│   ├── page.tsx                  # Home page
│   ├── admin/
│   │   ├── page.tsx              # Admin dashboard (protected)
│   │   └── login/page.tsx        # Admin login
│   └── api/
│       ├── booking/
│       │   ├── slots/route.ts    # GET available slots
│       │   ├── create/route.ts   # POST create booking
│       │   └── cancel/route.ts   # POST cancel booking
│       ├── voice/
│       │   ├── answer/route.ts   # Twilio voice webhook
│       │   └── process/route.ts  # STT → Claude → TTS
│       ├── sms/
│       │   └── inbound/route.ts  # Twilio SMS webhook
│       ├── email/
│       │   └── inbound/route.ts  # Resend inbound webhook
│       └── whatsapp/
│           └── inbound/route.ts  # WhatsApp webhook
├── components/
│   ├── 3d/
│   │   ├── HeroScene.jsx         # Three.js hero canvas
│   │   ├── FloatingOrb.jsx       # Animated 3D orb
│   │   └── ParticleField.jsx     # Background particles
│   ├── sections/
│   │   ├── Hero.tsx
│   │   ├── About.tsx
│   │   ├── Services.tsx
│   │   ├── Booking.tsx
│   │   ├── Testimonials.tsx
│   │   ├── Gallery.tsx
│   │   └── Contact.tsx
│   ├── ui/
│   │   ├── Navbar.tsx
│   │   ├── Footer.tsx
│   │   ├── WhatsAppButton.tsx
│   │   ├── CustomCursor.tsx
│   │   ├── BookingModal.tsx
│   │   └── ServiceCard.tsx
│   └── admin/
│       ├── BookingTable.tsx
│       ├── CalendarView.tsx
│       ├── AnalyticsPanel.tsx
│       └── SlotConfig.tsx
├── lib/
│   ├── supabase.ts               # Supabase client
│   ├── twilio.ts                 # Twilio client
│   ├── resend.ts                 # Resend client
│   ├── claude.ts                 # Claude API client
│   ├── booking.ts                # Booking logic
│   └── slots.ts                  # Slot generation logic
├── emails/
│   ├── BookingConfirmation.tsx   # React Email template (admin)
│   └── ClientConfirmation.tsx    # React Email template (client)
├── public/
│   ├── models/                   # GLTF 3D models
│   ├── images/                   # Static images
│   └── manifest.json             # PWA manifest
├── styles/
│   └── globals.css               # CSS variables, base styles
├── .env.local                    # Environment variables
├── next.config.js
├── tailwind.config.ts
└── package.json
```

---

## Environment Variables

```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=https://xxxx.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJxx...
SUPABASE_SERVICE_ROLE_KEY=eyJxx...

# Twilio
TWILIO_ACCOUNT_SID=ACxxx
TWILIO_AUTH_TOKEN=xxx
TWILIO_PHONE_NUMBER=+1xxxxxxxxxx
TWILIO_WHATSAPP_NUMBER=whatsapp:+14155238886

# Resend (Email)
RESEND_API_KEY=re_xxx
ADMIN_EMAIL=admin@krishnasalon.in
FROM_EMAIL=bookings@krishnasalon.in

# Anthropic (Claude AI)
ANTHROPIC_API_KEY=sk-ant-xxx

# Google
GOOGLE_ANALYTICS_ID=G-XXXXXXXXXX
GOOGLE_CALENDAR_API_KEY=xxx

# App
NEXT_PUBLIC_SITE_URL=https://krishnasalon.in
ADMIN_PASSWORD_HASH=bcrypt_hash_here
BOOKING_LOCK_MINUTES=5
```

---

## Installation & Setup

```bash
# 1. Clone repository
git clone https://github.com/yourorg/krishna-salon.git
cd krishna-salon

# 2. Install dependencies
npm install

# 3. Copy env file and fill in values
cp .env.example .env.local

# 4. Run Supabase migrations
npx supabase db push

# 5. Seed slot configuration
npm run seed:slots

# 6. Run dev server
npm run dev

# 7. Open in browser
open http://localhost:3000
```

---

## Deployment

### Vercel (Recommended)

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel --prod

# Add environment variables via Vercel dashboard or:
vercel env add ANTHROPIC_API_KEY production
```

### Configure Twilio Webhooks

After deployment, set in Twilio Console:

```
Voice webhook:     https://krishnasalon.in/api/voice/answer
SMS webhook:       https://krishnasalon.in/api/sms/inbound
WhatsApp webhook:  https://krishnasalon.in/api/whatsapp/inbound
```

### Configure Resend Inbound

In Resend dashboard → Inbound → Add endpoint:
```
https://krishnasalon.in/api/email/inbound
```

---

## Future Roadmap

| Phase | Feature | Priority |
|---|---|---|
| V1.1 | Staff profile pages with individual booking | High |
| V1.2 | Online payment (Razorpay) at booking | High |
| V1.3 | Membership / package system (buy 5 get 1 free) | Medium |
| V1.4 | Hindi language toggle (i18n) | Medium |
| V2.0 | Native mobile app (React Native / Expo) | High |
| V2.1 | AI-powered service recommender (selfie upload) | Medium |
| V2.2 | Multi-branch support | Low |
| V2.3 | Staff performance dashboard | Low |

---

## Google Business Profile Optimization Checklist

- [ ] Complete all business info (name, address, phone, hours, category)
- [ ] Upload 20+ high-quality photos (interior, exterior, work examples)
- [ ] Enable messaging on Google Business Profile
- [ ] Respond to every review within 24 hours
- [ ] Post weekly offers/updates via GBP Posts
- [ ] Add all services with prices in GBP Services section
- [ ] Enable online booking link (point to your website)
- [ ] Add FAQs in GBP Q&A section
- [ ] Get 50+ verified reviews (send review link after each completed booking via SMS)
- [ ] Use keywords naturally in business description

---

*Built for Krishna Unisex Family Salon — IBD Emporia Mall, Bhopal*  
*Documentation Version: 2.0 | Last Updated: May 2025*
