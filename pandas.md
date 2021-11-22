# How to read in files using the pandas library

The stored data that we work with while coding is typically formated as a csv. Having a way to read in this data is critical to being able to use it! Luckily, the pandas library helps us do just that (along with many other things).

Below is an example of how I have used the pandas library to read in a csv file, as well as use its arguments and functions to make the data more usable.

{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {
    "collapsed": false
   },
   "source": [
    "#### Importing data into a data frame that we can work with."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
   ],
   "source": [
    "import pandas as pd\n",
    "\n",
    "# This line makes pandas show you all of a DataFrame\n",
    "pd.set_option('display.max_columns', None)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "collapsed": false
   },
   "source": [
    "#### Reading in the data file that we want to work with"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "collapsed": false
   },
   "source": [
    "In this case, the data that we were working with was in the folder 's01' and was named 's01.txt'"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
   ],
   "source": [
    "df = pd.read_csv('s01/s01.txt')"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "collapsed": false
   },
   "source": [
    "#### Taking a look at our data using the pandas function head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>id\\tyear\\tmonth\\tday\\thour\\tminute\\tgender\\tage\\thandedness\\twait\\tblock\\ttrial\\ttarget_location\\ttarget\\tflankers\\trt\\tresponse\\terror\\tpre_target_response\\tITI_response\\ttarget_on_error</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "  id\\tyear\\tmonth\\tday\\thour\\tminute\\tgender\\tage\\thandedness\\twait\\tblock\\ttrial\\ttarget_location\\ttarget\\tflankers\\trt\\tresponse\\terror\\tpre_target_response\\tITI_response\\ttarget_on_error\n",
       "0  001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...                                                                                                                                         \n",
       "1  001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...                                                                                                                                         \n",
       "2  001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...                                                                                                                                         \n",
       "3  001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...                                                                                                                                         \n",
       "4  001\\t2015\\t05\\t22\\t11\\t30\\tm\\t25\\tr\\t3.24\\tpra...                                                                                                                                         "
      ]
     },
     "execution_count": 3,
     "metadata": {
     },
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "collapsed": false
   },
   "source": [
    "Initially looking at our data, we can see that this is likely not a format that we want to work with. To make it easier to read and easier to perform operations on, we can specify that we want to separate the data in the data frame into columns based on the key '\\t'."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>id</th>\n",
       "      <th>year</th>\n",
       "      <th>month</th>\n",
       "      <th>day</th>\n",
       "      <th>hour</th>\n",
       "      <th>minute</th>\n",
       "      <th>gender</th>\n",
       "      <th>age</th>\n",
       "      <th>handedness</th>\n",
       "      <th>wait</th>\n",
       "      <th>block</th>\n",
       "      <th>trial</th>\n",
       "      <th>target_location</th>\n",
       "      <th>target</th>\n",
       "      <th>flankers</th>\n",
       "      <th>rt</th>\n",
       "      <th>response</th>\n",
       "      <th>error</th>\n",
       "      <th>pre_target_response</th>\n",
       "      <th>ITI_response</th>\n",
       "      <th>target_on_error</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1</td>\n",
       "      <td>2015</td>\n",
       "      <td>5</td>\n",
       "      <td>22</td>\n",
       "      <td>11</td>\n",
       "      <td>30</td>\n",
       "      <td>m</td>\n",
       "      <td>25</td>\n",
       "      <td>r</td>\n",
       "      <td>3.24</td>\n",
       "      <td>practice</td>\n",
       "      <td>1</td>\n",
       "      <td>left</td>\n",
       "      <td>black</td>\n",
       "      <td>incongruent</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>0.023</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>1</td>\n",
       "      <td>2015</td>\n",
       "      <td>5</td>\n",
       "      <td>22</td>\n",
       "      <td>11</td>\n",
       "      <td>30</td>\n",
       "      <td>m</td>\n",
       "      <td>25</td>\n",
       "      <td>r</td>\n",
       "      <td>3.24</td>\n",
       "      <td>practice</td>\n",
       "      <td>2</td>\n",
       "      <td>right</td>\n",
       "      <td>black</td>\n",
       "      <td>incongruent</td>\n",
       "      <td>0.550</td>\n",
       "      <td>black</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>0.023</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>1</td>\n",
       "      <td>2015</td>\n",
       "      <td>5</td>\n",
       "      <td>22</td>\n",
       "      <td>11</td>\n",
       "      <td>30</td>\n",
       "      <td>m</td>\n",
       "      <td>25</td>\n",
       "      <td>r</td>\n",
       "      <td>3.24</td>\n",
       "      <td>practice</td>\n",
       "      <td>3</td>\n",
       "      <td>up</td>\n",
       "      <td>white</td>\n",
       "      <td>incongruent</td>\n",
       "      <td>0.565</td>\n",
       "      <td>white</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>0.024</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>1</td>\n",
       "      <td>2015</td>\n",
       "      <td>5</td>\n",
       "      <td>22</td>\n",
       "      <td>11</td>\n",
       "      <td>30</td>\n",
       "      <td>m</td>\n",
       "      <td>25</td>\n",
       "      <td>r</td>\n",
       "      <td>3.24</td>\n",
       "      <td>practice</td>\n",
       "      <td>4</td>\n",
       "      <td>up</td>\n",
       "      <td>black</td>\n",
       "      <td>congruent</td>\n",
       "      <td>0.453</td>\n",
       "      <td>black</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>0.024</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>1</td>\n",
       "      <td>2015</td>\n",
       "      <td>5</td>\n",
       "      <td>22</td>\n",
       "      <td>11</td>\n",
       "      <td>30</td>\n",
       "      <td>m</td>\n",
       "      <td>25</td>\n",
       "      <td>r</td>\n",
       "      <td>3.24</td>\n",
       "      <td>practice</td>\n",
       "      <td>5</td>\n",
       "      <td>down</td>\n",
       "      <td>black</td>\n",
       "      <td>congruent</td>\n",
       "      <td>0.442</td>\n",
       "      <td>black</td>\n",
       "      <td>True</td>\n",
       "      <td>False</td>\n",
       "      <td>False</td>\n",
       "      <td>0.023</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   id  year  month  day  hour  minute gender  age handedness  wait     block  \\\n",
       "0   1  2015      5   22    11      30      m   25          r  3.24  practice   \n",
       "1   1  2015      5   22    11      30      m   25          r  3.24  practice   \n",
       "2   1  2015      5   22    11      30      m   25          r  3.24  practice   \n",
       "3   1  2015      5   22    11      30      m   25          r  3.24  practice   \n",
       "4   1  2015      5   22    11      30      m   25          r  3.24  practice   \n",
       "\n",
       "   trial target_location target     flankers     rt response error  \\\n",
       "0      1            left  black  incongruent    NaN      NaN   NaN   \n",
       "1      2           right  black  incongruent  0.550    black  True   \n",
       "2      3              up  white  incongruent  0.565    white  True   \n",
       "3      4              up  black    congruent  0.453    black  True   \n",
       "4      5            down  black    congruent  0.442    black  True   \n",
       "\n",
       "   pre_target_response  ITI_response  target_on_error  \n",
       "0                False         False            0.023  \n",
       "1                False         False            0.023  \n",
       "2                False         False            0.024  \n",
       "3                False         False            0.024  \n",
       "4                False         False            0.023  "
      ]
     },
     "execution_count": 4,
     "metadata": {
     },
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df = pd.read_csv('s01/s01.txt', sep='\\t')\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 0,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
   ],
   "source": [
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (system-wide)",
   "language": "python",
   "metadata": {
    "cocalc": {
     "description": "Python 3 programming language",
     "priority": 100,
     "url": "https://www.python.org/"
    }
   },
   "name": "python3",
   "resource_dir": "/ext/jupyter/kernels/python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.8.10"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 4
}

