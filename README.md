# Citizen Browser: Facebook Keeps Recommending Political Groups, Including Some Associated With Militias
This repository contains data from the story ["Facebook Keeps Recommending Political Groups—Including Militia Groups—To Its Users, Despite Promises"](https://themarkup.org/citizen-browser/) from from our series, [Citizen Browser](https://themarkup.org/citizen-browser/). Citizen Browser construction and methodology is described in "[How We Built a Facebook Inspector](https://themarkup.org/citizen-browser/2021/01/05/how-we-built-a-facebook-inspector)."

## Methodology
In the absence of a clear definition of political groups from Facebook, we took the standard Facebook uses when [classing ads as political](https://www.facebook.com/business/help/167836590566506?id=288762101909005) — *containing a call to political action or support for politicians, movements, parties or ideologies* — and constructed a simple classifier based on a list of the names of the President, Vice President and [serving members of the House and Senate](https://github.com/unitedstates/congress-legislators), plus two high profile non-serving politicians (Hillary Clinton and Donald Trump).

We also counted recommendations for groups supporting local or national branches of the Republican and Democratic parties, defined by searching for the keywords "Democrat" or "Republican" and manually filtering out non-political results. Groups promoting the ideologies of democratic socialism or political (anti-monarchy) republicanism were retained.

## Data
The `data/` directory contains files with data from the story, with csv files containing four different types of group.

1. `militia-groups.csv` contains 2 recommended groups that are associated with known militia movements.
2. `not-my-president.csv` contains 15 recommended groups with the phrase "Not my president" in the group title.
3. `republican-democrat.csv` contains 330 recommended groups with "Republican" or "Democrat" in the group title.
4. `political-figures.csv` contains 584 recommended groups containing the name of a current legislator or political figure, as defined above.

The data is also available in Excel spreadsheet format, with each of the above group types represented in a separate tab.
