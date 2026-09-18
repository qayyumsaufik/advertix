Advertix — HTML Mockups Foundation

This file governs a folder of standalone HTML mockups for Advertix. Read it fully before any task. The mockups are for design review only — they are NOT the real app.

0. Hard rules (read first)
Output standalone HTML files into this folder only. Each is a self-contained page that opens directly in a browser with no build step and no server.
Never modify, import from, or reference the real Advertix application or its repo. Everything you create lives inside this mockups folder and nowhere else.
No frameworks, no bundler, no npm. Plain HTML + CSS, with minimal vanilla JS only for interactions (tabs, modals, theme toggle, nav). Fonts load from Google Fonts.
Every page links the shared stylesheet assets/tokens.css. Do not duplicate design tokens inside individual pages — change them in one place.
1. Product

Advertix is an AI-powered, multi-platform ad-management SaaS. Users connect Meta, Google, TikTok, and LinkedIn ad accounts and manage campaigns, budgets, creatives, audiences, and reporting from one console, with an AI layer that recommends and automates optimizations. Audience: performance marketers and agencies. It must feel precise, trustworthy, and fast — a performance console, not a toy.

2. Folder structure
advertix-mockups/
├─ index.html          # hub: title + a linked card/list for every mockup
├─ assets/
│   └─ tokens.css      # the shared design system (single source of truth)
├─ dashboard.html
├─ campaigns.html
├─ campaign-detail.html
└─ … one file per page/section

Keep index.html updated: whenever you add a page, add a link to it on the hub.

3. Design system — tokens (define once in assets/tokens.css)

Never hardcode a hex in a page; reference a CSS variable.

Color — light

canvas 
#f4f7fb · surface 
#ffffff · surface-2 
#f1f5fa · surface-3 
#e8eef6 · ink 
#0e1a2b · ink-2 
#4b5a70 · ink-3 
#8092a8 · line 
#e4eaf2 · line-strong 
#cfd9e6 · brand 
#1271c4 · brand-hover 
#0f5fa8 · brand-active 
#0c4d88 · brand-soft 
#e7f1fb · positive 
#149a5e · warning 
#b6770c · risk 
#cf3b3b · ai 
#6b47d6 · Meta 
#1877f2 · Google 
#ea4335 · TikTok 
#111111 · LinkedIn 
#0a66c2

Color — dark (via :root[data-theme="dark"])

canvas 
#0a121e · surface 
#101c2c · surface-2 
#0d1826 · surface-3 
#182636 · ink 
#e8eef7 · ink-2 
#a6b6cd · ink-3 
#728299 · line 
#213247 · line-strong 
#2d4058 · brand stays 
#1271c4, brand-hover lightens to 
#3b93e0 · positive 
#38b87a · warning 
#d79a2b · risk 
#ef6f6b · ai 
#8a72e0

Typography

Headings: Space Grotesk (600/700, tracking -0.015em). UI/body: Inter (400–700). Metrics: Inter with font-variant-numeric: tabular-nums. Hard floor 14px — never smaller. Scale: body 15 · small 14 · h3 18 · h2 22 · metric 28 · page title 32.

Shape & depth

Radius: controls 8px · cards 12px · pills 999px. Cards use borders, not shadows; shadow only for overlays. Spacing scale: 4/8/12/16/20/24/32.

Semantics

Green = gain/active · red = loss/rejected · amber = paused/warning/learning. Every metric delta shows an arrow + color. Status badges: Active (green), Paused (amber), Draft (grey), In review (brand), Rejected (red).

4. Component & layout conventions
Shared shell on every app screen: fixed sidebar rail + topbar; below ~860px the rail becomes an off-canvas drawer with a hamburger. Marketing pages use their own layout.
Every interactive element has hover, focus-visible (2px brand ring), disabled states. Keyboard-navigable. Respect prefers-reduced-motion. Tables scroll in their own container; the page never scrolls sideways.
One primary button per view. Buttons are verbs ("Create campaign", "Apply"), never "Submit". Include a working light/dark toggle on every page.
5. Content & data standards ("professional")
No lorem ipsum, no placeholders, no dead buttons. Write real, domain-accurate copy for every label, heading, empty state, and tooltip.
Realistic, internally consistent mock data: real-sounding campaign names, plausible metrics (spend × ROAS ≈ revenue). Money $12,480, rates 2.6%, ratios 4.10x.
Every screen shows its states: empty (an invitation to act), loading (skeletons), and error (says what happened + how to fix, in the product's voice).
Voice: plain, active, sentence case. An action keeps its name through the flow ("Publish" → "Published" toast).
6. Page plan (one HTML file each)
Existing screens

Dashboard · Campaigns · Campaign detail · Creatives · Audiences · Analytics · Insights · AI Planner · Budget Optimizer · Billing · Settings · Onboarding (multi-step) · Connect done · Sign in · Sign up · Marketing: Home · Features · About · Contact · Privacy · Terms · Data deletion

New pages/sections to add

A/B Test Engine · Agency sub-accounts · Automated Rules · Reports & exports · Integrations hub · AI Copilot · Alerts / anomaly feed · Team & permissions · Command palette (⌘K)

7. Working method
One page per task. Small, reviewable output.
Task 1 creates assets/tokens.css + index.html hub + one reference page (Dashboard) that proves the system. Every later page reuses tokens.css and the same shell markup.
Never restyle from scratch per page — copy the shell, swap the content.
After each page, add its link to index.html.