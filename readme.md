#Introduction to Data Science Notes

##Lesson 1

To get brushed up on python https://www.udacity.com/course/programming-foundations-with-python--ud036

####Python Pandas
Handle data in a way suited for analysis
Similiar to R So nice pick up

Data frames: string, int, float, bolean. Similiar to excel spreadsheets.

So what we'll want to do is create a dataframe that's based on a chart. 

| Nam  | Age  | Fare  | Survived  |
|---|---|---|---|---|
| Braund  | 22  | 7.25  | False   |
|  Cummings | 38  |  71.83 | True   |
|  Heikkinen |  26 | NaN  |   True |
| Alen | 35 | 8.05 | False |
#####Create a data frame. 

Start by creating a python dictionary called d where each key is the name of the column. 
Then the name of the data frames and the index of where you want them to go.

**NOTE:** In fare, there was a NaN and so it is 'skipped' in the data frame and indexes are given to everything else

```python
d = {'name': Series(['Braund', 'Cummings', 'Heikkinen', 'Allen'], index=['a', 'b', 'c', 'd']),
	'age': Series([22,38,26,35], index=['a','b','c','d']),
	'fare': Series([7.25,71.83,.8.05], index=['a','b','d'])
	'survived': Series([False, True, True, False], index=['a', 'b', 'c', 'd'])}
```
Now that this is created, we can actually pass this on to the data frame function to create the actual dataframe.
```python
df = DataFrame(d)
```
print (df)

returns a 'excel' like info

```python
import pandas as pd

'''
The following code is to help you play with the concept of Series in Pandas.

You can think of Series as an one-dimensional object that is similar to
an array, list, or column in a database. By default, it will assign an
index label to each item in the Series ranging from 0 to N, where N is
the number of items in the Series minus one.

Please feel free to play around with the concept of Series and see what it does

*This playground is inspired by Greg Reda's post on Intro to Pandas Data Structures:
http://www.gregreda.com/2013/10/26/intro-to-pandas-data-structures/
'''
# Change False to True to create a Series object
if False:
    series = pd.Series(['Dave', 'Cheng-Han', 'Udacity', 42, -1789710578])
    print series

'''
You can also manually assign indices to the items in the Series when
creating the series
'''

# Change False to True to see custom index in action
if False:
    series = pd.Series(['Dave', 'Cheng-Han', 359, 9001],
                       index=['Instructor', 'Curriculum Manager',
                              'Course Number', 'Power Level'])
    print series

'''
You can use index to select specific items from the Series
'''
# Change False to True to see Series indexing in action
if False:
    series = pd.Series(['Dave', 'Cheng-Han', 359, 9001],
                       index=['Instructor', 'Curriculum Manager',
                              'Course Number', 'Power Level'])
    print series['Instructor']
    print ""
    print series[['Instructor', 'Curriculum Manager', 'Course Number']]

'''
You can also use boolean operators to select specific items from the Series
'''
# Change False to True to see boolean indexing in action
if False:
    cuteness = pd.Series([1, 2, 3, 4, 5], index=['Cockroach', 'Fish', 'Mini Pig',
                                                 'Puppy', 'Kitten'])
    print cuteness > 3
    print ""
    print cuteness[cuteness > 3]

###More Examples
import numpy as np
import pandas as pd

'''
The following code is to help you play with the concept of Dataframe in Pandas.

You can think of a Dataframe as something with rows and columns. It is
similar to a spreadsheet, a database table, or R's data.frame object.

*This playground is inspired by Greg Reda's post on Intro to Pandas Data Structures:
http://www.gregreda.com/2013/10/26/intro-to-pandas-data-structures/
'''

'''
To create a dataframe, you can pass a dictionary of lists to the Dataframe
constructor:
1) The key of the dictionary will be the column name
2) The associating list will be the values within that column.
'''
# Change False to True to see Dataframes in action
if False:
    data = {'year': [2010, 2011, 2012, 2011, 2012, 2010, 2011, 2012],
            'team': ['Bears', 'Bears', 'Bears', 'Packers', 'Packers', 'Lions',
                     'Lions', 'Lions'],
            'wins': [11, 8, 10, 15, 11, 6, 10, 4],
            'losses': [5, 8, 6, 1, 5, 10, 6, 12]}
    football = pd.DataFrame(data)
    print football

'''
Pandas also has various functions that will help you understand some basic
information about your data frame. Some of these functions are:
1) dtypes: to get the datatype for each column
2) describe: useful for seeing basic statistics of the dataframe's numerical
   columns
3) head: displays the first five rows of the dataset
4) tail: displays the last five rows of the dataset
'''
# Change False to True to see these functions in action
if False:
    data = {'year': [2010, 2011, 2012, 2011, 2012, 2010, 2011, 2012],
            'team': ['Bears', 'Bears', 'Bears', 'Packers', 'Packers', 'Lions',
                     'Lions', 'Lions'],
            'wins': [11, 8, 10, 15, 11, 6, 10, 4],
            'losses': [5, 8, 6, 1, 5, 10, 6, 12]}
    football = pd.DataFrame(data)
    print football.dtypes
    print ""
    print football.describe()
    print ""
    print football.head()
    print ""
    print football.tail()
```

