# Richness Creator CRM — Starter Build

## Included
- Responsive web CRM dashboard
- Lead create/edit/delete/search/filter
- Lead status and priority
- Follow-up queue
- Sales pipeline
- Team role planning screen
- Basic reports
- CSV and JSON import/export
- Installable Progressive Web App (PWA) shell for Android
- Offline app-shell caching

## Run locally
Open `index.html` in a modern browser. For PWA install/offline support, serve the folder over HTTPS or localhost:
- Python: `python -m http.server 8000`
- Then visit `http://localhost:8000`

## Important limitations
This is a working front-end starter. Data is stored in the current browser's localStorage. It is NOT yet a multi-user cloud CRM:
- No shared database or user login yet
- No team permissions enforced yet
- No automatic AI lead scraping or email/WhatsApp sending
- No native Android APK; install the PWA from Chrome after HTTPS deployment

For 10–50 users, connect a hosted backend (for example Supabase) with authentication, database tables, row-level security, backups and audit logs before using real customer data. A free hosting tier may be suitable for testing, but availability, quotas and pricing can change. Do not store sensitive customer data in this local prototype.

## Suggested production schema
`profiles(id, full_name, role, created_at)`
`companies(id, name, industry, country, website, email, phone, address, district, source_url, verification_status, created_by, owner_id, created_at, updated_at)`
`contacts(id, company_id, full_name, title, email, phone, consent_status)`
`deals(id, company_id, stage, value, currency, probability, owner_id, next_followup_at)`
`activities(id, company_id, type, summary, due_at, completed_at, created_by)`
`audit_logs(id, actor_id, action, record_type, record_id, created_at)`

## Security checklist before launch
- Enable email/password or SSO authentication
- Enforce role-based access with database row-level security
- Validate and sanitize imports
- Keep API keys server-side; never embed service-role keys in frontend code
- Add backups, audit logs, rate limits and opt-out controls
- Review Sri Lanka PDPA and applicable marketing/privacy rules
