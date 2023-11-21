# MSR 2024 Mining Challenge
Link: https://2024.msrconf.org/track/msr-2024-mining-challenge
## DevGPT Infrastructure
Link: https://github.com/NAIST-SE/DevGPT

# CEN - 5035 - Software Engineering - Group 22
## Group Members:
### Roochitha Ikkurthy (RI23B)
### Chaitanya Guntupalli (CG21BB) 
### Srinija Dharani (SD23BE)
## Contributor: Chaitanya Guntupalli (CG21BB)

## Contents

1. [Reseeach Question](#research-question)
2. [Coding Environment](#coding-environment)
3. [Methodology](#methodology)
	- [Data Collection](#data-collection)
	- [Data Preprocessing](#data-preprocessing)
	- [Issue Categorization](#issue-categorization)
	- [Length of Conversation Calculation](#length-of-conversation-calculation)
4. [Status Report](#status-report)
5. [Future Work](#future-work)

## Research Question

How does the length of conversations with ChatGPT change based on the type of issue presented? 

## Coding Environment

I've used Jupyter Notebook for the entire process of collecting, cleaning(Preprocessing) and categorizing the data, and also the plan is to use the Data Visulaizing tool within this Environment for the nest representation of the rsults.

## Methodology

### Data Collection

I've choosen commit_sharing.json file in Snapshot_20231012. Throughtout the process I've considered only this Snapshot as this snapshot is the latest addition to the data and has all the data included in it from previous snapshots.

Snapshot_20231012
	commit_sharing.json
	hn_sharig.json
	pr_sharing.json
	file_sharing.json
	issue_sharing.json
	discussion_sharing.json
	ChatGPT_Link_sharing.csv

### Data Preprocessing

In the .json file, I've navigated through the nested structure, iterated over each element in the 'Sources' column, for each element in 'Sources', accessed 'ChatgptSharing', which is a list, within each item, accessed 'Conversations', and then extracted 'prompt' and 'Answer' from each item in the 'Conversations' list.

This results in a DataFrame with two columns 'Prompts' and 'Answers' corresponding to the data in the JSON files

### Issue Categorization

To categoriza the issues, I've defined rules for how to classify each prompt into issues such as Bugs, Features, Errors, and others. I started by analyzing the conversations data to find keywords and patterns that re typically associated wth each category.
For example, Bugs might more likely include words like "error", "problem", "bug", "issue"
I've written a function that takes 'Prompts' as input and returns the category based on the keywords and patterns defined. this functions basically defines the accuracy of the data.

### Length of Conversation Calculation

For calculating the length of coversation, I've modified the data processing as such that I'll also count the number of turns in each conversation while processing the JSON data to extract 'Prompts' and 'Answers'.
I've included a new column in my DataFrame, that stores the length of eeach conversation.

## Status Report

As of this phase of the project, I've worked towards asnwering the reseach question, I've learned from my group member that the latest snapshot includes all the previous snapshots data init. it helped in subsetting the data to be collected from the DevGPT snapshots. I've used the Jupyter Notebook which helps me access the data easy with Python language and its easy to use. As explained the previous sections, I've managed to clean the data, categorize the issues, and calculate the length od conversation.

## Future Work

I've also included some Data Visualization using Python Matplot in the Notebook, which can seem to be the final step of work on the first JSON file, but I still have to improve the issue categorization, as the number of issues categorized as 'others' should be lesser. 
This will improve the accuracy of issue categorization.

For categorizing, I'll also try the NLP models to understand if they are providing any better results that the regular classification.

What provides the best result will be used on all the remaining .json files and will be presented in the final report.