####Python Numpy
Multidimentional arrays + Matrices
Mathematical functions
Like Statistical analysis
numbers = [1,2,3,4,5]

Mean
numpy.mean(numbers)
return 3.0

Median
numpy.median(numbers)
return 3.0

Standard Deviation
numpy.std(numbers)
returns 1.4142...

#####Numpy Examples
import numpy as np

'''
The following code is to help you play with Numpy, which is a library
that provides functions that are especially useful when you have to
work with large arrays and matrices of numeric data, like doing
matrix matrix multiplications. Also, Numpy is battle tested and
optimized so that it runs fast, much faster than if you were working
with Python lists directly.
'''

'''
The array object class is the foundation of Numpy, and Numpy arrays are like
lists in Python, except that every thing inside an array must be of the
same type, like int or float.
'''
# Change False to True to see Numpy arrays in action
if False:
    array = np.array([1, 4, 5, 8], float)
    print array
    print ""
    array = np.array([[1, 2, 3], [4, 5, 6]], float)  # a 2D array/Matrix
    print array

'''
You can index, slice, and manipulate a Numpy array much like you would with a
a Python list.
'''
# Change False to True to see array indexing and slicing in action
if False:
    array = np.array([1, 4, 5, 8], float)
    print array
    print ""
    print array[1]
    print ""
    print array[:2]
    print ""
    array[1] = 5.0
    print array[1]

# Change False to True to see Matrix indexing and slicing in action
if False:
    two_D_array = np.array([[1, 2, 3], [4, 5, 6]], float)
    print two_D_array
    print ""
    print two_D_array[1][1]
    print ""
    print two_D_array[1, :]
    print ""
    print two_D_array[:, 2]

'''
Here are some arithmetic operations that you can do with Numpy arrays
'''
# Change False to True to see Array arithmetics in action
if False:
    array_1 = np.array([1, 2, 3], float)
    array_2 = np.array([5, 2, 6], float)
    print array_1 + array_2
    print ""
    print array_1 - array_2
    print ""
    print array_1 * array_2

# Change False to True to see Matrix arithmetics in action
if False:
    array_1 = np.array([[1, 2], [3, 4]], float)
    array_2 = np.array([[5, 6], [7, 8]], float)
    print array_1 + array_2
    print ""
    print array_1 - array_2
    print ""
    print array_1 * array_2

'''
In addition to the standard arthimetic operations, Numpy also has a range of
other mathematical operations that you can apply to Numpy arrays, such as
mean and dot product.

Both of these functions will be useful in later programming quizzes.
'''
if False:
    array_1 = np.array([1, 2, 3], float)
    array_2 = np.array([[6], [7], [8]], float)
    print np.mean(array_1)
    print np.mean(array_2)
    print ""
    print np.dot(array_1, array_2)


###Sochi Medals

from pandas import DataFrame, Series


