# PySpark Learning Lab

This repository contains practice notebooks used to learn and explore PySpark and Apache Spark. It is a learning repository, not a production Data Engineering project, and the notebooks preserve the progression of the original exercises.

## Topics Covered

- Creating a `SparkSession`, using `SparkContext`, and building RDDs
- RDD transformations, actions, partitioning, persistence, broadcast variables, and accumulators
- Creating DataFrames from RDDs and reading text, CSV, JSON, and Parquet data
- DataFrame selection, filtering, sorting, missing-data handling, sampling, and persistence
- Spark SQL aggregations, grouping, pivots, and join types
- Built-in functions for dates, strings, arrays, JSON, conditional expressions, and windows
- User-defined functions, pandas UDFs, query plans, and the Catalyst optimizer
- Practice exercises using the concepts introduced in each stage

## Notebook Progression

The numbered notebooks begin with first steps and local Spark session setup. They then introduce RDD transformations and actions, followed by partitioning, caching, broadcast variables, and accumulators. The later notebooks move into DataFrames and Spark SQL, including file input, column operations, aggregations, joins, built-in functions, UDFs, window functions, and query-plan inspection. Practice notebooks are interleaved with the corresponding topic notebooks and are intended to be opened in numbered order.

## Data

The `data/` directory contains datasets and small artifacts used directly by the exercises. These include text, CSV, JSON, ORC, and Parquet files. Some Parquet inputs are stored through the repository's existing Git LFS configuration. The input files are retained because the notebooks read them directly or because their origin cannot be established safely from the notebook history.

Spark output locations used by the exercises are excluded in `.gitignore` when they are clearly regenerable. Broad patterns such as `part-*` are intentionally not ignored because several small files with those names are required inputs for the later notebooks.

## Environment

The historical notebooks do not pin dependency versions. Running them requires Python, a Java runtime compatible with the chosen Apache Spark release, and PySpark/Apache Spark. Most notebooks also import `findspark`; the pandas UDF section additionally requires pandas and Spark's PyArrow integration. A fresh clone needs Git LFS support to retrieve the existing Parquet objects rather than their pointer files.

Several notebooks retain local Windows environment paths from the original learning setup. Adjust or remove those path assignments to match the machine where the notebooks are opened. No universal current version combination is claimed here because the original environment was not recorded.

## Usage

Install a mutually compatible Python, Java, Spark/PySpark, Jupyter, and (where imported) `findspark` environment. From the repository root, start either interface:

```bash
jupyter notebook
```

or:

```bash
jupyter lab
```

Open the notebooks in their existing numbered order. Run them from the repository root so that relative paths such as `./data/...` resolve correctly. Exercise cells that write Spark output may need their target directory removed before a second run unless the cell uses overwrite mode.

## Scope

This repository is maintained as a learning lab rather than a production-ready data engineering project. Its purpose is to preserve practical Spark exercises and their original learning sequence, not to provide an application architecture, deployment workflow, or production pipeline.
