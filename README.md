# An Examination of Visa Applicant Data [2012 - 2017]

Statistical testing & partner project with Jonathan Keller for the Flatiron School Data Science Program. We reviewed a dataset from Kaggle and determined four hypotheses. We used Chi-squared tests and ANOVA to determine the statistical significance of our hypotheses. 

<p align="center"> 
<img width="300" height="300" src=https://user-images.githubusercontent.com/54602329/67625653-d21f2d80-f80e-11e9-9546-5623757042c5.png>
</p>

## US Visa Applicant Hypotheses

__HO1__: Working for a Fortune 500 company has no impact on a visa application certification.

__HA1__: If applicants are from a Fortune 500 company, it is more probable that their visa will be certified.

### Methodology and Results:

- A list of Fortune500 companies was scraped from the Fortune500 for the years covered by the dataset.

- A sample of the source dataset was extracted and each observation was updated with whether the employer for that applicant was a Fortune500 company. 

- A Chi-Squared test was performed to compare the Fortune500 company applicants approval rates versus their non-Fortune500 counterparts with an alpha of 0.01. 

- Our P was ~0.0, so there is an extremely high correlation between an applicant’s employer being a Fortune500 company and their certification rates. 

![visa1](https://user-images.githubusercontent.com/54602329/67626407-20392e80-f819-11e9-909d-f9f148d4f516.png)



__HO2__: There is no relationship between annual salaries offered and country of origin in the technology industry for software developer roles.

__HA2__ : There is a relationship between annual salaries offered to candidates and their country of origin in the technology industry for software developer roles.

### Methodology and Results:
 - There is no statistical difference between certified applicants and denied applicants, thus all applicant data was used in the analysis.
 
 - Using Python/pandas North American Industry Classification Titles were grouped together to form the "Technology Industry". Standard Occupation Codes were grouped together to form "Software Developer Roles". Groupings are listed in the footnote section below.

 - If 5 or less applicants represented a country, they were considered outliers and removed.

 - ANOVA test was run for two-categories of data: job level and birth country.  
 
 - Alpha = .05
 - There is a relationship between annual salaries offered to candidates and their country of origin in the technology industry for computer programming roles [P = 1.017885e-40 ] 
 
![country](https://user-images.githubusercontent.com/54602329/67626389-e2d4a100-f818-11e9-82e6-21f46ea2cb01.png)

![country2](https://user-images.githubusercontent.com/54602329/67626390-e7995500-f818-11e9-908c-435176c90b2f.png)



__HO3__: There is no difference in certification rates between STEM US ECONOMIC SECTORS and NON_STEM SECTORS.

__HA3__ : There is a difference in certification rates between STEM US ECONOMIC SECTORS and NON_STEM SECTORS.

### Methodology and Results:

- Grouped together STEM SECTORS and NON-STEM SECTORS. Groupings are listed in the footnote section below. 

- Took the certified and denied applicant counts for each group and created a two-dimensional array.

- Because we are looking at one categorical variable - certified or not - for two populations, we ran a Chi-squared test for homogeneity. 

- Alpha = 0.05

- P = 1.7341877760642102e-06 

 - There is a difference in certification rates between STEM US ECONOMIC SECTORS and NON_STEM SECTORS with STEM clearly leading. 
 
![ch1](https://user-images.githubusercontent.com/54602329/67626391-ebc57280-f818-11e9-8894-f6e5b3ab7fde.png)



__HO4__: There is no difference in certification rates between hourly and salaried employees.

__HO4__: There is no difference in certification rates between hourly and salaried employees.

### Methodology and Results:

 - We divided the dataset into two populations- those applicants who were being offered an hourly position and those who were being offered a salary (or yearly) position. 

 - Took the certified and denied applicant counts for each group and created a two-dimensional array.

 - Because we are looking at one categorical variable - certified or not - for two populations, we ran a Chi-squared test for homogeneity. 
 
 - Alpha = 0.01

 - P = ~0.0

 - There is a significant difference in certification rates between hourly applicants and salary applicants with salary applicants certifying 7% more often. 
 
![ch4](https://user-images.githubusercontent.com/54602329/67626392-ed8f3600-f818-11e9-8f9a-2f69234db97e.png)



## Key Take Aways

 1. The majority of temporary visas granted are H1-B work visas. This reflects a considerable lack of available US talent in the jobs and sectors that are granted large numbers of visas.

 2. The jobs associated with visas are often high paying and technical.

 3. The short list of organizations that benefit the most from visa’s are companies that represent two-thirds of the U.S. GDP.

 4. While there is a relationship between birth country and salaries, it is unclear what additional factors may contribute to this relationship including differing education systems and regional expertise.

***



## _Footnotes_

### _Common Visa Types_:
__H1-B__: a visa that allows U.S. employers to temporarily employ foreign workers in specialty occupations. A specialty occupation requires the application of specialized knowledge and a bachelor's degree or the equivalent of work experience.

__L-1__: L-1 visas are available to employees of international companies with offices in both the United States and abroad. The visa allows foreign workers to relocate to the corporation's US office after having worked abroad for the company for at least one continuous year within the previous three prior to admission in the US. 

__F-1__: student visa that allows foreigners to pursue education -academic studies and language training programs- in the United States. 

__TN__:  NAFTA visa,  special non-immigrant status in the United States, Canada, and Mexico that offers expedited work authorization to a citizen of these countries. 

__E2__:  Investor Visa allows an individual to enter and work inside of the United States based on an investment he or she will be controlling, while inside the United States. The E2 visa is good for three months to five years (depending on the country of origin) and can be extended indefinitely.

### _Applicant Outcomes_:

__Denied__: An application may be denied because it did not provide all  information required to determine if the applicant is eligible to receive a visa, or because the applicant does not qualify for the visa category for which he or she applied, or because the information reviewed indicates the applicant is ineligibility under the law.

__Withdrawn__: Withdrawal of application for admission is suitable for cases where an alien may have innocently or through ignorance, misinformation, or bad advice, obtained an inappropriate visa but has not concealed the true purpose of the trip. A voluntary withdrawal will allow them to reapply and avoid being barred from future entry.

__Certified__: The applicant has provided all relevant information and has met eligibility requirements. The visa is granted.

__Certified-Expired__: The applicant has provided all relevant information and has met eligibility requirements, but has not followed up by filing the I-140 form within 180 days of certification, causing the certification to expire.  The visa is no longer valid. 

### _Technology Industry NAIC Titles_:

COMPUTER SYSTEMS DESIGN SERVICES

CUSTOM COMPUTER PROGRAMMING SERVICES

OTHER COMPUTER PERIPHERAL EQUIPMENT MANUFACTURING

COMPUTER SYSTEMS DESIGN AND RELATED SERVICES

OTHER COMPUTER RELATED SERVICES

WEB SEARCH PORTALS

SOFTWARE PUBLISHERS

FINANCIAL TRANSACTIONS PROCESSING, RESERVE, AND CLEARINGHOUSE ACTIVITIES

COMPUTER AND COMPUTER PERIPHERAL EQUIPMENT AND SOFTWARE MERCHANT WHOLESALERS

INTERNET PUBLISHING AND BROADCASTING

SECURITY SYSTEMS SERVICES

ENGINEERING SERVICES

INTERNET SERVICE PROVIDERS AND WEB SEARCH PORTALS

DATA PROCESSING, HOSTING, AND RELATED SERVICES

### _Software Developer SOCs_:

COMPUTER SYSTEMS DESIGN SERVICES

CUSTOM COMPUTER PROGRAMMING SERVICES

OTHER COMPUTER PERIPHERAL EQUIPMENT MANUFACTURING

COMPUTER SYSTEMS DESIGN AND RELATED SERVICES

OTHER COMPUTER RELATED SERVICES

WEB SEARCH PORTALS

SOFTWARE PUBLISHERS

FINANCIAL TRANSACTIONS PROCESSING, RESERVE, AND CLEARINGHOUSE ACTIVITIES

COMPUTER AND COMPUTER PERIPHERAL EQUIPMENT AND SOFTWARE MERCHANT WHOLESALERS

INTERNET PUBLISHING AND BROADCASTING

SECURITY SYSTEMS SERVICES

ENGINEERING SERVICES

INTERNET SERVICE PROVIDERS AND WEB SEARCH PORTALS

DATA PROCESSING, HOSTING, AND RELATED SERVICES

### _STEM Sectors_:

IT

AEROSPACE

ADVANCED MANUFACTURING

ENERGY

BIOTECHNOLOGY

GEOSPATIAL 

AGRIBUSINESS

AUTOMOTIVE

### _Non-STEM Sectors_:

EDUCATIONAL SERVICES

RETAIL

CONSTRUCTION

HOSPITALITY

HEALTH CARE

FINANCE

TRANSPORTATION

