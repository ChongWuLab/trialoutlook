# TrialOutlook: Trial Outcome Live Benchmark

A prospective benchmark for clinical trial outcome forecasts.

- **TrialDossier** uses a ClinicalTrials.gov identifier to assemble a standardized evidence dossier; **TrialOutlook**
  uses the dossier to forecast, with a GPT-5 reasoning expert, the probability that the trial meets its prespecified
  primary endpoint.
- **69 adjudicated readouts** of the initial prospective cohort of 694 trials, first disclosed after the forecasts were
  recorded on 29 July 2026 and adjudicated by 20 October 2026: 40 successes, 29 failures. Reasoning expert ROC AUC
  0.819 (95% CI 0.708 to 0.914), average precision 0.860; at 0.5 it identified 27 of 29 failures and classified 17 of 40
  successes as failures.
- **Prospective benchmark of 5,809 ongoing trials** of US listed companies, with forecasts recorded before outcome
  disclosure. The trial list is public; anyone can submit forecasts for the open trials (see the Contribute page).
  The 470 trials whose outcome was first disclosed before 5 November 2026 are closed
  (`downloads/trialoutlook_benchmark_closed_470_nct_ids.csv`); the other 5,339 are open
  (`downloads/trialoutlook_benchmark_open_5339_nct_ids.csv`).
- **Prespecified adjudication**: trials are classified by whether the reported results satisfy the prespecified criteria
  for the primary endpoints; trials terminated before completion are failures unless attainment of the primary endpoint
  has been reported; everything else stays unresolved. Every label links its primary source.

The site publishes the 69 adjudicated readouts with their evidence and the reasoning expert's recorded forecasts, and
the benchmark trial list (NCT ID, company, phase, drug, drug targets and disease). Evidence dossiers, model inputs and the forecast values of the benchmark trials are not
published.

## Repository layout

This repository contains only the static website (GitHub Pages, `main` branch root).

```
index.html / results.html / benchmark.html / preliminary.html / contribute.html
predictions.html  redirect to benchmark.html (old link)
css/          styling
js/config.js  deployment config: site name, domain, repo, paper (edit here only)
js/           page logic
data/         compact JSON consumed by the pages
downloads/    the 69 adjudicated readouts (CSV), the benchmark trial list with status, and the NCT IDs of all,
              closed and open benchmark trials (CSV)
submissions/  accepted forecast CSVs, stored by the automatic check of the submission form
.github/      submission issue form and the workflow that checks and stores submissions
```

## Citation

Xu J, Zhang W, Yuan Y, Wu C. Prospective prediction of clinical trial outcomes from public evidence.
medRxiv 2026.11.17.26368242 (2026). https://doi.org/10.64898/2026.11.17.26368242

## Disclaimer

Research resource only. Not medical, clinical or investment advice. Adjudicated labels may be revised as further
evidence emerges; revisions are recorded.
