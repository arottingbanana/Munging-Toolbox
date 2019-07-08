# Munging-Toolbox
# Some quick little tricks for data cleaning and preparation
# This is intended for R usage
# some commands are repeated in different sections for easy access

# Useful packages to use in data cleaning
library(dplyr)
library(caret)

# ACCESSING data
dataframe[c(1,2,3,4), c(1,2,3)] #remember to use c() to make specific references in datasets


# WHICH function
# You can use any combination of logical operators in the which function to return matching records of a dataset
# Remember that returning the records can be used as a count for different purposes
which(dataframe$column == max(dataframe$column)) #returns the positions of the maximum records in the data column
length(which(dataframe$column == max(dataframe$column)) #returns the count of the maximum records in the data column
DATAFRAME$data1[ which.max(DATAFRAME$data2) ] #returns the data1 value of the record containing maximum value for data2

# MISSING DATA
# Combinations of the which() and is.na() functions
datacolumn[which(is.na(datacolumn)] <- median(datacolumn) #replace missingness with a central operator
max(datacolumn, na.rm = TRUE) # removes missing data from being considered in the statistic, could save computing time
mean(is.na(datacolumn)) # returns the fraction of records that are missing

# Applying functions to list types like columns of a data frame
lapply(dataframe[1:8], class) # applies the class() function to the first 8 columns of the dataframe
table(unlist(lapply(dataframe[1:8], class))) #unlists the 8 classes and returns of a table summary

# MEAN USAGE
mean(dataframe$column %% 30 == 0 , na.rm=TRUE) #You can use logical operators in a mean function to subset columns prior to statistic
mean(is.na(datacolumn)) # returns the fraction of records that are missing
