---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Name(s)
**Fridtjof Gustaf Alestroem**


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


**YOUR ANSWER HERE**


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
# YOUR SOLUTION HERE
import numpy as np

a = np.ones((6,4))*2
a
```

## Exercise 2

```python
# YOUR SOLUTION HERE
b = np.ones((6,4))*1
np.fill_diagonal(b, 3)
b
```

## Exercise 3


The dot product do not work because the the number of rows in the first matrics have to match the number of columns in the second matrics. 


## Exercise 4

```python
# YOUR SOLUTION HERE

c = np.dot(a, b.transpose())
d = np.dot(a.transpose(), b)

print(c)
print(d)
```

## Exercise 5

```python
def func(a):
  print(a)
```

```python
func("Hello World")
```

## Exercise 6

```python
# YOUR SOLUTION HERE
def array_generator():
    dimention_x = np.random.randint(low=1, high=8)
    dimention_y = np.random.randint(low=1, high=8)
    array = np.random.rand(dimention_x,dimention_y)
    mean_value = np.mean(array)
    sum_value = np.sum(array)
    print(array)
    print(sum_value)
    print(mean_value)
array_generator()
```

## Exercise 7

```python
#YOUR SOLUTION HERE
def count_ones():
    c = 0
    for i in range(b.shape[0]):
        for j in range(b.shape[1]):
            if b[i,j] == 1:
                c += 1
    return c
count_ones()
```

```python
def count_ones2(array):
    ones = np.where(array == 1)
    print(len(array[ones]))

count_ones2(b)





    
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
# YOUR SOLUTION HERE
import pandas as pd

df1 = pd.DataFrame(np.ones((6,4))*2, columns=list('ABCD'))
df1
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE
df2 = pd.DataFrame(np.ones((6,4))*1, columns=list('ABCD'))
np.fill_diagonal(df2.values, 3)
df2
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE
df1*df2
# The dot product do not work because the the number of rows in the first matrics 
# have to match the number of columns in the second matrics. 
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE
c=0
for i in range(df2.shape[0]):
    for j in range(df2.shape[1]):
        if df2.iloc[i,j] == 1:
            c += 1
c
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
## YOUR SOLUTION HERE
names = titanic_df['name']
names

```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
titanic_df.loc['female']
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
titanic_df.reset_index()

```

```python

```
