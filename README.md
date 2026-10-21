# Prodigy A Level Biology

OCR Biology A H420. 57 revision lessons across all six modules, practical and statistical skills, and three full practice papers (100/135 min, 100/135 min, 70/90 min).

Live site: https://biologyalevel.prodigyai.uk/

## Edit and check

- Edit `course.json` for native lesson content and `papers.json` for original papers.
- Run `node scripts/build.cjs` to update deployable `course-data.js`.
- Run `node --test tests/course.test.cjs` before committing.
- Use `python -m http.server 8766` in this repository for a local preview.
- GitHub Pages serves the repository root from `main`; no package installation is needed.

`index.html` contains the existing corrected Prodigy lesson, marking, progress-report and optional account engine. `learning.js` adds data-driven Biology lessons, interactive models, papers, timers and tier selection. `topic-search.js` provides course-wide search and a last-lesson resume button. `print.html` provides question papers and mark schemes through the browser print / Save as PDF dialog.

Answers save on input. Final numerical checks do not automatically award all method marks. Practice scores have no official grade boundaries. All papers are original, unofficial Prodigy resources, not endorsed by AQA or OCR. Online practical revision does not award the OCR Practical Endorsement.

Progress keys are isolated by course, including on GitHub Pages project URLs. The existing Supabase project/config is reused for accounts. Authenticated teacher/class creation requires the existing database to accept the new site IDs (`gcse-biology`, `alevel-biology`, `gcse-combined`); no database schema was changed by this repository. Guest revision and device-local progress work independently of that backend.

Curriculum sources are listed in `course.json` and on the site. `provenance.json` records the reused framework and content sources.

## Practical labs and saved evidence

`lab-notebook.js` preserves recorded practical evidence and reviews under course-scoped
`learn-<site>-lab-*` keys, which use the existing progress account sync. Apparatus animations
restart after a reload; completed readings, reconstructed graphs, student conclusions and
practical review scores remain. Results can be downloaded as CSV. Teacher student details
show completion, the 2-mark skills check and student-written evaluation. No database schema
or account permissions are changed. Authenticated sync depends on the existing account/backend
configuration; local saving works without signing in.

Biology investigations use simplified teaching models with units, controls, safety guidance,
repeats and uncertainty analysis. They do not replace real practical assessment or certify
the OCR Practical Endorsement. PAG 12 research activities are outside this update.
