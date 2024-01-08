Immigrant Mortality Advantage in the United States during the First Year
of the COVID-19 Pandemic
================
Eugenio Paglino and Irma T. Elo

<!-- README.md is generated from README.Rmd. Please edit that file -->

# Immigrant Mortality during the COVID-19 Pandemic

We used death records for 2017-2020 from the National Center for Health
Statistics (NCHS) under a data user agreement. We classified deaths by
sex, age, bridged race, Hispanic origin, nativity, and cause of death.
Deaths of US-born residents include deaths of individuals who were born
and resided in the 50 US states, and deaths of foreign-born residents
include deaths of foreign-born individuals residing in the 50 US states.

We obtained US population counts by age, bridged race, Hispanic origin,
and sex for 2017-2020 from CDC WONDER. To estimate population by
nativity we pooled the 2017-2019 American Community Survey (ACS) 1-year
files to estimate the proportion foreign-born by age, sex, race, and
Hispanic origin. We then applied these proportions to the population
counts to obtain populations by 10-year age groups, sex, race, Hispanic
origin, and nativity. Because the pandemic affected the 2020 ACS data
collection, we applied the 2019 proportions to the 2020 Census
population estimates. Supplementary Tables 1a and 1b present the number
of deaths and populations by nativity, race, Hispanic origin, and sex
for broad age groups in 2017-2019 and 2020.

We included nine exhaustive and mutually exclusive cause-of-death
categories based on the underlying cause of death. These are respiratory
diseases, circulatory diseases, cancers, Alzheimer disease and other
dementias, diabetes, COVID-19, external causes, and all other causes
combined (Supplementary Table 2). We chose these causes because
mortality from them increased during the pandemic.

Using the average 2017-2020 age distribution as the standard, we
calculated age-standardized death rates (ASDR) by sex, race,
Hispanic-origin, and nativity for all causes combined, COVID-19, and all
causes other than COVID-19 at ages 25+, 25-64, and 65+ and by the more
detailed causes at ages 25+ for 2017-2019 and 2020. We pooled three
pre-pandemic years to adjust for year-to-year fluctuations in death
rates. For each ASDR, we computed standard errors (SD) and coefficients
of variation (SD/ASDR), which are included in the Supplementary
Material. Because the size our smallest group (US-born Asian females in
2020) exceeds one million, all standard errors are small, and the
largest coefficient of variation is 3.75%.

Based on these data, we examined the contribution to COVID-19 and all
other causes of death, other than COVID-19, to the change in all-cause
mortality between 2017-2019 and 2020 by sex, nativity, and
race/ethnicity at ages 25+, 25-64 and 65+. We further decomposed the
cause-of-death contributions by the more detailed cause-of-death
categories to US-born and foreign-born difference in ASDRs at ages 25+
by race/ethnicity and sex in 2017-2019 and 2020 and their contributions
to the change in these differences between 2017-2019 and 2020.

## Repository Structure

