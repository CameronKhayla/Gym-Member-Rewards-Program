# Gym Member Rewards Program

Authors: Cameron Davis and Alexia John-Bellot

## Description

A python program that calculates the frequency of
attendance of a gym member and rewards them for their attendance.

## Achievements

Instead of attempting to collect data from a local gym, we created a dataset containing
10 random names with a corresponding ‘x’ for each day a member attended the gym.
Using openpyxl, we were able to read the excel file containing the member information
to extract the data we needed for the function to work. We used
concurrent.futures.ThreadPoolExecuter() to create a thread that counts a list called
data, which consisted of a single row within the spreadsheet. The function
memberRewards() was created to identify when a column in the row contains ‘x’ and
count the total number times ‘x’ was found in the row, representing the member’s
attendance. We also created if statements to tell the user what reward they earned based
on the number of days they attended the gym.

## Issues

The main issue for this program was being able to identify the ‘x’ in the rows. We
initially tried using pandas and changing the way the data was displayed in the
spreadsheet, however, although we were able to easily locate the ‘x’ in the row, there was
not a need to use a thread. We eventually found that to find the value of a cell using
openpyxl, we only needed to call the sheet.cell.value to return the value without having
to manipulate the code to find the ‘x’ in the spreadsheet. The ThreadPoolExecuter()
successfully goes through the row and counts ‘x’, however, we came across another issue
where it was only counting up until the next cell was an empty cell, which means that
part of the function is likely missing a piece. We ran out of time before being able to
solve this problem because of the difficulty with understanding how to use openpyxl to
find exactly what data we are looking for and how to properly get to it. I believe a way to
solve this problem could be by changing which row the function starts on, however, I got
several errors when trying to manipulate the code in that way. In the end, the output no
matter what name you enter will get you 22 occurrences.

## Future Work

We would like to continue to work to find the solution to the current problem stated
about. In addition, we wanted to create a GUI so that the user is actually able to sign in
with a name and password to access their membership and rewards.
