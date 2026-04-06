# Materials Data Pipeline with PySpark and Spark SQL

A data pipeline project for analyzing materials science data using PySpark and Spark SQL. Built as a portfolio project to learn distributed data processing.

Data comes from the [Materials Project](https://materialsproject.org) - 50000 materials with properties like band gap, density, and formation energy.

---

## What the project does

- Loads 50,000 materials into a PySpark DataFrame
- Filters and aggregates data using both PySpark and Spark SQL
- Identifies stable semiconductor candidates with band gap suitable for solar cells (0.5-3.0 eV)
- Compares PySpark and Pandas performance on the same dataset
- Visualizes key distributions and correlations

---

## Key results

- 18608 non-metals and 13502 thermodynamically stable materials found
- 2967 stable semiconductor candidates identified
- On 50000 rows, Pandas is ~1840x faster than PySpark - expected, since PySpark is designed for much larger datasets on distributed clusters

---

## Technologies

- Python 3.11
- PySpark 3.5.3 + Spark SQL
- Pandas, Matplotlib
- mp-api (Materials Project API)
- Java 17 (required by PySpark)

---

## How to run

1. Install Java 17 from [adoptium.net](https://adoptium.net)

2. Install Python dependencies:
```bash
pip install pyspark==3.5.3 pandas matplotlib mp-api
```

3. Get a free API key at [materialsproject.org](https://materialsproject.org)

4. At the top of the notebook, update:
- `JAVA_HOME` - path to your Java 17 installation
- `API_KEY` - your Materials Project key

5. Run cells in order.

---

## Notes

PySpark requires more setup than Pandas and is slower on small datasets due to JVM overhead. Its advantage shows on very large datasets processed across multiple machines. This project is meant to demonstrate familiarity with the tool rather than showcase its performance benefits.
