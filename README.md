# Python project
The main aim of the project is to provide a simple vector autoregression (VAR) model producing forecasts for key Czech macroeconomic variables, which can then be compared with the official forecasts of the Czech National Bank (CNB). The data used are fetched from the CNB's ARAD database. Hence, the project can be seen as a little methodological experiment trying to find out to what extent would "amateur" forecasts derived via a basic VAR model differ from the professional ones based on the same data. Additionally, various customisable visualisations of both the historical data and the projections are presented.

In order to replicate the code, one must generate their own CNB ARAD API key. This can be done for free by creating an account in CNB ARAD (https://www.cnb.cz/arad/#/en/home), and there the user can generate their own API key.

## Summary of the sections
The project is divided into 5 principal sections, each covering one larger stage in the process eventually leading to the VAR forecasts and their comparison with the ones from the CNB.

In the first section "Download DATA", we download the data from the CNB Arad database. Right afterward, in the "Processing the data" section, we adjust the downloaded data so that a Pandas dataframe well usable for further parts of the project is created. We also present the descriptive statistics for the resulting dataframe.

In the "Visualisation" section, all the time series we have in our dataframe are shown graphically. There are two figures - one with the data as indexes and one with the growth rates of variables. In both cases, the graphs are customisable - it is possible to select which variables should be displayed. The graphs can also be zoomed in to display a particular subset period.

The "Preparing the VAR model" part essentially covers the VAR modelling we do before getting to forecasting. In our VAR model, we standardly include inflation, the interest rate (PRIBOR), the exchange rate (against the euro), and either GDP or the variable concerned with industry. The option to choose between the last two mentioned variables is facilitated through a button, which then creates corresponding objects to be used in the modelling. We examine stationarity using Augmented Dickey-Fuller tests and suggestions on the lag order based on different information criteria. In both cases, tables summarising the results are generated. Although not a primary aim of the project, we also present and comment on the impulse response functions (IRFs) of our model.

The last section "Forecasting" then finally presents our forecasts. After getting the forecasts from our VAR model, we download the official ones from the CNB and compare them graphically. Just as the graphs where the series are visualised, the comparison figures can be adjusted by the user. The differences between the forecasts of our simple VAR model built on the CNB data and the actual CNB forecasts are mostly rather stark.  
