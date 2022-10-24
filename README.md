# 1.0 Business Understanding
The task is to help a candidate to become US president. The winner of the election will be the candidate winning the most grand electors. 
Grand electors are attributed at the state level: in each of the 51 states, there is a given number of grand electors to win (roughly, but not exactly, proportional to the size of the state) and the presidential candidate receiving the most local votes wins ALL the Grand Electors in that state.
Because the number of grand electors is not exactly proportional to the population, some states can be prioritized to increase the return on investment of the campaign. We assume here there are only 2 candidates, and no history (no trend of certain states to vote for a particular candidate or party). Hence, each vote is equally "expensive" to get, but some states grant more grand elector per capita.

# 2.0 Data Understanding
At this moment, the team has no plans to purchase external databases or spend money
conducting surveys. This is because brute force computation of all possibilities to find the absolute optimum would be too computationally expensive.

Below are two datasets that we shall be considered for research:
* Grand electors by State.  [Link](https://drive.google.com/file/d/1AuPlNXKjmEdRTLGqKbP-OP1XZ5UQPIPw/view)
* Population by State. [Link](https://drive.google.com/file/d/1VKt_hF2pRqPxcNb1DKotkVXWNd2HX_KL/view)

##  2.1 Exploring data
The Population datasets we shall be using contains two columns, State and Population respectively with a total record of 57 states/ territories in the United State of America. The Grand Electors by state dataset contains two columns, State and GrandElectors with a record of 52 states/ territories in the United State of America.



##  2.2 Verifying data quality
We have noted from the datasets that states are not capitalized the same way in both tables (one is in uppercase letters, the other not), so you will need to convert all to uppercase, for instance’
We also have no missing records on the data. 

# 3.0 Data Preparation
* We joined the two tables using the State field as the key and making a new table by the name “Election”. 
* The team wanted to change the name of the "District of Columbia" state to its short version "DC", we updated the records accordingly.
* We created a new column by the name “Ratio” to  compute the ratio between the number of grand electors and the population.
* We ordered the states by decreasing ratio of Grand Electors per capita. This made our priority list.
* We computed the running total of Grand Electors in that sorted list.
* We salso computed the half of the total of Grand Electors overall (in the whole country). This made us to determine the threshold we need to reach for winning the presidential election.
* We filtered our sorted list of states in order to keep only the (top) ones enabling us to reach the computed threshold. (the other states will were ignored).

# 4.0 Modeling
We did a very simple analysis model to sort the columns and calculate the ratio between the grand electors and population. From our sorted data we created a new column to show the cumulative electors’ vote. We can easily see the 11 states with highest chances to get to the threshold electors votes i.e 270

# 5.0 Usage
This project was purely developed for Academic Purposes. It is NOT for any public or commercial use.

# 6.0 License
Distributed under the MIT License. See license.txt for more information.
