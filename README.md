# CEN-5035-SE-GP
# Group 22
# CG21BB
## Contents

- [Reseeach question](#researchquestion)
- [Coding Environment](#codingenvironment)
- [Structure](#structure)
- [What's done so far](#whatsdonesofar)
- [What's left to be done](#whatslefttobedone)

## Research Question

How does the length of conversations with ChatGPT change based on the type of issue presented? 

## Coding Environment

I've used Jupyter Notebook for the entire process of collecting, cleaning(Preprocessing) and categorizing the data, and also the plan is to use the Data Visulaizing tool within this Environment for the nest representation of the rsults.

## structure

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

### Data Preprocessing(Cleaning)

In the .json file, I've navigated through the nested structure, iterated over each element in the 'Sources' column, for each element in 'Sources', accessed 'ChatgptSharing', which is a list, within each item, accessed 'Conversations', and then extracted 'prompt' and 'Answer' from each item in the 'Conversations' list.

This results in a DataFrame with two columns 'Prompts' and 'Answers' corresponding to the data in the JSON files

### Issue Categorization

To categoriza the issues, I've defined rules for how to classify each prompt into issues such as Bugs, Features, Errors, and others. I started by analyzing the conversations data to find keywords and patterns that re typically associated wth each category.
For example, Bugs might more likely include words like "error", "problem", "bug", "issue"
I've written a function that takes 'Prompts' as input and returns the category based on the keywords and patterns defined. this functions basically defines the accuracy of the data.

### Length of Conversation Calculation

