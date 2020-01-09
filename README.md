# Orders of Authors in Scientific Journals
This dataset identifies the journals whose policy is alphabetical order of authors in their publications.

Data format:
* Journal's name [*string*]
* Journal's normalized name [*string*]
* Alphabeticality score [*float*]

## Alphabeticality score

**alpha=1** - The journal forces alphabetical order
**alpha=0** - The order is approximately random

Ranges from -1 to 1. Maximum alpha score is 1 for journals with alphabetical order of authors. The majority of journals have alpha distributed around zero with few hunderd journals with alpha closer to one.

**Data:** I used data from the Microsoft Academic Graph. The journals analyzed are those with the publications in years 2011 to 2015. Only papers with more than 3 authors have been included in the analysis. Only journals who have published more than three papers in the selected years are analyzed.

**Methodology:** For each paper in the dataset I estimate first how much the authors order differ from the alphabetical order. To measure that, I use Kendall's tau correlation which ranges from 1 if the order is alphabetical to -1 if the order is opposite of the alphabetical. Kendall's tau can take any value in between. Then, for each journal I estimate the alpha score by calculating the weighted average of the Kendall's tau for all the papers. The weights used for the weighted average are number of authors squared. The reason for using such weighted average is the number of the possible errors in the dataset. In case of the conflicting results, this way I value more the papers with more authors as it is much lower probability that they end up in an alphabetical order just by chance. Even though, the probability of having an exact order of n authors is n!, using factorial would give too much weight to very small number of papers. So, I decided to settle in between by using n squared.

![im] (https://github.com/gmuric/journals_alpha_score/blob/master/images/dist_alpha.png?raw=true)
