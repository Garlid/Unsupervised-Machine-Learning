# Revision notes (October 2026)

> **This revision was made by Claude, an AI assistant made by Anthropic, at Susannah Bear's request.** Susannah's original December 2023 submission is preserved unchanged in the parent folder, errors included.

## What was wrong

The notebook compared five clustering models and selected **K-Medoids (K=5)**, based on the highest silhouette score (0.339). The silhouette scores were computed correctly. However, when the segment labels were attached to the data for profiling, three sections used the **K-Means** model's labels (`kmeans.labels_`) instead of their own:

| Section | Original code | Revised code |
|---|---|---|
| K-Medoids | `kmeans.labels_` | `kmedo.labels_` |
| DBSCAN | `kmeans.labels_` | `dbs.fit_predict(data_pca)` |
| Gaussian Mixture | `kmeans.labels_` | `preds` (the model's own predictions) |

As a result, the segment profiles, personas and advertising plan in the original written summary and presentation describe **K-Means segments**, not K-Medoids segments. The original summary's statement that the Gaussian Mixture model "produced very similar segment results as the K-Medoids model" was comparing K-Means labels with themselves.

## What changed

- The three label assignments above. Every changed line in [`Market_Segmentation_Revised.py`](Market_Segmentation_Revised.py) and the [revised notebook](Market_Segmentation_Revised.ipynb) is marked `# REVISED (fix by Claude, an AI assistant, Oct 2026)`.
- The data is read from `../Market_Segmentation_Data.csv` instead of Google Drive, so the notebook runs from this repo.
- Two markdown **Revision note** cells explain where Susannah's original observations no longer match the corrected output. Her original observations are kept as written.

Nothing else was changed: not the data cleaning, feature engineering, PCA, model settings or written observations.

## How it was verified

The notebook was re-run end to end with the library versions Google Colab used in late 2023: pandas 1.5.3, scikit-learn 1.2.2, scikit-learn-extra 0.3.0, seaborn 0.12.2 and matplotlib 3.7.1. The original results reproduce exactly. K-Means gives the same five segment sizes (518 / 258 / 447 / 584 / 420), and the silhouette scores match: K-Means 0.328, K-Medoids 0.339, Gaussian Mixture 0.102.

## How the results changed

**The personas hold.** Each corrected K-Medoids segment's income, spending, channel use and household profile still fits the persona it was given. The sizes and averages change:

| Persona | Customers (original → revised) | Avg. spend, 2 yrs (original → revised) | Share of all spending (revised) | Avg. offers accepted (revised) |
|---|---:|---:|---:|---:|
| Wine Connoisseurs | 258 → **373** | $1,778 → **$1,650** | **45.6%** | 1.36 |
| Cooking Enthusiasts | 447 → **484** | $1,145 → **$981** | **35.2%** | 0.43 |
| Foodie Adventurers | 420 → **403** | $611 → **$444** | **13.3%** | 0.30 |
| Budget-Conscious Shoppers | 518 → **455** | $127 → **$84** | **2.8%** | 0.18 |
| Convenience Seekers | 584 → **512** | $97 → **$83** | **3.1%** | 0.15 |

**The headline finding gets stronger.** Wine Connoisseurs and Cooking Enthusiasts are 38.5% of customers but **80.7% of spending** (originally 31.7% of customers and 71.9% of spending). Wine Connoisseurs accept about **9× as many campaign offers** as Convenience Seekers.

**Revised advertising cost per campaign.** These figures use the original per-contact channel rates ($0.67 display ads, $0.04 email, $1.00 magazine, $0.50 direct mail) with the revised segment sizes:

| Persona | Channels | Customers | Cost per campaign |
|---|---|---:|---:|
| Wine Connoisseurs | Magazine + direct mail | 373 | $559.50 |
| Cooking Enthusiasts | Email + direct mail | 484 | $261.36 |
| Foodie Adventurers | Display ads + email | 403 | $286.13 |
| Budget-Conscious Shoppers | Display ads + email | 455 | $323.05 |
| Convenience Seekers | Display ads + email | 512 | $363.52 |
| **Total** | | **2,227** | **$1,793.56** |

The channel recommendations themselves are unchanged.

## Known issues not changed

These are in the original notebook too. They were left as they are so the revision stays limited to the labeling bug:

- The hierarchical-clustering dendrogram cell raises a `RecursionError`, as it did in the original Colab run.
- The second DBSCAN search (`eps` of 2–3, `min_samples` of 6–20) raises a `ValueError`, because every customer is labeled as noise at those settings. With `eps = 3, min_samples = 20`, DBSCAN finds no clusters.
- PCA and t-SNE are fit on the unscaled feature table (`data_model`), not the standardized one (`df_scaled`), even though the comment says "scaled data". This affects every model equally, so it doesn't change which model was selected. It does mean spending columns, which have the largest ranges, dominate the clusters.
- In the original written summary's Table 1, the "Total # of Purchases" column mixes average purchase counts and average total spend across rows.
