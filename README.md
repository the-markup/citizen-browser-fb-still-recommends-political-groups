# Citizen Browser: Facebook Keeps Recommending Political Groups, Including Some Associated With Militias
This repository contains data from the story ["Facebook Keeps Recommending Political Groups—Including Militia Groups—To Its Users, Despite Promises"](https://themarkup.org/citizen-browser/) from from our series, [Citizen Browser](https://themarkup.org/citizen-browser/). Citizen Browser construction and methodology is described in "[How We Built a Facebook Inspector](https://themarkup.org/citizen-browser/2021/01/05/how-we-built-a-facebook-inspector)."

## Methodology
In the absence of a clear definition of political groups from Facebook, we took the standard Facebook uses when [classing ads as political](https://www.facebook.com/business/help/167836590566506?id=288762101909005) — *containing a call to political action or support for politicians, movements, parties or ideologies* — and constructed a simple classifier based on a list of the names of the President, Vice President and [serving members of the House and Senate](https://github.com/unitedstates/congress-legislators), plus two high profile non-serving politicians (Hillary Clinton and Donald Trump). Results were manually reviewed to remove groups related to non-political figures sharing names with politicians, such as the musician Al Green.


We also counted recommendations for groups supporting local or national branches of the Republican and Democratic parties, defined by searching for the keywords "Democrat" or "Republican" and manually filtering out groups unconnected to US politics, e.g. the United Kingdom Democratic Socialist Movement. Groups promoting the ideologies of democratic socialism or political (anti-monarchy) republicanism were retained.

We also examined groups with the phrase "not my president" in the title, and identified militia groups through targeted keyword search and review.

## Data
The `data/` directory contains five csv files with data from the story. The first four csv files list the different types of group cited:

1. `militia-groups.csv` contains 1 recommended political group with "militia" in the name.
2. `not-my-president.csv` contains 15 recommended groups with the phrase "Not my president" in the group title.
3. `republican-democrat.csv` contains 330 recommended groups with "Republican" or "Democrat" in the group title.
4. `political-figures.csv` contains 584 recommended groups containing the name of a current legislator or political figure, as defined above.

The fifth csv, `top-100.csv`, contains the 100 groups that were recommended to the most Citizen Browser panelists during the time of this investigation, along with a `TRUE` / `FALSE` flag denoting whether the group was assessed to be political.

The data is also available in [Excel spreadsheet](https://github.com/the-markup/citizen-browser-fb-still-recommends-political-groups/raw/main/data/Political%20recommended%20groups%20February-June.xlsx) format, with each of the above group types represented in a separate tab.

-----

Data in files 1-4 is arranged as follows:
| column           | decription                                                                                |
|:-----------------|:------------------------------------------------------------------------------------------|
| group_name       | Name of the group at time of data collection                                              |
| group_slug       | The unique identifier from the the group URL, i.e. facebook.com/groups/<group_slug>  |
| n_user_recommend | Number of individual panelists who received a recommendation to join this group |
| last_recommended  | Latest date in the investigation time period that the group was recommended to a panelist |

Data in `top-100.csv` contains columns as above, and one additional column:

| column           | decription                                                                                |
|:-----------------|:------------------------------------------------------------------------------------------|
| is_political      | Boolean flag denoting whether the group was assessed to be political.                    |