In this repository we stored all the codes needed to reproduce the
figures and tables in the paper as well as supplementary material. Here
is the repository structure.

    ## /Users/eugeniopaglino/Dropbox/Upenn/GitHub/pandemic-immigrant-mortality
    ## ├── R
    ## │   ├── compWithWhitesPlots.Rmd
    ## │   ├── contributionsPlots.Rmd
    ## │   ├── createComorbTable.Rmd
    ## │   ├── createComorbTableComp.Rmd
    ## │   ├── createFinalTable.Rmd
    ## │   ├── createMortTable.Rmd
    ## │   ├── createPopTableCDC.Rmd
    ## │   ├── createPropTable.Rmd
    ## │   ├── mortalityDifferentialsPlots.Rmd
    ## │   ├── mortalityDifferentialsPlotsNoRatios.Rmd
    ## │   ├── mortalityRatiosPlots.Rmd
    ## │   ├── relativeComorbTable.Rmd
    ## │   └── sampleAndSummaryTables.Rmd
    ## ├── README.Rmd
    ## ├── README.md
    ## ├── data
    ## │   ├── input
    ## │   │   ├── ACS20171Year
    ## │   │   │   ├── ACS20171Year.dat
    ## │   │   │   └── ACS20171Year.xml
    ## │   │   ├── ACS20181Year
    ## │   │   │   ├── ACS20181Year.dat
    ## │   │   │   └── ACS20181Year.xml
    ## │   │   ├── ACS20191Year
    ## │   │   │   ├── ACS20191Year.dat
    ## │   │   │   └── ACS20191Year.xml
    ## │   │   ├── ACSDescStats
    ## │   │   │   ├── ACS17to19.dat
    ## │   │   │   └── ACS17to19.xml
    ## │   │   ├── CDCPopEstimates
    ## │   │   │   ├── CDCPopEstimates2017-2020.txt
    ## │   │   │   └── CDCPopEstimates2021.txt
    ## │   │   ├── CDCPopEstimatesSingleRace
    ## │   │   │   ├── SingleRacePop2017-2020.txt
    ## │   │   │   └── SingleRacePop2021.txt
    ## │   │   ├── ICD10CMCodes
    ## │   │   │   ├── ICD10CMCodesAll.txt
    ## │   │   │   └── ICD10CMCodesDetailed.txt
    ## │   │   ├── mort2017
    ## │   │   │   ├── 2014 Mortality History File Contents.doc
    ## │   │   │   ├── MULT2017.USPSAllCnty.zip
    ## │   │   │   ├── MULT2017.USPSAllCnty.zip.exe
    ## │   │   │   ├── MULT2017USAllCnty.txt
    ## │   │   │   └── Mort2005ToPresentAllCntyLayout_NAPHSIS.doc
    ## │   │   ├── mort2018
    ## │   │   │   ├── MULT2018.USPSAllCnty.zip.exe
    ## │   │   │   ├── MULT2018USAllCnty.txt
    ## │   │   │   ├── Mort2005ToPresentAllCntyLayout_NAPHSIS.doc
    ## │   │   │   └── Mort2018PS.AllCnty.txt
    ## │   │   ├── mort2019
    ## │   │   │   ├── MULT2019.USPSAllCnty.zip.exe
    ## │   │   │   ├── MULT2019PS.AllCnty.txt
    ## │   │   │   ├── MULT2019USAllCnty.txt
    ## │   │   │   └── Mort2005ToPresentAllCntyLayout_NAPHSIS.doc
    ## │   │   └── mort2020
    ## │   │       ├── MULT2020.PSAllCnty.txt
    ## │   │       ├── MULT2020.USPSAllCnty.zip
    ## │   │       ├── MULT2020.USPSAllCnty.zip.exe
    ## │   │       ├── MULT2020USAllCnty.txt
    ## │   │       └── Mort_2005ToPresentAllCntyLayout_NAPHSIS.doc
    ## │   └── output
    ## │       ├── ageStdRates.csv
    ## │       ├── ageStdRates.xlsx
    ## │       ├── ageStdRatesAbove65.csv
    ## │       ├── ageStdRatesAbove65.xlsx
    ## │       ├── ageStdRatesBelow65.csv
    ## │       ├── ageStdRatesBelow65.xlsx
    ## │       ├── ageStdRatesForPrint.xlsx
    ## │       ├── ageStdRatesSens.csv
    ## │       ├── ageStdRatesSens.xlsx
    ## │       ├── comorbTableUCD.csv
    ## │       ├── comorbTableUCDComp.csv
    ## │       ├── exampleData.csv
    ## │       ├── finalTable.csv
    ## │       ├── finalTable.feather
    ## │       ├── mortTable.feather
    ## │       ├── popTable.feather
    ## │       ├── proportionsData.feather
    ## │       ├── relativeComorbTable.csv
    ## │       ├── standardPop.csv
    ## │       ├── statsForAbstract.xlsx
    ## │       ├── summaryTableDataFemales.csv
    ## │       └── summaryTableDataMales.csv
    ## └── figures
    ##     ├── ICDCodesTable.docx
    ##     ├── USBornForeignDiffFemalesColorSafePlot.svg
    ##     ├── USBornForeignDiffFemalesColorSafePlotSens.svg
    ##     ├── USBornForeignDiffMalesColorSafePlot.svg
    ##     ├── USBornForeignDiffMalesColorSafePlotSens.svg
    ##     ├── absDiffTrendsByAgeHBarPlotRR.svg
    ##     ├── absDiffTrendsSimplePlot.svg
    ##     ├── absDiffTrendsSimplePlotSens.svg
    ##     ├── ageStdRatesForPrint.pdf
    ##     ├── contributionsTableFemales.docx
    ##     ├── contributionsTableMales.docx
    ##     ├── diffTrendsPlot.svg
    ##     ├── diffTrendsPlotSens.svg
    ##     ├── diffTrendsTable.docx
    ##     ├── popTable.png
    ##     ├── ratioTrendsPlot.svg
    ##     ├── ratioTrendsPlot2.svg
    ##     ├── ratioTrendsPlotSens.svg
    ##     ├── ratioTrendsTable.png
    ##     ├── relDiffTrendsHBarPlot.svg
    ##     ├── relDiffTrendsHBarPlotRR.svg
    ##     ├── relDiffTrendsHPlot.svg
    ##     ├── relDiffTrendsSimpleHPlot.svg
    ##     ├── relDiffTrendsSimpleHPlotSens.svg
    ##     ├── sampleTable2Females.docx
    ##     ├── sampleTable2Males.docx
    ##     ├── sampleTableFemales.docx
    ##     ├── sampleTableMales.docx
    ##     ├── summaryTableFemales.docx
    ##     └── summaryTableMales.docx