def create_dataframe():
    '''
    Create a pandas dataframe called 'olympic_medal_counts_df' containing
    the data from the  table of 2014 Sochi winter olympics medal counts.

    The columns for this dataframe should be called
    'country_name', 'gold', 'silver', and 'bronze'.

    There is no need to  specify row indexes for this dataframe
    (in this case, the rows will  automatically be assigned numbered indexes).
    '''

    countries = ['Russian Fed.', 'Norway', 'Canada', 'United States',
                 'Netherlands', 'Germany', 'Switzerland', 'Belarus',
                 'Austria', 'France', 'Poland', 'China', 'Korea',
                 'Sweden', 'Czech Republic', 'Slovenia', 'Japan',
                 'Finland', 'Great Britain', 'Ukraine', 'Slovakia',
                 'Italy', 'Latvia', 'Australia', 'Croatia', 'Kazakhstan']

    gold = [13, 11, 10, 9, 8, 8, 6, 5, 4, 4, 4, 3, 3, 2, 2, 2, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0]
    silver = [11, 5, 10, 7, 7, 6, 3, 0, 8, 4, 1, 4, 3, 7, 4, 2, 4, 3, 1, 0, 0, 2, 2, 2, 1, 0]
    bronze = [9, 10, 5, 12, 9, 5, 2, 1, 5, 7, 1, 2, 2, 6, 2, 4, 3, 1, 2, 1, 0, 6, 2, 1, 0, 1]

    # your code here
    olympic_medal_counts = { 'country_name': Series(countries),
             'gold': Series(gold),
             'silver': Series(silver),
             'bronze': Series(bronze)}


    olympic_medal_counts_df = DataFrame(d)
    return olympic_medal_counts_df

    ##How to access the Data

    df = DataFrame(d)

    df['name']

    returns name column.

    df.loc['a']

    Only want rows where age is greater than 30

    df[df['age'] >= 30]
    only survivor info

    df['survived?'][df['age'] >= 30]
RETURNED
    b true
    d false

import pandas as pd

'''
You can think of a DataFrame as a group of Series that share an index.
This makes it easy to select specific columns that you want from the
DataFrame.

Also a couple pointers:
1) Selecting a single column from the DataFrame will return a Series
2) Selecting multiple columns from the DataFrame will return a DataFrame

*This playground is inspired by Greg Reda's post on Intro to Pandas Data Structures:
http://www.gregreda.com/2013/10/26/intro-to-pandas-data-structures/
'''
# Change False to True to see Series indexing in action
if False:
    data = {'year': [2010, 2011, 2012, 2011, 2012, 2010, 2011, 2012],
            'team': ['Bears', 'Bears', 'Bears', 'Packers', 'Packers', 'Lions',
                     'Lions', 'Lions'],
            'wins': [11, 8, 10, 15, 11, 6, 10, 4],
            'losses': [5, 8, 6, 1, 5, 10, 6, 12]}
    football = pd.DataFrame(data)
    print football['year']
    print ''
    print football.year  # shorthand for football['year']
    print ''
    print football[['year', 'wins', 'losses']]

'''
Row selection can be done through multiple ways.

Some of the basic and common methods are:
   1) Slicing
   2) An individual index (through the functions iloc or loc)
   3) Boolean indexing

You can also combine multiple selection requirements through boolean
operators like & (and) or | (or)
'''
# Change False to True to see boolean indexing in action
if False:
    data = {'year': [2010, 2011, 2012, 2011, 2012, 2010, 2011, 2012],
            'team': ['Bears', 'Bears', 'Bears', 'Packers', 'Packers', 'Lions',
                     'Lions', 'Lions'],
            'wins': [11, 8, 10, 15, 11, 6, 10, 4],
            'losses': [5, 8, 6, 1, 5, 10, 6, 12]}
    football = pd.DataFrame(data)
    print football.iloc[[0]]
    print ""
    print football.loc[[0]]
    print ""
    print football[3:5]
    print ""
    print football[football.wins > 10]
    print ""
    print football[(football.wins > 10) & (football.team == "Packers")]

###

df.apply(numpy.mean) aplies this to every data point

