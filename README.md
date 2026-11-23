# A+ Skills College Application Portal

Static student portal hosted with GitHub Pages, using Firebase Authentication and Cloud Firestore.

## Deploy

1. Upload **all files and the `` folder contents** to the **root** of `zracer48/college-application-portal` (do not upload the containing ZIP or parent folder).
2. Commit changes and allow GitHub Pages to deploy.
3. Open https://zracer48.github.io/college-application-portal/ and hard-refresh.
4. Test with a **test student**, including login, logout, each card, PDFs, and mobile navigation.

## Firestore `students/{uid}` fields

All values are strings. The document ID **must equal** the Firebase Authentication UID.

| Field | Purpose |
|---|---|
| `name` | Display name |
| `email` | Login email |
| `googleSheetUrl` | Individual My Application worksheet |
| `testInnovatorsUrl` | Individual Test Innovators URL; **never store passwords** |
| `satActNotesFolderUrl` | Individual SAT/ACT session notes Drive folder |
| `documentsFolderUrl` | Individual My Documents Drive folder |

`intakeFormUrl` is no longer required. Both shared Google Forms are linked directly in `index.html`.

**Privacy:** Share student-specific Drive folders only with authorized students and staff. Firestore rules must permit a signed-in student to read only `students/{theirUID}`. Never commit credentials, student information, or private documents to this public repository. GitHub-hosted PDFs are public resources.

## Pages

- `index.html`: login and dashboard, seven cards
- `sat-act.html`: SAT/ACT account, session notes, **2026–2027 SAT and ACT date/deadline/fee tables**, official testing links, five PDFs
- `resources.html`: 14 topics, expandable questions, printable PDF links
- `styles.css`: shared design, mobile styling, sticky header/navigation
- `logo.png`: A+ Skills branding
- ``: shared public guides

## Resource PDFs awaiting approved content

The 14 topic links use stable filenames under ``. Only `02-common-application.pdf` and `03-uc-application.pdf` are currently included. **The other 12 PDF links intentionally return 404 until approved PDFs are uploaded using the exact filenames below.** Existing on-page dropdown guidance has been retained for the topics that existed previously.

- `01-college-majors.pdf` — College Majors Guide (pending)
- `02-common-application.pdf` — Common Application (included)
- `03-uc-application.pdf` — University of California Application (included)
- `04-stars.pdf` — STARS: Self-Reporting Grades (pending)
- `05-other-academic-records.pdf` — Other Self-Reported Academic Record Systems (pending)
- `06-florida-residency.pdf` — Florida Residency Documentation (Florida Residents Only) (pending)
- `07-recommenders-ferpa.pdf` — Recommenders, School Counselors, and FERPA Agreement (pending)
- `08-honors-programs.pdf` — Honors Programs and Colleges (pending)
- `09-final-reviews.pdf` — Final Application Reviews and Immediately Following Submission (pending)
- `10-post-submission.pdf` — Post-Submission: Application Portals, Emails, and Application Monitoring (pending)
- `11-official-test-scores.pdf` — Sending Official Standardized Test Scores: SAT, ACT, and CLT Exams (pending)
- `12-college-housing.pdf` — College Housing Applications and Priority Registration (included)
- `13-scholarships.pdf` — Scholarships (pending)
- `14-financial-aid.pdf` — Financial Aid: FAFSA and CSS Profile (pending)

## Annual maintenance

Check the SAT and ACT official date/deadline/fee pages before publishing a dated table; the portal currently links to their official live calendars rather than presenting unverified figures. Update guidance when testing or financial aid policies change.

## Testing notes

Student-specific links remain hidden until a valid HTTPS URL is configured. Missing URLs show an informative message. Public forms do not require a Firestore field. The resources page uses the previous Firebase logout integration and collapses every dropdown on page load.

## SAT/ACT calendar maintenance

The `sat-act.html` page includes static U.S. 2026–2027 weekend SAT and ACT tables, with test dates, regular and late registration deadlines, standard test fees, and late-registration totals. These values **do not update automatically**. Verify and update them each academic year against:

- SAT dates: https://satsuite.collegeboard.org/sat/dates-deadlines
- SAT fees: https://satsuite.collegeboard.org/sat/registration/fees-and-refunds/test-fees
- ACT dates: https://www.act.org/content/act/en/products-and-services/the-act/registration/test-dates.html
- ACT fees: https://www.act.org/content/act/en/products-and-services/the-act/registration/fees.html

Note: ACT's current online calendar shows November 9, 2026 as the December ACT regular registration deadline, while its downloadable flyer lists November 6. The website shows November 9 with a caution to verify directly in MyACT.


## Flat GitHub upload package
All files in this ZIP are at the repository root (including PDFs). Upload all extracted files directly to the root of the repository. HTML PDF links are configured for root-level PDFs. Future PDF replacements should use the same filenames in the root directory.


## Resource navigation (latest update)
The resources page has a single-row sticky topic dropdown instead of 14 navigation pills. Common App and UC Application each have seven expandable questions; all start closed. All files in this ZIP belong at the repository root.


## Application Resources PDF inventory (November 2026)

Resources 1–13 are original PDFs supplied by A+ Skills and copied without editing their contents. Resource 14 is the FAFSA and CSS Profile guide. All 14 resource PDFs are included in the repository root (no subfolders), and Resource 12 links to `12-college-housing.pdf`.
