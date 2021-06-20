# Election Analysis
Audit of CO-1 congressional race using Python

## Election Audit Overview
In this project, Tom of the Colorado Board of Elections has tasked me with auditing the election results for Colorado's 1st Congressional District. Using Python, I have been asked to come up the following figures for the race: 
1) the total number of votes cast
2) votes broken down by county in absolute terms and as percentages
3) the county with the largest number of votes cast
4) a breakdown of the number and percentage of votes cast by candidate
5) the winner of the popular vote, along with the number of votes they received and their share of the vote total

## Resources
Data source: election_results.csv

Software: Visual Studio Code 1.52.1, Python 3.8.6

## Election Audit Results
* **Total votes cast in election**

369,711

* **Votes by county**

|County|Votes|Share of vote count|
|------|-----|-------------------|
|Jefferson|38,855|10.5%|
|Denver|306,055|82.8%|
|Arapahoe|24,801|6.7%|

* **County with the most votes**

Denver

* **Votes by candidate**

|Candidate|Votes|Share of vote count|
|---------|-----|-------------------|
|Charles Casper Stockham|85,213|23.0%|
|Diana DeGette|272,892|73.8%|
|Raymon Anthony Doane|11,606|3.1%|

* **Winning candidate**

Diana DeGette won the election with 272,892 votes, which represents 73.8% of all ballots cast. 

The full .txt readout of the analysis looks like this and can be found [here:](https://github.com/perryabdulkadir/Election-Analysis/blob/main/analysis/election_results.txt)

![election_results_printout](Resources/election_results_printout.PNG)


## Election Audit Summary

Currently, this script could be used to analyze any other election where the data is collected on the ballot level, the county's name is in the 2nd column, and the candidate's name is in the third column. 

The process for changing the script to work on similarly structured data for a municipal election would be quite simple. Imagine instead of a using this script for a Congressional race in Colorado we instead used it for a mayoral race in Denver. If this dataset instead had votes broken down by precinct rather than county, it would be simple to change. While not strictly necessary, it would be best practice to rename all county variables to things like "precinct_name," "precinct_list," and "precinct_dict" etc.

The only necessary change for the end user would be changing the print text from
```
 print("Largest county turnout:", largest_county, "\n")
 ```
 to
 
```
 print("Largest precinct turnout:", largest_precinct, "\n")
```
and from
```
 election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n")
    print(election_results, end="")
    txt_file.write(election_results)
```
to
```
 election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"Precinct Votes:\n")
    print(election_results, end="")
    txt_file.write(election_results)
 ```
 
This script could be changed in this way to accommodate any level of geography. For example, in a Colorado gubernatorial race, there may be data that has individual ballot data broken down on a municipal level. To accommodate this change would be simple. For programmer ease of use, variables should be renamed to "city_name," "city_list," and "city_dict," etc. From there, the print and write functions would need to be changed slightly. 

```
 print("Largest city turnout:", largest_city, "\n")
```
```
 election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"City Votes:\n")
    print(election_results, end="")
    txt_file.write(election_results)
 ```

-----

### **Contact:**

**Email:** perry.abdulkadir@alumni.harvard.edu

**Linkedin:** https://www.linkedin.com/in/perry-abdulkadir-6a255199/
