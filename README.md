# Student Insights Lab

A browser-based, educational capstone prototype for exploring **synthetic student records**, checking data quality, comparing course credits, and producing a simple report. It is designed to demonstrate a workflow from data intake through validation and descriptive analytics.

> **Privacy and scope:** This project uses fictional records only. It is not affiliated with or connected to an institutional Student Information System (SIS), and it does not access IFHE systems or real student data. Do not enter or commit real student information, SIS credentials, tokens, or other private institutional information.

## Features

- Search, filter, and sort a fictional record table by study year, score, ID, or course credits.
- View a score summary and a simple score-distribution chart.
- Run checks for missing values, invalid scores/years, duplicate IDs, and unknown course codes.
- Add a fictional record with basic validation, or repair deliberately flawed demo records.
- Select courses and calculate the selected credit total.
- Export the currently visible records as CSV and download a text report.
- Run entirely in a modern browser with no build process, server, external JavaScript library, or API key.

## Run locally

1. Download or clone this repository.
2. Open `index.html` in a current desktop or mobile browser.
3. Try the filters, quality checks, course selection, and report export.

All user edits remain in the current page session and are not saved to a database. Refreshing the page resets the app to its built-in example records.

## Publish with GitHub Pages

1. Create a GitHub repository named `student-insights-lab` (or another name you prefer).
2. Upload the contents of this folder, keeping `index.html` at the repository root.
3. Open **Settings → Pages** in the repository.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/(root)`, then click **Save**.
6. Wait for the GitHub Pages deployment to complete; the Pages section will show the published URL.

The app is static, so no build command or environment variables are required.

### Optional Git command-line upload

Replace `YOUR-USERNAME` with your GitHub username after creating an empty repository on GitHub:

```bash
git init
git add .
git commit -m "Add Student Insights Lab prototype"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/student-insights-lab.git
git push -u origin main
```

If the repository already has a README or license created on GitHub, clone that repository first and copy these project files into it to avoid unrelated initial-history conflicts.

## Repository layout

```text
student-insights-lab/
├── index.html
├── README.md
├── LICENSE
├── .gitignore
├── sample_data/
│   └── synthetic_student_records.csv
└── docs/
    ├── DATA_DICTIONARY.md
    ├── PROJECT_SCOPE.md
    └── TEST_PLAN.md
```

## Sample data

`sample_data/synthetic_student_records.csv` mirrors the format of the built-in examples and includes two deliberate data-quality defects: one missing score and one score above 100. These defects are intentional so the quality-check workflow can be demonstrated. The web app currently uses its built-in JavaScript sample records; it does not load this CSV file automatically.

The course titles and credit values in the prototype are for demonstration. Verify them against the official programme syllabus, admission batch, and curriculum version before using them for a formal academic audit.

## Validation checklist

See [`docs/TEST_PLAN.md`](docs/TEST_PLAN.md) for a manual smoke-test checklist. This repository does not claim to have an automated browser test suite.

## Limitations

- No authentication, database, server, SIS integration, or persistent storage.
- Synthetic scores are not evidence of real student performance and must not be used for academic decisions.
- The “repair demo issues” action is illustrative only; it fills a missing score with 75 and clamps invalid scores to 0–100. That is not an acceptable repair policy for real academic records. In a real workflow, ambiguous values should be reviewed by an authorized owner and corrected from an approved source.
- A production deployment would require institutional approval, data minimization, access controls, audit logging, privacy/security review, and approved integrations.

## License

Released under the MIT License. See [`LICENSE`](LICENSE).
