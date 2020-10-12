# readme

## How to run
To run this script, two directories are needed to be provided with:
1. The directory of a folder containing only readable scripts to parsed
2. The directory containing "labels.csv"
and the output will be an average score and ten scores of 10-fold cross validation for each of the three classifiers

## How to approach
I firstly parsed out the libraries, and make a dictionary with imported libraries as keys and a set of names of files
which import them as the value. Then I made another dictionary with same keys but this time values are n-size lists
(n = total number of files), and value 1 at position i represents "i.py" imported this library(key of this list in this
case). Afterwards labels were added to that dictionary and I converted this dictionary to a data frame using pandas
module. Then, I used sklearn module to import three classifiers, and did 10-fold cross validation using parsed data and
labels, along with measuring the average accuracy of each classifier.

## Challenge
The main challenge I met is mostly about finding a way to neglect documenting and comments in the files. To do that, I
learned and used the re module(regular expression), and let the program recognize pattern of triple quotation(either
double quotation mark or single quotation mark) and how many times this pattern occurs to determine if the next line is
in documenting, and along the way I used another pattern to recognize names of scripts in the directory entered.
Also I find out that some functions import some libraries, so I stripped the line in every iteration first and then
check if it starts with "import" or "from".
