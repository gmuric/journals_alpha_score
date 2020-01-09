# Orders of Authors in Scientific Journals
This dataset identifies the journals whose policy is alphabetical order of authors in their publications.

Data format:
* Journal's name
* Journal's normalized name
* Alphabeticality score

## Alphabeticality score
Ranges from -1 to 1. Maximum alpha score is 1 for journals with alphabetical order of authors. The majority of journals have alpha distributed around zero with few hunderd journals with alpha closer to one.

Data: I used data from the Microsoft Academic Graph. The journals analyzed are those who have published papers in years 2011-2015. Only papers with more than 3 authors have been included in the analysis. Only journals who have published more than three papers in the selected years are analyzed.

Methodology: For each paper in the dataset I estimate how much the authors order differ from the alphabetical order. To measure that, I use Kendall's tau correlation which ranges from 1 if the order is alphabetical to -1 if the order is opposite of the alphabetical. It can take any value in between. Then, for each journal I estimate the alpha score by calculating the weighted average of the Kendall's tau for all the papers. The weights used for the weighted average are number of authors squared.
