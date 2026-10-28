# econ3916-lab06-sampling
ECON 3916 Lab 06 - The Train-Test Split — Sampling for Machine Learning
# Sampling for Machine Learning — Train-Test Splits

## Objective

I studied how the way a sample is drawn affects model evaluation and estimation accuracy, using train-test splits on the Titanic data and a simulation of the 1936 Literary Digest polling failure.

## Methodology

- Explored the Titanic dataset (891 passengers) with survival as the target.
- Compared a naive train-test split with a stratified one, and checked that stratifying keeps the survival rate the same in both halves.
- Found data leakage in a StandardScaler step and a SimpleImputer step, and fixed both.
- Wrote a function, `split_by_share()`, that splits a table by a test share and a seed, and checked it against the lab's own split.
- Simulated the 1936 Literary Digest polling failure on 10 million voters.
- Computed Meng's data defect correlation for the biased sample.
- Compared a biased sample of 4,382,503 responses with a random sample of 50,000.
- Ran 100 replications of the biased-versus-random comparison.

## Key Findings

- **Stratified split:** Stratifying kept the survival rate the same in the training and test halves.
- **Data leakage:** The StandardScaler and SimpleImputer steps both leaked information, and I fixed both.
- **Custom split function:** `split_by_share()` matched the lab's own split.
- **Sample design versus sample size:** The biased sample of 4,382,503 responses was less accurate than the random sample of 50,000. A data defect correlation of 0.1475 produced an error of 8.3 percentage points.
- **Takeaway:** Sample design matters more than sample size.
