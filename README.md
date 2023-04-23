Download Link: https://assignmentchef.com/product/solved-assignment-2-stock-code-reader-codes
<br>
ICT209_Asg2_JoBlogs_12345678.zip

Assignment Question:

Design an object-oriented solution and implement the solution in C++ to solve the problem described below. You must read the entire specification and work out what is needed before starting work on this assignment.

Like assignment 1, this assignment is not for actually buying and selling shares. The assignment only deals with data from past share transactions (trades).

The solution needs to be worked out on paper before you start coding.

Extend assignment 1 to do the tasks described below.  You need to also reflect on the design and code changes needed to convert your assignment 1 into assignment 2.

Start early. Design the menu system and test to make sure the menu works. Use code stubs (refer to your earlier units) to test the overall flow of execution.  If you have forgotten what a stub is, see <a href="https://en.wikipedia.org/wiki/Method_stub?__hstc=188378999.453ca0259ce981127619062c7af1279b.1487744500573.1488090086728.1488094553241.27&amp;__hssc=188378999.2.1488094553241&amp;__hsfp=2337163350" target="_blank" rel="nofollow noopener noreferrer">http://en.wikipedia.org/wiki/Method_stub</a> for a quick overview. You already have data file reading code, so make sure that you are able to read data files correctly. In the initial stages, read the files and print them out to check. Once this stage is completed, you start using the data structures after unit testing the data structures.

Create your own test data files as given in these specifications below. You will be submitting these files.

Make sure you design a simple menu so that users do not get confused or annoyed – consider what it is like if you were the end-user.

Your program should be able to deal with course of sales data for multiple days and multiple stock exchange codes (x-code). Each day’s trading data for each stock code (x-code) is still stored in CSV files. This means that there will be a number of data files for each stock code.  For proper testing (for the various test conditions), you need to create your own data files. These test data files shouldn’t be large. There should only be enough data to check the test conditions. This involves various x-code values and dates. You decide on these values and the decision is important as the data values are used to test your solution.

Program input:

The data format in each course of sales file is the same as assignment 1. As there are multiple x-codes, the date files are arranged in directories or folders. The folder names are the x-codes. To illustrate, assume there are course of sales data for 3 companies with their own x-codes. Assume the x-codes are IAG, NAB, CBA. The data folder will have 3 folders called “IAG”, “NAB”, and “CBA”. This data folder will have an index file called code_index.txt.  The contents of this index file would just be the x-code names whose folder exists in the data folder. The folder names match the x-code names.

So, for this example, code_index.txt will contain each x-code on a line:

IAG

NAB

CBA

The contents of code_index.txt indicate that there are these 3 sub-folders in the data folder.

Do not make any assumption that the x-code is sorted in code_index.txt.

The course of sales files (in CSV format, as in assignment 1) for each day and given x-code will found in the sub-folder of the data folder. As indicated earlier, the sub-folder is named by the x-code. Do not make any assumptions about the naming conventions used for the course of sales files. The names of the files in the x-code sub-folders are listed in a file called sales_index.txt. Each x-code subfolder will have a sales_index.txt file.

Assuming that the folder IAG has course of sales files day1.csv, day2.csv, day3.csv, the sales_index.txt file in folder IAG will contain the following lines.

day1.csv

day2.csv

day3.csv.

Do not assume that there is any sort order in sales_index.txt. The names of the CSV files do not indicate any chronological order. Arrange your data files to reflect this – change the order in which the files are listed and check.

So to read course of sales data into your program:

In the data folder, read the code_index.txt file.

For each code in code_index.txt

Read code/sales_index.txt

For each csv file in code/sales_index.txt

Load the csv file data into your program.

Endfor

Endfor

The program reads all files and loads the appropriate data structures before the menu is displayed to the end user.

Program output:The program reads data from the data files and produces output according to the menu option selected by the user. Assignment 2 deals with multiple stock codes and course of sales for multiple days. Consequently, most of the menu options are variations of what was needed for Assignment 1.

Date is shown as dd/mm/yyyy. (02/01/2014).

Time uses the 24-hour format.

The stock code is the x-code.

Read the requirements for each option, and design your menu system to be user friendly.  Your design may have some of the menu options listed below as sub-menus.

Before any menu option is displayed, the program reads all data files and loads the appropriate data structures.

Menu option 1:The highest share price and start time(s) of the highest share price during the day for a user specified stock code and date. This is printed on the screen in the following format:

Stock code: &lt;the stock codeDate: &lt;the transaction dateHighest price: &lt;the highest priceStart time(s):&lt;time when highest price transaction occurred&lt;time when highest price transaction occurred…