As a refresher on lambda, lambda functions are small inline functions that are defined on-the-fly in Python. lambda x: x>= 1 will take an input x and return x>=1, or a boolean that equals True or False.

In this example, map() and applymap() create a new Series or DataFrame by applying the lambda function to each element. Note that map() can only be used on a Series to return a new Series and applymap() can only be used on a DataFrame to return a new DataFrame.

For further reference, please refer to the official documentation on lambda:

#### Average Bronze Medals

from pandas import DataFrame, Series

```python

from pandas import DataFrame, Series
import numpy


def avg_medal_count():
    '''
    Compute the average number of bronze medals earned by countries who
    earned at least one gold medal.

    Save this to a variable named avg_bronze_at_least_one_gold.

    HINT-1:
    You can retrieve all of the values of a Pandas column from a
    data frame, "df", as follows:
    df['column_name']

    HINT-2:
    The numpy.mean function can accept as an argument a single
    Pandas column.

    For example, numpy.mean(df["col_name"]) would return the
    mean of the values located in "col_name" of a dataframe df.
    '''


    countries = ['Russian Fed.', 'Norway', 'Canada', 'United States',
                 'Netherlands', 'Germany', 'Switzerland', 'Belarus',
                 'Austria', 'France', 'Poland', 'China', 'Korea',
                 'Sweden', 'Czech Republic', 'Slovenia', 'Japan',
                 'Finland', 'Great Britain', 'Ukraine', 'Slovakia',
                 'Italy', 'Latvia', 'Australia', 'Croatia', 'Kazakhstan']

    gold = [13, 11, 10, 9, 8, 8, 6, 5, 4, 4, 4, 3, 3, 2, 2, 2, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0]
    silver = [11, 5, 10, 7, 7, 6, 3, 0, 8, 4, 1, 4, 3, 7, 4, 2, 4, 3, 1, 0, 0, 2, 2, 2, 1, 0]
    bronze = [9, 10, 5, 12, 9, 5, 2, 1, 5, 7, 1, 2, 2, 6, 2, 4, 3, 1, 2, 1, 0, 6, 2, 1, 0, 1]

    # YOUR CODE HERE

    d = {'name': Series(countries),'gold': Series(gold),'bronze': Series(bronze)}

    df = DataFrame(d)
    one_gold = df['bronze'][df['gold'] >= 1]

    avg_bronze_at_least_one_gold = numpy.mean(one_gold)
    return avg_bronze_at_least_one_gold

    ```

    ### Apply

    ```python

    import numpy
from pandas import DataFrame, Series


def avg_medal_count():
    '''
    Using the dataframe's apply method, create a new Series called
    avg_medal_count that indicates the average number of gold, silver,
    and bronze medals earned amongst countries who earned at
    least one medal of any kind at the 2014 Sochi olympics.  Note that
    the countries list already only includes countries that have earned
    at least one medal. No additional filtering is necessary.

    You do not need to call the function in your code when running it in the
    browser - the grader will do that automatically when you submit or test it.
    '''

    countries = ['Russian Fed.', 'Norway', 'Canada', 'United States',
                 'Netherlands', 'Germany', 'Switzerland', 'Belarus',
                 'Austria', 'France', 'Poland', 'China', 'Korea',
                 'Sweden', 'Czech Republic', 'Slovenia', 'Japan',
                 'Finland', 'Great Britain', 'Ukraine', 'Slovakia',
                 'Italy', 'Latvia', 'Australia', 'Croatia', 'Kazakhstan']

    gold = [13, 11, 10, 9, 8, 8, 6, 5, 4, 4, 4, 3, 3, 2, 2, 2, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0]
    silver = [11, 5, 10, 7, 7, 6, 3, 0, 8, 4, 1, 4, 3, 7, 4, 2, 4, 3, 1, 0, 0, 2, 2, 2, 1, 0]
    bronze = [9, 10, 5, 12, 9, 5, 2, 1, 5, 7, 1, 2, 2, 6, 2, 4, 3, 1, 2, 1, 0, 6, 2, 1, 0, 1]

    olympic_medal_counts = {'country_name':countries,
                            'gold': Series(gold),
                            'silver': Series(silver),
                            'bronze': Series(bronze)}
    df = DataFrame(olympic_medal_counts)

    # YOUR CODE HERE

    avg_medal_count = df[['gold','silver','bronze']].apply(numpy.mean)

    return avg_medal_count

    ```
