# Manual Test Plan

Use the built-in demo records only. No real SIS credentials or personal student data are needed. This is a manual smoke-test plan, not an automated test suite.

| ID | Test | Action | Expected result |
|---|---|---|---|
| T01 | Initial load | Open `index.html` | Dashboard and sample rows appear without needing a server |
| T02 | Search | Search for `SYN-104` | Matching fictional record is shown |
| T03 | Year filter | Select Year 3 | Only Year 3 records are shown in the table |
| T04 | Score sort | Select high-to-low score | Valid high scores appear before lower scores; missing score remains handled without a crash |
| T05 | Missing score | Run data quality checks | Missing-score defect on `SYN-111` is identified |
| T06 | Out-of-range score | Run data quality checks | Score 105 on `SYN-112` is identified as invalid |
| T07 | Duplicate ID protection | Try adding an existing ID such as `SYN-101` | App rejects the duplicate ID with a visible message |
| T08 | New valid record | Add `SYN-113`, Year 2, choose a course, score 80 | New fictional row is added for the current session and summaries update |
| T09 | Invalid new score | Enter a score outside 0–100 | Browser validation or app validation prevents the invalid submission |
| T10 | Export CSV | Filter records and choose Export visible CSV | A CSV downloads containing the currently visible rows and a data-status field |
| T11 | Course totals | Select/clear course checkboxes | Selected-course count and credits update |
| T12 | Report export | Choose Download report (.txt) | A report downloads and states the data is synthetic |
| T13 | Demo repair | Choose Repair demo issues | Example issues are changed; message explicitly says the repair is illustrative only |
| T14 | Refresh reset | Add a record, then refresh the page | App returns to its embedded starting dataset because there is no persistence |

## Evidence to capture for a submission

Capture screenshots of the initial dashboard, the quality-check results before repair, a filtered result, the course-credit calculator, and a generated report. Screenshots must show only the built-in synthetic data. Label them as prototype screenshots, not observations of the real SIS or evidence of an official college process.
