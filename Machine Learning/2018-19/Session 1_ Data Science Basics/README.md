# Session 1

Data Science Basics and Introduction to Kaggle

## Resources

The notebook used for the session can be found [here](./Session%201.ipynb).

## Brief Summary

- **EDA**: In statistics,  exploratory data analysis (EDA)
  is an approach to analyzing data sets to
  summarize their main characteristics, often with
  visual methods.
- **Ways of analyzing data**:  Histograms,Scatter etc.
- **Feature engineering** is the process of using
  domain knowledge of the data to create features
  that make machine learning algorithms work.
- **Data correlation** is the way in which one set of
  data may correspond to another set.
- **Outliers**: Any value which out of range of 5th and 95th
  percentile can be considered as outlier . Data
  points, three or more standard deviation away
  from mean are considered outlier
- **Libraries Used**: pandas, numpy, matplotlib
- **Functions Used** :
  - `pd.read_csv()` : an important pandas function to read
    csv files and do operations on it.
  - `df.head()` : method is used to return top n (5
    by default) rows of a dataframe or series.
  - `df.info()`  function is used to get a concise
    summary of the dataframe. It comes really handy
    when doing exploratory analysis of the data.
  - `df.isnull()` and `df.notnull()` methods are used to
    check and manage NULL values in a data
    frame. Returns a DataFrame object of Boolean values which are
    True for NaN values. Further, df.isnull().sum() is used to calculate number of NaN
    values along the axis.
  - `Series. value_counts()` function returns object
    containing counts of unique values
  - `df.copy()`  method returns a "deep" copy of the
    set in python. If we use “=” to copy a set to
    another set, when we modify in the copied set, the
    changes are also reflected in the original set. So
    we have to create a deep copy of the set such
    that when we modify something in the copied set,
    changes are not reflected back in the original set.
  - `df.isna()` function is used to
    detect missing values. It return a boolean
    same-sized object indicating if the values are NA.
    NA values, such as None or numpy.NaN, gets
    mapped to True values. Everything else gets
    mapped to False values.
  - `df.drop()` is used to remove rows or columns by specifying
    label names and corresponding axis, or by
    specifying directly index or column names
  - `corr()`  Compute pairwise correlation of columns,
    excluding NA/null value
  - `df.groupby()` function is used to
    split the data into groups based on some criteria.
    pandas objects can be split on any of their axes. The abstract definition of grouping is to provide a
    mapping of labels to group names.
  - `Series.map()` function returns a list of the results after
    applying the given function to each item of a
    given iterable (list, tuple etc.)
  - `df.fillna()`  manages and let the user replace NaN
    values with some value of their own.
  - `groups.groups` where groups is a `df.groupby` object
    which is used to check the indices corresponding
    to a particular group label

## Credits

*Conducted by:* [Suyog Jadhav](https://github.com/IAmSuyogJadhav) and [Udbhav Bamba](https://github.com/ubamba98) on 24-01-2019

*Report compiled by*: [Pritam Roy](https://github.com/chefpr7)