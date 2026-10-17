# Catching SMS Spam with Naive Bayes

CS 5830 · Project 5 · Abinash Pant

Naive Bayes spam filters on the UCI SMS Spam Collection: multinomial Naive Bayes on the words of each message, Gaussian Naive Bayes on eight numeric statistics of each message, a hybrid that combines the two, plus Bernoulli Naive Bayes and logistic regression for comparison.

**Result.** The final filter (Bernoulli Naive Bayes, chosen by cross-validation) caught 112 of 128 spam messages in a held-out test set of 1,032 messages and flagged none of the 904 legitimate ones: precision 1.00, recall 0.875, F1 0.933 (95% CI 0.896–0.964).

## Files

| Path | Contents |
|---|---|
| `sms_spam_naive_bayes.ipynb` | The full analysis with outputs: cleaning, exploration, method, training, results, conclusions |
| `data/sms_spam_collection/` | The dataset (the notebook downloads it if it is missing) |
| `figures/` | The 8 figures saved by the notebook |
| `results/` | Tables saved by the notebook (CSV and JSON); the slides read their numbers from here |
| `slides/sms_spam_naive_bayes.pptx` | 8-slide presentation with speaker notes |
| `report/` | The written report (Word and PDF) |

## Reproduce

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace sms_spam_naive_bayes.ipynb
```

The notebook runs top to bottom in about 30 seconds with a fixed random seed (5830), and regenerates every number, table and figure used in the report and slides.

## Data source

Almeida, T. A., Gómez Hidalgo, J. M., & Yamakami, A. (2011). Contributions to the study of SMS spam filtering: new collection and results. *Proceedings of the 11th ACM Symposium on Document Engineering*, 259–262. https://doi.org/10.1145/2034691.2034742 · Dataset: https://archive.ics.uci.edu/dataset/228/sms+spam+collection
