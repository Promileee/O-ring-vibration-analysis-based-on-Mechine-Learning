# Code Overview

This Python `data_load_and_plot.ipynb` script performs the following tasks:

## 1. Imports Required Libraries

- It imports `numpy` for numerical operations and array handling
- It imports `matplotlib.pyplot` for plotting graphs
- It imports `os` for interacting with the operating system
Although the script import `pandas`, it's not used.

## 2. Set Up File Paths and Data Structure

Defines paths to folders containing data files and creatrs a 5-dimensional numpy array `data` intialized to zeros. The dimensions of this array represent different parameters as following:
- The first dimension corresponds to four compression levels: "15%", "20%", "25%", and "30%".
- The second dimension corresponds to five different databases.
- The third dimension corresponds to four rotation rates: "5000", "10000", "15000", and "20000".

## 3. Load Data into Memory

Interates over all combinations of compression levels, database items, and Rotational rate, reads each `.txt` file into the corresponding position in the `data` array using `numpy.loadtxt`, skipping the first 16rows which are presumably headers or metedata.

## 4. Plot Data

- Sets up plot configurations for size and resolution
- For each combination of compression level, database item, and rotational rate, it creates a figure with 6 subplots.
- Each subplot represents a vibration signal in a dimension, for `x_`, `y_` and `z_` represent the mass response signal while `x`, `y` and `z` represent the excitation response signal.
