# antoniotitanic
Week 3 HW Practice 
#This code chunk identifies my working directory 
#and sets it to where I want to save and fetch files
#TASK: fill in between the parentheses if needed. 
#If not needed, make the two lines a comment
getwd()
#(AT Comment)I did a run function to make sure I had the correct wd (i.e., my rfolder)
#setwd()
#(AT Comment)Since I'm not setting a new wd then I don't need this one

#This brings the 'Titanic' data into my environment from Base R (Run this)
Titanic

#This code saves the Titanic data as a dataframe with a new name
#TASK: Save the Titanic data as a dataframe with a new name that includes your first name
#for example I would name my data AnnaTitanic
antoniotitanic<-Titanic

#This code chunk allows me to see the top 2 rows of my data
#TASK: Write the code that returns the top rows
head(antoniotitanic,2)

#This code chunk shows me the internal structure 
#Task: Write the code that shows the number of rows, columns, column names, class of columns   
str(antoniotitanic)
#(AT Comment) Adding a couple of more below as well
nrow(antoniotitanic)
ncol(antoniotitanic)
colnames(antoniotitanic)
sapply(antoniotitanic,class)

#This code chunk shows me some basic summary stats
#Such as Min, Max, Mean. Quartiles...
#Task: Write the code that gives summary stats
summary(object=antoniotitanic)
#(AT Comment) Adding a couple of more below as well
min(antoniotitanic)
max(antoniotitanic)
mean(antoniotitanic)
quantile(antoniotitanic)
median(antoniotitanic)

#This allows me to save one column as its own object ('values' in the Environment)
#Task: Write the code to create an object for just the Sex column 
#and write the code to create an object for just the Age column 
#(these should show as values in the environment window, not as 'datasets'Data')
sex<-antoniotitanic["Sex"]
age<-antoniotitanic["Age"]

#This takes the individual objects ('values' in the Environment) and creates a dataframe
#Once I do this, I can see the Data in the Environment 
#Task: Write the code to create one new data.frame from the Sex and Age values you just created
sex_age<-data.frame(Sex=antoniotitanic['Sex'],Age=antoniotitanic['Age'])

#This code chunk creates a subset from my dataset
#Note that the subset only appears in the Console (not the Environment)
#Task: Write the code to create a subset of the data where the Freq is > 25
#If I wanted to save the subset, I would need to name it as done in the code above
filter(antoniotitanic,Freq>25)

#This shows me how many rows are in my dataset and
#TASK: Write the code that returns the number of rows
nrow(antoniotitanic)

#This shows me how many columns are in my dataset
#TASK: Write the code that returns the number of columns
ncol(antoniotitanic)

#This also shows me how many rows and columns with just one command
#TASK: Write the code that returns the number of rows and columns with just one command
dim(antoniotitanic)

#This code will install the ggplot2 package
#TASK: Write the code that installs the ggplot2 package
install.packages(pkgs="ggplot2")

#This code calls the ggplot2 package so I can use its functions
#Task: Write the code that 'calls' the ggplot2 package
library("ggplot2")

#This code creates a bar chart of the number of passengers that survived 
#and did not survive (2 bars)
#Task: replace the dataframe name and column names to create the chart
#(you should see the chart in the Plots window)
ggplot(Yourdataframename, aes(columnname, columnname)) +
  geom_col()
ggplot(antoniotitanic,aes('Survived','Freq'))+geom_col()
