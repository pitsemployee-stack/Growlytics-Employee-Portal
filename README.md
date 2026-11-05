# Growlytics Employee Portal

This package has two parts.

## 1. `interactive-demo/` — the complete design and every feature

Open `interactive-demo/index.html` in any browser. No install needed.

It contains the latest design (frosted glass, top navigation, liquid-aurora cursor effect,
light and dark themes, the official Growlytics logo) and every feature:
sign-in and security, attendance, leave, overtime, approvals, payroll and payslips,
Attendance Editor and holidays, timesheets, resignation, notifications, preferences,
Server Logs, Root recovery codes, **announcements** (posted by Founder & CEO, Co-Founder and Root), **shift schedules with Daylight Saving**, **overtime safety checks** (paid = min(approved, actually worked), shift-end reminder, automatic clock-out after 1 hour, clock-out corrections, payroll review gate), and **impersonation** ("View as", Founder & CEO, Co-Founder and Root, read-only).

Data lives in memory and resets on reload. Open **Demo accounts** (link on the sign-in card, or in the
account menu after signing in) to sign in, move the demo clock with **Jump to…**, or reset the data.

Source: `interactive-demo/src/` (CSS + JavaScript modules). Rebuild the single HTML file with
`python3 build.py` (needs `nextjs-app/src/fonts/` for the embedded fonts; edit the font path at the top of
`build.py` if you move folders).

Company rules (shift, grace, leave quota, penalties, ÷26 / ÷8 payroll, notice periods) are in
`src/1-core.js` → `POLICY`.

## 2. `nextjs-app/` — the production app (Phase 1)

Next.js 16 + Tailwind 4 + PostgreSQL (Drizzle). Currently implements Phase 1 only:
sign-in, password policy, first-login reset, lockout, Root recovery codes, roles, dashboards,
employee management, notifications and the audit log — with the official logo.

The rest of the features and the new glass design are in the demo and still need to be built
into this app with the database. See `nextjs-app/README.md` to run it.
