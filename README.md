# Analyzing Hispanic Inmate Population

This is an informal analysis of the distribution of races assigned to hispanic inmates in two criminal justice systems.

## Description

I was reviewing the article [Using Python to scrape a website and gather data: Practicing on a criminal justice dataset](https://journalistsresource.org/tip-sheets/research/python-scrape-website-data-criminal-justice/) from Journalist's Resource, which analyses the list of inmates in Polk County, Iowa, and decided to go along with it. I noticed two things: the races assigned to inmates are  inaccurate and the structure of the site since the article was posted has changed.

Firstly, the inaccuracy is in that the Polk County System seems to only have some race categories, such as "Asian", "Black", "Pacific Islander" and "White". There is no category "Hispanic" for reasons unknown and they are usually classified as "White". These are arrest records and don't indicate whether the person was found guilty of a crime or not. Maybe there is a second layer where the information is retaken with more care, but at this step the data taken shows mistakes. I was not able to do more research into this.

Secondly, the way the data is presented in the website has changed. According to the article from Journalist's Resource, the site used to show the data in a table written into the html source of the page, which made it easy to search for the table row tag and extract the information. Now, the website seems to call a script to build the table (I know little about how to build websites at the moment so this is a noob's perspective, basically) and that means the data is not found in the _View Page Source_, so I had to look for another technique.

As this [article](https://www.urban.org/urban-wire/we-dont-know-how-many-latinos-are-affected-criminal-justice-system) from the Urban Institute states, not properly counting and describing the inmate population can affect the policies that are created to deal with racial disparities and mask the bias in a criminal justice system. The purpose of this analysis is to try and identify the Hispanic/Latino members from an inmate population and studying the race category they have been assigned. 


## Techniques

The comparison is done by comparing the last names of the inmates with a list of the most common hispanic last names in the US. The list is almost a 1000 names long and can be found from [Mongobay](https://global.mongabay.com/es/nombres/hispanic.html) and it is taken from the 2010 US Census. This list is reduced as some last names that would produce more non-hispanic results were present. This comparison should be taken as an approximation, since many cases can still slip through. Then, a Selenium WebDriver is used to access the webpages with the inmate data and what is displayed is then extracted and processed using Beautiful Soup. Finally, the data is collected and visualized using pandas. All the details of the code is explained in the Jupyter Notebooks used.

## Results

### Polk County

First, the data from Polk County is analyzed in this [Jupyter Notebook](link_to_notebook...). The counts of races of the inmates are shown in the following table:

| Race             | Original | Reviewed |
| ----------------:|---------:| --------:|
| Asian            | 21       | 20       |
| Black            | 248      | 232      |
| Pacific Islander | 9        | 8        |
| White            | 588      | 534      |
| Hispanic         | 0        | 72       |

where we notice that from starting with no hispanic population, 72 where identifed. From direct inspection of the inmate database one finds that non-black hispanics are usually labeled "White", so the Asian and Pacific Islander inmates relabeled as "Hispanic", as is shown in the table above, might be due to similarity in last name. The number of 72 hispanics is an approximation to the real number. A bar graph of the change in race distribution is shown next.

![Polk County Inmate Race Distribution](https://user-images.githubusercontent.com/13749006/65365672-6cc19680-dbe9-11e9-9110-7be8e2a5ec3d.png)


### Florida

_soon to be finished..._