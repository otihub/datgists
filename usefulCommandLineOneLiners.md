# Useful One-liners on the Unix/Linux Commandline

## Overview
This is a repository of short and sweet oneliners of code to help with automating annoying tasks

## Code Library

Combine two or more csvs together (and only keep the header of the first file) into a new csv.  Note, that the csvs must have matching columns.
< br />

`cat < firstFile.csv <(tail +2 secondFile.csv) <(tail +2 thirdFile.csv) > combineOutFile.csv`




