# Data Dictionary

All rows in the sample file are fictional and use a synthetic ID prefix (`SYN-`). They do not represent real students.

| Field | Meaning | Example / validation |
|---|---|---|
| `synthetic_id` | Fictional record identifier | `SYN-101`; should be unique |
| `study_year` | Example programme year | Integer from 1 to 4 |
| `course_code` | Example course identifier | `CS101`; should exist in the chosen course catalog |
| `course_title` | Example course title | `Computer Programming` |
| `credits` | Example course credit value | Non-negative number; verify against official syllabus before formal use |
| `score` | Demonstration score | Expected range 0–100; may be blank in a deliberately invalid test row |

## Deliberate test defects

- `SYN-111` has a missing score.
- `SYN-112` has a score of `105`, outside the demonstration range.

These defects are intentional for testing and must not be mistaken for actual academic records. The CSV is reference/sample data; `index.html` currently uses its own embedded JavaScript array rather than loading this file.
