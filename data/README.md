# Data

Raw review data is not included in this portfolio repository.

Expected input CSV format:

```text
product_url,product_name,review_text
```

For the aspect analytics notebook, a preprocessed CSV may include:

```text
product_url,product_name,review_text,Clean
```

Place raw or private datasets under `data/raw/` or `data/private/`; both folders are ignored by Git.
