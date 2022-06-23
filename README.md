# DDP-Cricket-Analytics
A host of time series algorithms
*******  ECONOMETRIC TIME SERIES MODELS IN CRICKET  *******

1) Download the CSV files named Indian.csv, Overseas.csv, Indian_correct_fcode.csv
and Overseas_fcode.csv from github.

2) Open STATA, click on File on the top left corner, click Import, select csv and 
choose the appropriate dataset

I) Ordinary Least Squares Models (OLS)
-> For Indian players, use the Indian.csv file
-> Write the following command on the terminal:
reg amount playerage y14 y15 y16 y17 y18 y19 y20 y21 y22

-> For Overseas players, use the Overseas.csv file
-> Write the following command on the terminal:
reg amount playerage country y14 y15 y16 y17 y18 y19 y20 y21 y22




II) Fixed Effects Model (FE)
-> For Indian players, use the Indian_correct_fcode.csv
-> Declare the data as panel data by writing the following command:
xtset fcode year
-> Write the following command on the terminal:
xtreg amount playerage,fe

-> For Overseas players, use the Overseas_fcode.csv file
-> Declare the data as panel data by writing the following command:
xtset fcode year
-> Write the following command on the terminal:
xtreg amount playerage country,fe




III) Random Effects Model (RE)
-> For Indian players, use the Indian_correct_fcode.csv
-> Declare the data as panel data by writing the following command:
xtset fcode year
-> Write the following command on the terminal:
xtreg amount playerage,re theta

-> For Overseas players, use the Overseas_fcode.csv file
-> Declare the data as panel data by writing the following command:
xtset fcode year
-> Write the following command on the terminal:
xtreg amount playerage country,re theta



***************** HAUSMAN TEST TO DISTINGUISH BETWEEN FE AND RE ******************************
IV) Hausman test (Same procedure for both Indian and Overseas)
-> After computing the results from fixed effects model, write est store fixed
-> After computing the results from random effects model, write est store random
Write the command
hausman fixed random




V) LSDV Model
-> For Indian players, use the Indian_correct_fcode.csv
-> Declare the data as panel data by writing the following command:
xtset fcode year
-> Write the following command on the terminal:
regress amount playerage i.fcode

-> For Overseas players, use the Overseas_fcode.csv file
-> Declare the data as panel data by writing the following command:
xtset fcode year
-> Write the following command on the terminal:
regress amount playerage country i.fcode


************************  DONE!    ******************************
