# Orders of authors for journals
This dataset identifies the journals whose policy is alphabetical order of authors for the publications.

It contains:
* Journal's name
* Journal's normalized name
* Alphabeticality score

## Alphabeticality score
Ranges from -1 to 1. Maximum alpha score is 1 for journals with alphabetical order of authors. The majority of journals have alpha distributed around zero with few hunderd journals with alpha closer to one.

Data: I used data from the Microsoft Academic Graph. The journals analyzed are those who have published papers in years 2011-2015. Only papers with more than 3 authors have been included in the analysis. Only journals who have published more than three papers in the selected years are analyzed.

Methodology: For each paper in the dataset I estimate how much the authors order differ from the alphabetical order. For that, I use Kendall's tau correlation which ranges from 1 if the order is identical (the order is actually alphabetical) to -1 if the order is opposite of the alphabetical. It can take any value in between.
