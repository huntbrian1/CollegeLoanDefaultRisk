# College Loan Default Risk

Authored by Brian Hunt & Logan Laszewski

## Classification of High Default Risk in U.S. Higher Education Programs

This project uses U.S. Department of Education College Scorecard data to classify higher-education programs by elevated federal student-loan default risk. The goal is to identify which program, credential, regional, and institutional characteristics are most associated with higher borrower default rates.

## Business Problem

Student-loan default creates serious consequences for borrowers, institutions, lenders, and policymakers. Schools with persistently high default outcomes can face reputational damage and federal-aid risk, while students may face long-term financial harm.

This project frames default-risk classification as an early-warning decision-support problem: can program-level and institution-level data help flag higher-risk educational pathways before outcomes worsen?

## Data

The analysis uses two College Scorecard datasets:

- Most Recent Data by Field of Study
- Most Recent Institution-Level Data

The datasets were merged using `UNITID` to connect program-level outcomes with institutional characteristics.

## Target Variable

The outcome variable was based on `BBRR3_FED_COMP_DFLT`, which measures the percentage of undergraduate federal student-loan borrowers who defaulted within three years after completion.

Because the original field included ranges, inequalities, and privacy-suppressed values, the project converted the variable into a binary classification target:

- `1`: default rate above 10%
- `0`: default rate at or below 10%

## Methods

The project compares interpretable and nonlinear classification models:

- Logistic Regression
- Lasso Logistic Regression
- Ridge Logistic Regression
- Random Forest Classifier

Logistic Regression was used for interpretability through coefficients and directional effects. Random Forest was used to capture nonlinear relationships and compare feature importance.

## Key Findings

The strongest default-risk signals included:

- Credential level, especially undergraduate certificates and diplomas
- Institution type
- Region
- Major category / field of study
- Select program categories such as Engineering & Technology and Health & Medical fields

Bachelor’s degree programs generally showed lower high-default-risk proportions than undergraduate certificate, diploma, and associate-level programs.

## Evaluation

The models were evaluated using:

- Precision
- Recall
- F1-score
- Feature importance
- Permutation importance

Precision was important because falsely flagging programs as high-risk could create unnecessary institutional concern. Recall was important because missing truly high-risk programs could leave students exposed to financial risk.

## Deployment Concept

A practical deployment would be an interactive dashboard where students, schools, or policymakers could filter by credential type, major category, region, and institution type.

The dashboard would support program-level financial transparency while avoiding individual-borrower assumptions.

## Files

- Main analysis notebook: `CollegeLoanDefaultRisk.ipynb`
- Full written report: `college_scorecard_default_risk_paper.pdf`