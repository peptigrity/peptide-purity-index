# Peptigrity Purity Index

Independent HPLC purity data for research peptides, one row per compound, aggregated from third-party laboratory tests indexed by [Peptigrity](https://peptigrity.com).

- **Live data, updated daily:** https://peptigrity.com/purity-index
- **This repository:** dated snapshots, one release per quarter
- **License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Reuse it freely; credit "Peptigrity Purity Index" and link https://peptigrity.com/purity-index.

## Files

| File | Contents |
|---|---|
| `purity-index.csv` | One row per compound, plus one composite row |
| `purity-index.json` | The compound data plus the composite index, failure and underdose rates, quarterly history and the method block |

## Columns in `purity-index.csv`

| Column | Meaning |
|---|---|
| `slug` | Compound identifier. Compound page: `https://peptigrity.com/peptides/{slug}` |
| `name` | Compound name |
| `index` | Recency-weighted mean HPLC purity, in percent. Empty when a compound has too few tests to publish |
| `change_90d` | Change in the index over the last 90 days, in percentage points |
| `test_count` | Number of independent lab tests behind the value |
| `lab_count` | Number of different testing labs behind the value |
| `earliest_test` | Date of the oldest test included (YYYY-MM-DD) |
| `latest_test` | Date of the newest test included (YYYY-MM-DD) |

## How the index is built

- Only results issued by independent third-party laboratories are included.
- Recent tests count more than older ones (a recency-weighted mean).
- A compound gets an index value only once it has a minimum number of tests. Blend vials and quantity-only tests are left out of purity figures.
- Each compound's weight in the composite is capped, so no single compound dominates it.
- Full method, thresholds and weights: https://peptigrity.com/purity-index

## What this data does not tell you

- It describes the samples that were tested, not the whole market.
- HPLC purity is not identity, quantity, sterility or endotoxin. A vial can test 99% pure and still be underfilled or the wrong molecule. See https://peptigrity.com/how-to-test-peptides
- It contains no shop, vendor or batch identifiers. Individual test records are at https://peptigrity.com/lab-tests

## Versions

The files on peptigrity.com change daily. This repository publishes a dated snapshot each quarter as a release, and each release is archived on Zenodo with its own DOI.

## How to cite

Peptigrity. *Peptigrity Purity Index* [Data set]. https://peptigrity.com/purity-index

## Corrections

Found an error? Tell us at https://peptigrity.com/feedback
