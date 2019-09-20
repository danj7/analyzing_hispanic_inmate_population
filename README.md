# Analyzing Hispanic Inmate Population

This is an informal analysis of the distribution of races assigned to hispanic inmates in two criminal justice systems.

## Description

I was reviewing the article [Using Python to scrape a website and gather data: Practicing on a criminal justice dataset](https://journalistsresource.org/tip-sheets/research/python-scrape-website-data-criminal-justice/) from Journalist's Resource, which analyses the list of inmates in Polk County, Iowa, and decided to go along with it. I noticed two things: the races assigned to inmates are  inaccurate and the structure of the site since the article was posted has changed.

Firstly, the inaccuracy is in that the Polk County System seems to only have some race categories, such as "Asian", "Black", "Pacific Islander" and "White". There is no category "Hispanic" for reasons unknown and they are usually classified as "White". These are arrest records and don't indicate whether the person was found guilty of a crime or not. Maybe there is a second layer where the information is retaken with more care, but at this step the data taken shows mistakes. I was not able to do more research into this.

Secondly, the way the data is presented in the website has changed. According to the article from Journalist's Resource, the site used to show the data in a table written into the html source of the page, which made it easy to search for the table row tag and extract the information. Now, the website seems to call a script to build the table (I know little about how to build websites at the moment so this is a noob's perspective, basically) and that means the data is not found in the _View Page Source_, so I had to look for another technique.

As this [article](https://www.urban.org/urban-wire/we-dont-know-how-many-latinos-are-affected-criminal-justice-system) from the Urban Institute states, not properly counting and describing the inmate population can affect the policies that are created to deal with racial disparities and mask the bias in a criminal justice system. The purpose of this analysis is to try and identify the Hispanic/Latino members from an inmate population and studying the race category they have been assigned. 


## Techniques

The comparison is done by comparing the last names of the inmates with a list of the most common hispanic last names in the US. The list is almost a 1000 names long and can be found from [Mongobay](https://global.mongabay.com/es/nombres/hispanic.html) and it is taken from the 2010 US Census. A Selenium WebDriver is used to access the webpages with the inmate data and what is displayed is then extracted and processed using Beautiful Soup. Finally, the data is collected and visualized using pandas. All the details of the code is explained in the Jupyter Notebooks used.

## Results

### Polk County

First, the data from Polk County is analyzed. 

_soon to be finished..._