The `data/output` folder contains all the datasets produced in the
project. The most important ones are the `ageStdRates*.csv` files that
store the age standardized crude death rates by sex, race/ethnicity,
nativity, cause of death, and period together with uncertainty measures
for each rate. The structure of these files is described below. The
remaining files are produced in the project as intermediate steps. The
`figures` folder contains all figures and tables of the project.
Finally, the `R` folder contains all the code used to clean and analyse
the data. This repository does not contain the individual level death
records because they are not publicly available. The public version of
these data, in which information on place of birth has been masked, can
be obtained from the [Vital Statistics Online Data
Portal](https://www.cdc.gov/nchs/data_access/vitalstatsonline.htm#Mortality_Multiple).
They have the same structure as the data we used.

## Content of Main Data Files

The table below details the structure of the `ageStdRates*.csv` files.

<table class="table" style="font-size: 12px; margin-left: auto; margin-right: auto;">
<caption style="font-size: initial !important;">
output/ageStdRates
</caption>
<thead>
<tr>
<th style="text-align:left;">
Name
</th>
<th style="text-align:left;">
Class
</th>
<th style="text-align:left;">
Label
</th>
<th style="text-align:left;">
Values
</th>
<th style="text-align:left;">
Missing
</th>
<th style="text-align:left;">
Summary
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
period
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Years or year for which the mortality measure was computed.
</td>
<td style="text-align:left;">
‘2017-2019’ ‘2020’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
sex
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Sex
</td>
<td style="text-align:left;">
‘Female’ ‘Male’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
raceEthnicity
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Race/Ethnicity
</td>
<td style="text-align:left;">
‘Asian’ ‘Black’ ‘Hispanic’ ‘White’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 4
</td>
</tr>
<tr>
<td style="text-align:left;">
foreign
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Whether the mortality measure was computed for the Foreign-Born or the
US-Born population.
</td>
<td style="text-align:left;">
‘Foreign-Born’ ‘Total’ ‘US-Born’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 3
</td>
</tr>
<tr>
<td style="text-align:left;">
majorCauses
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Group of the underlying cause of death reported on the death
certificates.
</td>
<td style="text-align:left;">
‘All other causes’ ‘Alzheimer disease and other dementias’ ‘Circulatory
diseases’ ‘COVID-19’ ‘Diabetes’ and 4 more
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 9
</td>
</tr>
<tr>
<td style="text-align:left;">
age
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Ages over which the mortality measure was computed, 100 is used as an
upper bound.
</td>
<td style="text-align:left;">
‘25-100’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 1
</td>
</tr>
<tr>
<td style="text-align:left;">
deaths
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Number of deaths.
</td>
<td style="text-align:left;">
Num: 0 to 3275911
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 106751.167, sd: 344136.165, nuniq: 407
</td>
</tr>
<tr>
<td style="text-align:left;">
pop
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Mid-period population.
</td>
<td style="text-align:left;">
Num: 1416388.584 to 224932209
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 37059951.417, sd: 56394352.809, nuniq: 48
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: 0 to 2419.774
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 268.98, sd: 383.012, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
logASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Logarithm of the Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: 3.071 to 7.791
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 5.056, sd: 1.044, nuniq: 408
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR.SD
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Standard deviation of the ASDR computed using the formula in Chiang
(1984) “The Life Table and Its Application” (pp. 105-106).
</td>
<td style="text-align:left;">
Num: 0 to 6.456
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 0.811, sd: 0.825, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
coefOfVar
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Coefficient of variation for the ASDR computed as ASDR.SD/ASDR.
</td>
<td style="text-align:left;">
Num: 0.027 to 3.753
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 0.575, sd: 0.558, nuniq: 408
</td>
</tr>
</tbody>
</table>
<table class="table" style="font-size: 12px; margin-left: auto; margin-right: auto;">
<caption style="font-size: initial !important;">
output/ageStdRatesAbove65
</caption>
<thead>
<tr>
<th style="text-align:left;">
Name
</th>
<th style="text-align:left;">
Class
</th>
<th style="text-align:left;">
Label
</th>
<th style="text-align:left;">
Values
</th>
<th style="text-align:left;">
Missing
</th>
<th style="text-align:left;">
Summary
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
period
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Years or year for which the mortality measure was computed.
</td>
<td style="text-align:left;">
‘2017-2019’ ‘2020’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
sex
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Sex
</td>
<td style="text-align:left;">
‘Female’ ‘Male’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
raceEthnicity
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Race/Ethnicity
</td>
<td style="text-align:left;">
‘Asian’ ‘Black’ ‘Hispanic’ ‘White’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 4
</td>
</tr>
<tr>
<td style="text-align:left;">
foreign
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Whether the mortality measure was computed for the Foreign-Born or the
US-Born population.
</td>
<td style="text-align:left;">
‘Foreign-Born’ ‘Total’ ‘US-Born’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 3
</td>
</tr>
<tr>
<td style="text-align:left;">
majorCauses
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Group of the underlying cause of death reported on the death
certificates.
</td>
<td style="text-align:left;">
‘All other causes’ ‘Alzheimer disease and other dementias’ ‘Circulatory
diseases’ ‘COVID-19’ ‘Diabetes’ and 4 more
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 9
</td>
</tr>
<tr>
<td style="text-align:left;">
age
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Ages over which the mortality measure was computed, 100 is used as an
upper bound.
</td>
<td style="text-align:left;">
‘65-100’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 1
</td>
</tr>
<tr>
<td style="text-align:left;">
deaths
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Number of deaths.
</td>
<td style="text-align:left;">
Num: 0 to 2670630
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 80830.824, sd: 272034.284, nuniq: 405
</td>
</tr>
<tr>
<td style="text-align:left;">
pop
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Mid-period population.
</td>
<td style="text-align:left;">
Num: 158719.795 to 66442571
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 8821142.375, sd: 16086779.765, nuniq: 48
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: 0 to 6786.988
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 853.186, sd: 1194.322, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
logASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Logarithm of the Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: 3.774 to 8.823
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 6.172, sd: 1.112, nuniq: 408
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR.SD
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Standard deviation of the ASDR computed using the formula in Chiang
(1984) “The Life Table and Its Application” (pp. 105-106).
</td>
<td style="text-align:left;">
Num: 0 to 5.182
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 0.677, sd: 0.697, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
coefOfVar
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Coefficient of variation for the ASDR computed as ASDR.SD/ASDR.
</td>
<td style="text-align:left;">
Num: 0.006 to 1.094
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 0.162, sd: 0.17, nuniq: 408
</td>
</tr>
</tbody>
</table>
<table class="table" style="font-size: 12px; margin-left: auto; margin-right: auto;">
<caption style="font-size: initial !important;">
output/ageStdRatesBelow65
</caption>
<thead>
<tr>
<th style="text-align:left;">
Name
</th>
<th style="text-align:left;">
Class
</th>
<th style="text-align:left;">
Label
</th>
<th style="text-align:left;">
Values
</th>
<th style="text-align:left;">
Missing
</th>
<th style="text-align:left;">
Summary
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
period
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Years or year for which the mortality measure was computed.
</td>
<td style="text-align:left;">
‘2017-2019’ ‘2020’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
sex
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Sex
</td>
<td style="text-align:left;">
‘Female’ ‘Male’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
raceEthnicity
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Race/Ethnicity
</td>
<td style="text-align:left;">
‘Asian’ ‘Black’ ‘Hispanic’ ‘White’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 4
</td>
</tr>
<tr>
<td style="text-align:left;">
foreign
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Whether the mortality measure was computed for the Foreign-Born or the
US-Born population.
</td>
<td style="text-align:left;">
‘Foreign-Born’ ‘Total’ ‘US-Born’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 3
</td>
</tr>
<tr>
<td style="text-align:left;">
majorCauses
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Group of the underlying cause of death reported on the death
certificates.
</td>
<td style="text-align:left;">
‘All other causes’ ‘Alzheimer disease and other dementias’ ‘Circulatory
diseases’ ‘COVID-19’ ‘Diabetes’ and 4 more
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 9
</td>
</tr>
<tr>
<td style="text-align:left;">
age
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Ages over which the mortality measure was computed, 100 is used as an
upper bound.
</td>
<td style="text-align:left;">
‘25-65’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 1
</td>
</tr>
<tr>
<td style="text-align:left;">
deaths
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Number of deaths.
</td>
<td style="text-align:left;">
Num: 0 to 850264
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 25920.343, sd: 77380.811, nuniq: 402
</td>
</tr>
<tr>
<td style="text-align:left;">
pop
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Mid-period population.
</td>
<td style="text-align:left;">
Num: 1225192.498 to 158489638
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 28238809.042, sd: 40529995.045, nuniq: 48
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: 0 to 1055.559
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 86.487, sd: 136.983, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
logASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Logarithm of the Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: -0.434 to 6.962
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 3.57, sd: 1.582, nuniq: 408
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR.SD
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Standard deviation of the ASDR computed using the formula in Chiang
(1984) “The Life Table and Its Application” (pp. 105-106).
</td>
<td style="text-align:left;">
Num: 0 to 3.856
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 0.426, sd: 0.46, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
coefOfVar
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Coefficient of variation for the ASDR computed as ASDR.SD/ASDR.
</td>
<td style="text-align:left;">
Num: 0.055 to 17.436
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 1.505, sd: 2.128, nuniq: 408
</td>
</tr>
</tbody>
</table>
<table class="table" style="font-size: 12px; margin-left: auto; margin-right: auto;">
<caption style="font-size: initial !important;">
output/ageStdRatesSens
</caption>
<thead>
<tr>
<th style="text-align:left;">
Name
</th>
<th style="text-align:left;">
Class
</th>
<th style="text-align:left;">
Label
</th>
<th style="text-align:left;">
Values
</th>
<th style="text-align:left;">
Missing
</th>
<th style="text-align:left;">
Summary
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
period
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Years or year for which the mortality measure was computed.
</td>
<td style="text-align:left;">
‘2017-2019’ ‘2020’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
sex
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Sex
</td>
<td style="text-align:left;">
‘Female’ ‘Male’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 2
</td>
</tr>
<tr>
<td style="text-align:left;">
raceEthnicity
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Race/Ethnicity
</td>
<td style="text-align:left;">
‘Asian’ ‘Black’ ‘Hispanic’ ‘White’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 4
</td>
</tr>
<tr>
<td style="text-align:left;">
foreign
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Whether the mortality measure was computed for the Foreign-Born or the
US-Born population.
</td>
<td style="text-align:left;">
‘Foreign-Born’ ‘Total’ ‘US-Born’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 3
</td>
</tr>
<tr>
<td style="text-align:left;">
majorCauses
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Group of the underlying cause of death reported on the death
certificates.
</td>
<td style="text-align:left;">
‘All other causes’ ‘Alzheimer disease and other dementias’ ‘Circulatory
diseases’ ‘COVID-19’ ‘Diabetes’ and 4 more
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 9
</td>
</tr>
<tr>
<td style="text-align:left;">
age
</td>
<td style="text-align:left;">
character
</td>
<td style="text-align:left;">
Ages over which the mortality measure was computed, 100 is used as an
upper bound.
</td>
<td style="text-align:left;">
‘25-100’
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
nuniq: 1
</td>
</tr>
<tr>
<td style="text-align:left;">
deaths
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Number of deaths.
</td>
<td style="text-align:left;">
Num: 0 to 3275911
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 106751.167, sd: 344136.165, nuniq: 407
</td>
</tr>
<tr>
<td style="text-align:left;">
pop
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Mid-period population.
</td>
<td style="text-align:left;">
Num: 1402366.041 to 224932209
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 36992066.792, sd: 56413881.045, nuniq: 48
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: 0 to 2487.108
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 273.558, sd: 389.976, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
logASDR
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Logarithm of the Age-Standardized Crude Death Rate.
</td>
<td style="text-align:left;">
Num: 3.076 to 7.819
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 5.073, sd: 1.044, nuniq: 408
</td>
</tr>
<tr>
<td style="text-align:left;">
ASDR.SD
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Standard deviation of the ASDR computed using the formula in Chiang
(1984) “The Life Table and Its Application” (pp. 105-106).
</td>
<td style="text-align:left;">
Num: 0 to 6.675
</td>
<td style="text-align:left;">
0
</td>
<td style="text-align:left;">
mean: 0.828, sd: 0.849, nuniq: 409
</td>
</tr>
<tr>
<td style="text-align:left;">
coefOfVar
</td>
<td style="text-align:left;">
numeric
</td>
<td style="text-align:left;">
Coefficient of variation for the ASDR computed as ASDR.SD/ASDR.
</td>
<td style="text-align:left;">
Num: 0.027 to 3.741
</td>
<td style="text-align:left;">
24
</td>
<td style="text-align:left;">
mean: 0.575, sd: 0.557, nuniq: 408
</td>
</tr>
</tbody>
</table>

## Description of R Code

Below we briefly describe each of the R files. Ideally, they would be
run in the order in whcih they are listed below.

- `createMortTable.Rmd`: Reads and cleans the death records creating
  death counts.
- `createPopTableCDC.Rmd`: Reads and cleans the population data from
  CDC.
- `createPropTable.Rmd`: Reads and cleans the ACS data to compute
  proportion foreign-born by sex, race, Hispanic origin, age, and year
  to be applied to the CDC population estimates.
- `createFinalTable.Rmd`: Combines the death and population counts in a
  unique cleaned file.
- `sampleAndSummaryTables.Rmd`: Computes age-specific and
  age-standardized rates and creates the sample and summary tables
  (Supplementary Tables 1a, 1b, 3a, and 3b).
- `mortalityDifferentialsPlotsNoRatios.Rmd`: Creates Figure 1 and Figure
  2.
- `compWithWhitesPlots.Rmd`: Creates Figure 3 and the corresponding
  Supplementary Table 4.
- `contributionsPlots.Rmd`: Creates Figure 4a and 4b and the
  corresponding Supplementary Tables 5a and 5b.

As a note to help readers navigate the scripts, we used a functional
approach, defining the functions to create each figure and table at the
start of the file and then running the functions and saving the output
below.
