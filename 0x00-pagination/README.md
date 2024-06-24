# Pagination

## Project Overview
This project involves implementing pagination for a dataset of popular baby names. The tasks are divided into three main parts: simple pagination, hypermedia pagination, and deletion-resilient pagination.

## Learning Objectives
By the end of this project, you should be able to:
- Paginate a dataset with simple `page` and `page_size` parameters.
- Paginate a dataset with hypermedia metadata.
- Implement pagination in a deletion-resilient manner.

## Requirements
- All files will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- All files should end with a new line.
- The first line of all files should be `#!/usr/bin/env python3`.
- A `README.md` file is mandatory at the root of the folder of the project.
- Code should follow the `pycodestyle` style (version 2.5.*).
- The length of files will be tested using `wc`.
- All modules should have documentation.
- All functions should have documentation.
- All functions and coroutines must be type-annotated.

## Setup
Use the `Popular_Baby_Names.csv` data file for your project. The file contains information about popular baby names, including year of birth, gender, ethnicity, child's first name, count, and rank.

## Tasks

### Task 0: Simple Helper Function
Create a function named `index_range` that takes two integer arguments `page` and `page_size`. The function returns a tuple containing a start index and an end index corresponding to the range of indexes to return in a list for those particular pagination parameters.

### Task 1: Simple Pagination
- Copy `index_range` from Task 0.
- Implement a `Server` class with methods:
  - `dataset` to cache the dataset.
  - `get_page` to paginate the dataset using `page` and `page_size` parameters.

### Task 2: Hypermedia Pagination
- Extend the `Server` class from Task 1.
- Implement a `get_hyper` method that returns a dictionary with pagination metadata including `page_size`, `page`, `data`, `next_page`, `prev_page`, and `total_pages`.

### Task 3: Deletion-Resilient Hypermedia Pagination
- Implement a `get_hyper_index` method in the `Server` class that supports deletion-resilient pagination. This method should handle the scenario where certain rows are removed from the dataset between queries.

## Usage

### Task 0: Simple Helper Function
```python
from 0-simple_helper_function import index_range

res = index_range(1, 7)
print(res)  # (0, 7)

res = index_range(3, 15)
print(res)  # (30, 45)
