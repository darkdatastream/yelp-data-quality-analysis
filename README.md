# Yelp Business Listings — Data Quality Audit for Reliable Benchmarking

> **1M records. Placeholder ratings isolated. Invalid geographic values detected before analysis.**

---

## The Problem

Large business listing datasets often look analysis-ready while hiding issues that quietly distort comparisons.

This project audits a 1M-record Yelp business dataset to answer a practical question:  
**can this data be trusted for category benchmarking and geographic analysis?**

---

## What Was Wrong in the Data

Two issues had an outsized effect on the reliability of the dataset:

- **Placeholder ratings** — businesses with `Rating = 0` were mixed into the dataset as if they were valid observations
- **Invalid state values** — inconsistent or invalid geographic entries made location-based comparisons unreliable

Without isolating these issues first, any ranking, average, or geographic comparison built on top of the dataset would be misleading.

---

## Key Findings

| Issue | Scale | Business Risk |
|---|---:|---|
| Dataset size | **1,000,000 records** | Large enough to require structured validation before benchmarking |
| Placeholder ratings | **~259,000 records** | Distorted averages and false category comparisons |
| Invalid state values | **~4,000 records** | Unreliable geographic analysis |
| Raw category averages | Materially affected | Misleading performance comparisons |
| Geographic segmentation | Requires validation first | Incorrect regional conclusions |

---

## Cleaning Approach

The audit used simple but high-impact validation logic:

- created an **`is_rated`** flag to separate valid ratings from placeholder values
- created a **`valid_state`** flag to isolate usable geographic records
- built cleaned subsets for trustworthy downstream analysis
- compared raw outputs against validated outputs to measure distortion

---

## Why This Project Matters

This project shows that bad data does not need to be dramatic to be dangerous.

A dataset can look complete, load without errors, and still produce the wrong business conclusions if placeholder values and invalid geographic fields are left untreated.

That is the real value of data quality work:
**making analysis trustworthy before anyone acts on it.**

---

## Tech Stack

- **Python**
- **pandas**
- **matplotlib**
- **Jupyter Notebook**

---

## Repository Contents

- data quality audit notebook
- validation logic for ratings and state fields
- cleaned subsets for reliable comparison
- analysis of rating and geographic distortion

---

## Related Project

My main large-scale data quality project:  
**NYC Yellow Taxi — Data Quality Audit at Scale**  
https://github.com/darkdatastream/nyc-yellow-taxi-cleanup

---

## Work With Me

📧 **data.audit.contact@proton.me**

I help clean, validate, and audit messy datasets before they reach dashboards, reports, or decision-making.

---

## Notes

Dataset not included due to size.

---

## License

MIT