### Medal points system

```python
import numpy
from pandas import DataFrame, Series


def numpy_dot():
    '''
    Imagine a point system in which each country is awarded 4 points for each
    gold medal,  2 points for each silver medal, and one point for each
    bronze medal.

    Using the numpy.dot function, create a new dataframe called
    'olympic_points_df' that includes:
        a) a column called 'country_name' with the country name
        b) a column called 'points' with the total number of points the country
           earned at the Sochi olympics.

    You do not need to call the function in your code when running it in the
    browser - the grader will do that automatically when you submit or test it.
    '''

    countries = ['Russian Fed.', 'Norway', 'Canada', 'United States',
                 'Netherlands', 'Germany', 'Switzerland', 'Belarus',
                 'Austria', 'France', 'Poland', 'China', 'Korea',
                 'Sweden', 'Czech Republic', 'Slovenia', 'Japan',
                 'Finland', 'Great Britain', 'Ukraine', 'Slovakia',
                 'Italy', 'Latvia', 'Australia', 'Croatia', 'Kazakhstan']

    gold = [13, 11, 10, 9, 8, 8, 6, 5, 4, 4, 4, 3, 3, 2, 2, 2, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0]
    silver = [11, 5, 10, 7, 7, 6, 3, 0, 8, 4, 1, 4, 3, 7, 4, 2, 4, 3, 1, 0, 0, 2, 2, 2, 1, 0]
    bronze = [9, 10, 5, 12, 9, 5, 2, 1, 5, 7, 1, 2, 2, 6, 2, 4, 3, 1, 2, 1, 0, 6, 2, 1, 0, 1]

    # YOUR CODE HERE
  	olympic_medal_counts = {'country_name': Series(countries), 'gold': Series(gold), 'silver': Series(silver), 'bronze': Series(bronze)}

  	olympic_medal_counts_df = DataFrame(olympic_medal_counts)

  	medal_counts = olympic_medal_counts_df[['gold', 'silver',bronze']]
    points = numpy.dot(medal_counts, [4,2,1])
    olympic_points = {'country_name': Series(countries), 'points': Series(points)}
    olympic_points_df = DataFrame(olympic_points)

    return olympic_points_df
```

##Titanic Survivors

```python

import numpy
import pandas
import statsmodels.api as sm

def simple_heuristic(file_path):
    '''
    In this exercise, we will perform some rudimentary practices similar to those of
    an actual data scientist.

    Part of a data scientist's job is to use her or his intuition and insight to
    write algorithms and heuristics. A data scientist also creates mathematical models
    to make predictions based on some attributes from the data that they are examining.

    We would like for you to take your knowledge and intuition about the Titanic
    and its passengers' attributes to predict whether or not the passengers survived
    or perished. You can read more about the Titanic and specifics about this dataset at:
    http://en.wikipedia.org/wiki/RMS_Titanic
    http://www.kaggle.com/c/titanic-gettingStarted

    In this exercise and the following ones, you are given a list of Titantic passengers
    and their associated information. More information about the data can be seen at the
    link below:
    http://www.kaggle.com/c/titanic-gettingStarted/data.

    For this exercise, you need to write a simple heuristic that will use
    the passengers' gender to predict if that person survived the Titanic disaster.

    You prediction should be 78% accurate or higher.

    Here's a simple heuristic to start off:
       1) If the passenger is female, your heuristic should assume that the
       passenger survived.
       2) If the passenger is male, you heuristic should
       assume that the passenger did not survive.

    You can access the gender of a passenger via passenger['Sex'].
    If the passenger is male, passenger['Sex'] will return a string "male".
    If the passenger is female, passenger['Sex'] will return a string "female".

    Write your prediction back into the "predictions" dictionary. The
    key of the dictionary should be the passenger's id (which can be accessed
    via passenger["PassengerId"]) and the associated value should be 1 if the
    passenger survied or 0 otherwise.

    For example, if a passenger is predicted to have survived:
    passenger_id = passenger['PassengerId']
    predictions[passenger_id] = 1

    And if a passenger is predicted to have perished in the disaster:
    passenger_id = passenger['PassengerId']
    predictions[passenger_id] = 0

    You can also look at the Titantic data that you will be working with
    at the link below:
    https://www.dropbox.com/s/r5f9aos8p9ri9sa/titanic_data.csv
    '''

    predictions = {}
    df = pandas.read_csv(file_path)
    for passenger_index, passenger in df.iterrows():
        passenger_id = passenger['PassengerId']

        # Your code here:
        # For example, let's assume that if the passenger
        # is a male, then the passenger survived.
        #     if passenger['Sex'] == 'male':
        #         predictions[passenger_id] = 1

        if passenger['Sex'] == 'female':
            predictions[passenger_id] = 1
        if passenger['Sex'] == 'male':
            predictions[passenger_id] = 0
    return predictions

```

