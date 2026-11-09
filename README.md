# UKMEC 2025 pill check

A single-page documentation aid for UK GP clinicians reviewing combined hormonal contraception (CHC: combined oral contraceptive pill, patch, or ring).

It records checklist answers, highlights items to look up in the official CoSRH UKMEC 2025 tables, and builds a plain-text note to paste into EMIS.

Open `index.html` in Edge or Chrome. The page is one file, with CSS and JavaScript inside it. It does not load fonts, scripts, or other sites, so it works offline.

## What it does

- Records method, review type, age, blood pressure, BMI, smoking, vaping, migraine, a yes/no history list, and mood discussion.
- Shows a live **Items to check** list. Every highlight says to check the CoSRH UKMEC 2025 table.
- Writes blank items as **not asked**, so an untouched question is not pasted as “No”.
- Copies the note with the clipboard. If the browser blocks that (common when the file is opened from a folder), the note is selected for Ctrl+C.
- Clears the page with **Reset**.

Blood pressure lines use NICE stage labels only:

- Clinic: stage 1 = 140–159 and/or 90–99; stage 2/3 = 160 or higher and/or 100 or higher.
- Home average: stage 1 = 135–149 and/or 85–94; stage 2/3 = 150 or higher and/or 95 or higher.

The higher of the systolic and diastolic stages is shown. There is no UKMEC number next to the stage.

## What it does not do

- It does not replace clinical judgement or the [CoSRH UKMEC 2025 tables](https://www.cosrh.org/Public/Standards-and-Guidance/uk-medical-eligibility-criteria-for-contraceptive-use-ukmec.aspx).
- It does not calculate or display UKMEC categories, and it does not say whether CHC is suitable.
- Highlight colours are reminders to check the table. They are not categories. Red is used for migraine with aura, personal history of VTE, and NICE blood pressure stage 2/3. Amber is used for other highlighted answers. BMI of 35 or above, and smoking or recent stopping at age 35 or over, use a stronger amber.
- It does not store or send anything. There is no account, no patient name, no NHS number, no date of birth, no `localStorage`, and no network request from the page. Refreshing or closing the page clears the answers. Copy the note first.
- It is not a medical device.

Current vaping shows the wording: “UKMEC 2025: prioritise methods other than CHC”, and still tells the clinician to check the table. Mood shows: “UKMEC 2025: counsel and monitor mood.” Two or more highlights adds: “Multiple risk factors present - UKMEC 2025 advises clinical judgement on cumulative risk.”

Check the wording against the current CoSRH tables before using the page in clinic, and after any UKMEC update.

## Before you share it

In `index.html`, edit the footer:

- `Last reviewed: 3 November 2026`
- `Author: [name], GP trainee`

Replace `[name]` with your name. Update the date when you review the checklist against the tables. The note itself contains the checklist version (`v1.0`) and does not contain the author name.

Known hypertension is asked as Yes / No, so the note can show “not asked” when it has not been answered. An empty checkbox cannot do that.

## Use on an NHS PC

1. Copy `index.html` onto the PC or a shared drive.
2. Open it in Edge or Chrome (double-click, or File → Open).
3. JavaScript needs to be allowed for local files. The page does not need internet access.
4. If local files are blocked by policy, host this same file on the intranet. No build step and no server-side code.

## Host on GitHub Pages

The page is static. GitHub Pages only needs the files in the repository.

1. Create a new repository on GitHub.
2. Add `index.html` and `README.md` to the default branch.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose the default branch and the folder **/ (root)**, then Save.
6. Wait until GitHub shows the site URL, usually `https://<username>.github.io/<repository>/`.

Colleagues opening the Pages site need a network connection to load it the first time. After that, the browser may keep a copy, but the reliable offline copy is the `index.html` file itself. The link to the CoSRH tables needs a network connection and opens in a new tab so the checklist is not discarded.
