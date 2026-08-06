# Handoff: Publish Blue Route Privacy Policy on GitHub Pages

This document is a **self-contained handoff** for the agent working in the new public repository **`MicahHeneveld/blueroute-legal`**. You do not have access to the private Blue Route app repo — everything you need is in this file. Your job is to create a small public GitHub Pages site that hosts the Blue Route Privacy Policy and verify it is live.

---

## 1. Context

- **Product:** Blue Route — a walking/fitness course app for students (iOS + Android).
- **Why this site exists:** Apple App Store requires every app to have a publicly accessible Privacy Policy URL (no login, no paywall, no JS-only rendering) that stays live as long as the app is on the store. The URL is entered into App Store Connect.
- **Target URL:** `https://micahheneveld.github.io/blueroute-legal/`
- **Requirements the page must satisfy:**
  - Public HTTPS URL.
  - Returns HTTP 200 from anywhere in the world (Apple's reviewer clicks the link server-side).
  - No authentication, cookie wall, age gate, or JS-only content.
  - Must render on a plain HTTP GET.
  - Should be `noindex, nofollow` so search engines skip it (Apple's reviewers still reach it via the direct URL).
- **Brand/app name to use on the page:** "Blue Route".

---

## 2. Repo setup

1. Create a **public** repository named `MicahHeneveld/blueroute-legal`. Public is required for GitHub Pages on the free tier.
2. Do **not** include any Blue Route app source code — only the legal page files.
3. Default branch should be `main`.

Expected file layout:

```
blueroute-legal/
├── index.html      # the privacy policy (single page, plain HTML + minimal CSS)
├── robots.txt      # disallow all crawlers
└── README.md       # short description of the repo
```

---

## 3. Page content (authoritative copy)

Use the following as the **exact body content** of `index.html`. Do not change wording — it must match the App Store Connect privacy questionnaire answers for this app. You may wrap it in simple, clean HTML (`<h1>`, `<h2>`, `<p>`, `<ul>`, `<table>` as appropriate). Include `<meta name="robots" content="noindex, nofollow">` in the `<head>`.

---

### Privacy Policy — Blue Route

**Effective date:** August 5, 2026

This Privacy Policy describes how **Blue Route** ("we", "our", "us") collects, uses, and shares information when you use our mobile application and related services. "Blue Route" is a walking and fitness course app that students use to track walks, progress through a journey, and complete class assignments.

By using Blue Route, you agree to the collection and use of information as described in this policy. If you do not agree, please do not use the app.

#### 1. Information we collect

**1.1 Information you provide, or that your school/instructor provides**

- **Account and identity information:** Your name and email address (provided through Canvas or Google sign-in), plus an internal user ID we assign.
- **Course information:** Your cohort/class membership and instructor-assigned access code.
- **Waiver:** A liability waiver signature (image) when your cohort requires it.
- **Profile content:** Avatar configuration and any profile photo you choose to add.
- **Walk check-ins:** Photos you attach to walks, plus any moods, intentions, or tags you record.

**1.2 Information we collect automatically**

- **Location data:** While you are actively recording a walk, we collect precise GPS location to measure distance, pace, and elevation. Location tracking is only active during a walk session you start. We also collect coarse location for map rendering and route display.
- **Motion/fitness data:** Step and distance estimates derived from device motion sensors (indoor pedometer mode).
- **Walk activity records:** Distance, pace, elevation, elapsed time, and any music/podcast play log you record during a walk.
- **Notification tokens:** If you enable notifications, a push notification token (a device identifier) used to deliver reminders.
- **Canvas assignment data:** If you are enrolled in a Canvas-linked cohort, we sync course modules, assignments, quizzes, and your submission status from your institution's learning management system.

**1.3 Third-party partner data**

The app integrates third-party services, each of which may process limited data as described below and in Section 4.

#### 2. How we use your information

We use the information we collect to:

- Provide and operate the app: track walks, compute distance/pace/credit, and show journey progress.
- Manage your account, authentication, and cohort membership.
- Deliver class assignments, quizzes, and instructor-facing progress.
- Send notifications you have opted into (walk reminders, assignment reminders, module transitions).
- Store and display your profile, avatar, and walk history.
- Respond to support requests and enforce our terms.

We do **not** use your data for advertising, and we do not sell your personal information.

#### 3. Legal bases and your rights

If you are located in the European Economic Area (EEA), the UK, or Switzerland, we rely on the following legal bases: performance of a contract (providing the course service), your consent (e.g., precise location during walks, notifications, photos), and our legitimate interests (service security and improvement). You may withdraw consent at any time without affecting prior processing.

Subject to applicable law, you may have the right to:

- **Access** the personal data we hold about you.
- **Correct** inaccurate or incomplete data.
- **Delete** your data and account.
- **Restrict or object to** processing in certain circumstances.
- **Data portability** where applicable.

To exercise these rights, contact us at the address in Section 9. We will respond within the timeframe required by law (typically 30 days).

#### 4. Third-party services

The following third-party services process data on our behalf or as part of the app:

| Service | Purpose | Data involved |
|---|---|---|
| **Supabase** | Backend database, authentication, file storage, serverless functions | All app data, photos, and push tokens |
| **Spotify** | Optional music playback control and play-log capture during walks | Spotify account display name, product tier, and songs played |
| **Google Sign-In** | Optional account sign-in path | Google identity token during sign-in |
| **Mapbox** | Maps and route display | Map tiles; location data stays on-device (telemetry disabled) |
| **Canvas (your institution)** | OAuth sign-in and course-content sync | Your name, email, and course/assignment data |
| **Expo push service** | Notification delivery | Push token and notification payload |

These services have their own privacy policies, and we encourage you to review them.

#### 5. Data retention

We retain personal data only as long as needed for the purposes described in this policy, or as required by law. Specifically:

- **Walk records and journey progress:** retained for the duration of your account and as needed by your institution to award course credit.
- **Account data (name, email, waiver):** retained while your account is active, and as long as your institution requires records.
- **Photos:** retained while the related walk or profile exists, or until you request deletion.
- **Push tokens:** retained until you disable notifications, the token becomes invalid, or you delete your account.
- **Backups and logs:** retained per Supabase and hosting retention policies.

#### 6. How to delete your data

- **In-app:** You can remove walk photos and edit profile content from within the app.
- **Account deletion:** Contact us using the email in Section 9 to request account deletion. We will delete your personal data and walk records, except where we are required by law or by your institution's record-keeping obligations to retain them.
- **Canvas-linked cohorts:** Deletion of data may require coordination with your institution because course records may belong to the institution.

When you request deletion, we will process it promptly and confirm to you.

#### 7. Children's privacy

Blue Route is a class course app primarily used by college/university students and is not directed to children under the age of 13. We do not knowingly collect personal information from children under 13. If you believe a child under 13 has provided us personal information, contact us and we will delete it.

If your institution uses Blue Route with minors, the institution is responsible for obtaining any required parental consent.

#### 8. Data security

We use industry-standard safeguards, including:

- Authentication via OAuth (Canvas, Google) and Supabase's managed auth.
- Row-level security on our database to scope data access.
- Encrypted data in transit (HTTPS).
- Minimal collection: we do not run analytics or crash-reporting SDKs.

No method of transmission or storage is 100% secure, and we cannot guarantee absolute security.

#### 9. Contact us

Questions, requests, or concerns about this policy or your data:

**Blue Route**
Attn: Privacy
Email: **mheneveld@csumb.edu**

We will respond to privacy inquiries within 30 days. If you are in the EEA/UK and believe your data-protection rights have not been respected, you may also lodge a complaint with your local supervisory authority.

#### 10. Changes to this policy

We may update this Privacy Policy from time to time. When we do, we will revise the "Effective date" above and, where changes are material, notify you in the app. Your continued use of Blue Route after changes take effect constitutes acceptance of the updated policy.

---

## 4. Files to create

### `index.html`

- Standard HTML5 document with `<meta charset="utf-8">` and `<meta name="viewport" content="width=device-width, initial-scale=1">`.
- **Must include:** `<meta name="robots" content="noindex, nofollow">` in the `<head>`.
- Body: the policy content from Section 3, converted to semantic HTML (`<h1>` for the title, `<h2>` for sections, `<p>`, `<ul>`, `<table>` for the third-party table).
- Title tag: `Blue Route — Privacy Policy`.
- Keep styling minimal and inline (a max-width container, system font, basic spacing). No JavaScript required; the page must render fully without JS.

### `robots.txt`

```
User-agent: *
Disallow: /
```

### `README.md`

Short description, e.g.:

> Public legal pages for the Blue Route app, hosted on GitHub Pages. This repo only contains legal/privacy pages — it is intentionally kept separate from the private app codebase.

---

## 5. Publish steps

1. Commit all three files to `main` and push to GitHub.
2. Repo → **Settings** → **Pages**.
3. Under **Build and deployment**, set **Source = Deploy from a branch**, **Branch = main**, folder **/ (root)**.
4. Save. Wait ~1 minute for the first deploy.
5. Confirm the site is live at: `https://micahheneveld.github.io/blueroute-legal/`

---

## 6. Verification checklist (do all)

- [ ] `curl -I https://micahheneveld.github.io/blueroute-legal/` returns **HTTP 200**.
- [ ] The page loads in an **incognito/private window** with no cookies, no login, no challenge.
- [ ] The page renders without JavaScript enabled.
- [ ] The `<head>` contains `<meta name="robots" content="noindex, nofollow">`.
- [ ] The content matches the policy text in Section 3 exactly.
- [ ] `https://micahheneveld.github.io/blueroute-legal/robots.txt` returns the disallow-all content.

---

## 7. Report back (required)

Report the following to the requester:

1. The final live URL.
2. The raw output of `curl -I https://micahheneveld.github.io/blueroute-legal/` (must show `200`).
3. Confirmation each item in Section 6 passed (or the failure + what was fixed).
4. Any wording you had to change from Section 3 and why (there should be none unless requested).

---

## 8. Post-publish steps for the app owner (do NOT do these)

These are handled by the Blue Route app owner, not by you:

- Paste the final URL into App Store Connect → App Information → **Privacy Policy URL**.
- Paste the same URL into App Store Connect → the version's page → **Privacy Policy URL**.
- Keep the URL live for the entire lifetime of the app on the store.
- Keep the content in sync with the app's App Privacy questionnaire (source of truth: the private repo's `docs/PRIVACY_POLICY.md` and `docs/APP_STORE_PRIVACY.md`).