##Importing Data

```python
import pandas

baseball_data= pandas.read_csv('Master.csv')

print baseball_data['nameFirst']

baseball_data.to_csv('baseball_data_with_weight_height.csv')
```


```python

import pandas

def add_full_name(path_to_csv, path_to_new_csv):
    #Assume you will be reading in a csv file with the same columns that the
    #Lahman baseball data set has -- most importantly, there are columns
    #called 'nameFirst' and 'nameLast'.
    #1) Write a function that reads a csv
    #located at "path_to_csv" into a pandas dataframe and adds a new column
    #called 'nameFull' with a player's full name.
    #
    #For example:
    #   for Hank Aaron, nameFull would be 'Hank Aaron',
    #
    #2) Write the data in the pandas dataFrame to a new csv file located at
    #path_to_new_csv

    #WRITE YOUR CODE HERE
    baseball_data = pandas.read_csv(path_to_csv)
    baseball_data['nameFull'] = baseball_data['nameFirst'] + ' ' + baseball_data['nameLast']
    baseball_data.to_csv(path_to_new_csv)


if __name__ == "__main__":
    # For local use only
    # If you are running this on your own machine add the path to the
    # Lahman baseball csv and a path for the new csv.
    # The dataset can be downloaded from this website: http://www.seanlahman.com/baseball-archive/statistics
    # We are using the file Master.csv
    path_to_csv = ""
    path_to_new_csv = ""
    add_full_name(path_to_csv, path_to_new_csv)

```

###SQL queries

```python

import pandas
import pandasql

def select_first_50(filename):
    # Read in our aadhaar_data csv to a pandas dataframe.  Afterwards, we rename the columns
    # by replacing spaces with underscores and setting all characters to lowercase, so the
    # column names more closely resemble columns names one might find in a table.
    aadhaar_data = pandas.read_csv(filename)
    aadhaar_data.rename(columns = lambda x: x.replace(' ', '_').lower(), inplace=True)

    # Select out the first 50 values for "registrar" and "enrolment_agency"
    # in the aadhaar_data table using SQL syntax.
    #
    # Note that "enrolment_agency" is spelled with one l. Also, the order
    # of the select does matter. Make sure you select registrar then enrolment agency
    # in your query.
    #
    # You can download a copy of the aadhaar data that we are passing
    # into this exercise below:
    # https://www.dropbox.com/s/vn8t4uulbsfmalo/aadhaar_data.csv
    q = """
    SELECT registrar, enrolment_agency
    FROM aadhaar_data
    limit 50
    """

    #Execute your SQL command against the pandas frame
    aadhaar_solution = pandasql.sqldf(q.lower(), locals())
    return aadhaar_solution

    ```
Select * FROM aadhaar_data WHERE state = 'x'

### API and JSON

JSON Data can be likea python dictionary.

data = requests.get(url).text
data = json.loads(data)
print type(data)
print data
data['artist']