The highest price could be reached more than once during the day. If so, list each time on a new row. Do not list duplicate time values.

Menu option 2:The lowest share price and start time(s) of the lowest share price during the day for a user specified stock code and date. This is printed on the screen in the following format:

Stock code: &lt;the stock codeDate: &lt;the transaction dateLowest price: &lt;the lowest priceStart time(s):&lt;time when lowest price transaction occurred&lt;time when lowest price transaction occurred…

The lowest price could be reached more than once during the day. If so, list each time on a new row. Do not list duplicate time values.

A value of 0 for price should not be part of the output.

Menu option 3:This option is for a user specified stock code and date.

The output goes to a file called price-change-date.csv where the fields (individual items of data) are separated by commas.  The date part of the file name depends on the user specified date. The format is yyyy-mm-dd. As an example, an output file can be price-change-2014-02-10.csv. This is the output for the 10th of February 2014.  This file is created in the specified x-code directory.

The output format is:

Stock code, Date, Start time, Price of share, Volume of shares traded, Total value of shares traded

Make sure you write the header row. This is the first row of the output file. This involves simply printing the format line above as a string.

The data file will have a record (row) for each time the share price changes. The output will have data arranged in increasing time order.

The output fields have the following meanings:

Stock code: The x-code.Date: Date of trading.Start time: The time when the share price changed to the value indicated in the “Price of share” field. This time value is used to indicate that the share price changed to a new price value. The input data file may have multiple consecutive records (rows) where the share price is the same. This means that there may be multiple consecutive share transactions where the share price remained the same. In the output data file, output.csv, the Start time field records when the share price changed to a different value. The intention here is that this field records the time of initial change to a price in a series of consecutive same price transactions.Volume of shares traded: The number of shares traded since “Start time” at the value indicated in the “Price of share” field.Total value of shares traded: The total monetary (dollar) value of the shares given in the “Volume of shares” field.Treat a value of zero (0) for the price field in the input data file the same way as other prices are treated.

Menu option 4:This menu option is to be completed only when all other menu options are working as expected.

Proper completion of this option will give you a 15 marks bonus. If you attempt this option when any of the other options are not working, no bonus marks would be awarded.

It is theoretically possible to get 115 marks if all options are done perfectly. However the maximum mark that will awarded is 100.

Calculate a simple moving average (SMA) for the price of a user specified stock code on a given date. The moving average is over 5 transactions by default. The output goes to a file named SMA-date.csv.

The date part of the file name depends on the user specified date. The format is yyyy-mm-dd. As an example, an output file can be SMA-2014-02-10.csv. This is the SMA for the 10th of February 2014.  This file is created in the specified x-code directory.

The output format is:

Stock code, Date, Time, Price of share, simple moving average.

Make sure you write the header row. This is the first row of the output file. This involves simply printing the format line above as a string.

Stock code and Date have the same meaning as in option 3. Time is the recorded time in the course of sales file. Price of share is the price recorded in the course of sales file. The SMA is described at <a href="http://www.investopedia.com/terms/m/movingaverage.asp?__hstc=188378999.453ca0259ce981127619062c7af1279b.1487744500573.1488090086728.1488094553241.27&amp;__hssc=188378999.2.1488094553241&amp;__hsfp=2337163350" target="_blank" rel="nofollow noopener noreferrer">http://www.investopedia.com/terms/m/movingaverage.asp</a>.  Use the approach described at this site but instead of using daily closing prices, the actual transaction price at a given time recorded in the course of sales file is used.

Provide a sub-menu of this menu that enables the default of 5 transactions for the moving average to be changed to some other value.

Price values of 0 must not be averaged.

Menu option 5:Exit the program

Data Structures requirement:

STL data structures and algorithms can be used in this assignment.  You must use the templatized Binary search tree data structure and the templatized STL map (and/or multimap) data structure.

The data for the output in the various menu options must come from these data structures. You may use other data structures together with the STL map and tree.

You need to identify where these data structures can be used and provide a rationale for their use. There is a 30 marks penalty if you do not do this.

You may use std::string and string stream classes in your program instead of using C like strings. You may use iostream and file handling classes and objects in C++.  See laboratory exercises.

When working on this assignment, think of the usability of your program from the point of view of the user. This is the first thing you have to do, even before you start designing the program. This will form the menu system for the running program. You should not make the program more complicated than what is specified in the assignment. Make sure you provide an option to exit the program.

Any advice and further clarifications to these requirements would be found in the QandA file in the Assignment 2 folder. Please ask your questions early and do not wait until near the due date as you may not have time to incorporate any answers into your assignment.