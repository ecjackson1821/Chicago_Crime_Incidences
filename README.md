## Police Data Accountability

This project has two components and serves as a proof of concept for ECCSC – a Chicago non-profit offering first responders as an alternative to the police. 

Most violence intervention groups primarily utilize Chicago Police data; however, ECCSC would like to use Citizen data to evaluate the accuracy of the Chicago Police Data, and consider using both data sources to compare their own first responder activity against. Their primary concern is that the Chicago Police data may not always categorize incident type correctly.

## 1. Record Link: 
Project EZ runs an analysis on two primary sources used to track crime incident data for Chicago. We apply a record linking algorithm to match crime data extracted
from the Chicago Data Portal’s API to reported incidences of crime pulled from crowdsourced application Citizen. We match incidences based on geo coordinates, date, and time. This enables ECCSC to evaluate Citizen reports of crime compared with Chicago’s Police response to crime and assess any severity differences in reporting.

## 2. First Response Activity: 
Pulls down data from a google survey which ECCSC uses to log first response activity. Cleans data and generates latitude and longitude coordinates to map
into a map of Chicago using Dash. ECCSC can visually assess their first response activity for internal operations and to demonstrate their value proposition to prospective funders.

## Project Structure

###1. Refresh Data
• Chicago data API pull
• Visualization of ECCSC data using Dash
• Command line interaction to select which component of  project to run
###2. Citizen scrape
• Built automated daily citizen pull (on local machine) 
• Storage system for preserving csv files aggregating by month 
of crime incident and key search terms 
###3. Refresh Data
• Pull down google sheet ECCSC data
• Find latitude and longitudes based on inputted survey data
• Record link algorithm
###4. Data Store
• SQL database connection for each data source
• Clean incoming data and data types
• Record link algorithm

## Interact with EZ Project
To run our project from command line:
cd ~/proj-ez
sh install.sh 
(if local machine requires different command line arguments for virtual environment, then enter 
following commands to run program)
cd ez
bash project-requirements

## Expected output:
Interaction:
• Asks for user input, if they would like to run record link analysis, map data, or exit program
• Once user inputs, echos user choice and runs corresponding command
• If still in script after command is run, reminds user of possible inputs
From Link Records Analysis:
• Prints the start and end dates captured by Chicago Crime data and Citizen. Prints number
of days captured between the two datasets which overlap and can generate a match
• Writes all matches to a csv file called “match_file.csv”
From ECCSC Map visualization:
• Displays map of first response activity from ECCSC data generated from google forms
survey. Click cursor on marker to display detail of crime type.

