# Introduction

<img src="prophet.png" class="inline" alt="centered image">

•       Prophet is open source software released by Facebook’s Core Data Science team. It is available for download on CRAN and PyPI.

•       Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects.

•       It works best with time series that have strong seasonal effects and several seasons of historical data.

•       Prophet is robust to missing data and shifts in the trend, and typically handles outliers well.



Accurate and fast.
--------------------------

•       Prophet is used in many applications across Facebook for producing reliable forecasts for planning and goal setting. We’ve found it to perform better than any other approach in the majority of cases. We fit models in Stan so that you get forecasts in just a few seconds.


Fully automatic.
--------------------------

•       Get a reasonable forecast on messy data with no manual effort. Prophet is robust to outliers, missing data, and dramatic changes in your time series.


Tunable forecasts.
--------------------------


•      The Prophet procedure includes many possibilities for users to tweak and adjust forecasts. You can use human-interpretable parameters to improve your forecast by adding your domain knowledge.


Available in R or Python.
--------------------------

•      We’ve implemented the Prophet procedure in R and Python, but they share the same underlying Stan code for fitting. Use whatever language you’re comfortable with to get forecasts.



# SUMMARY
-------------------------------------------------------------------------------------------------------------------------------------



•      Forecasting is a data science task that is central to many activities within an organization.For instance, organizations across all sectors of industry must engage in capacity planningto  eciently  allocate  scarce  resources  and  goal  setting  in  order  to  measure  performancerelative to a baseline.

•      We  describe  performance  analysesto compare and evaluate forecasting procedures, and automatically  ag forecasts formanual review and adjustment.  Tools that help analysts to use their expertise moste ectively enable reliable, practical forecasting of business time series.

•      First, completely automatic forecasting techniques can be hardto tune and are often too in exible to incorporate useful assumptions or heuristics.  Second,the analysts responsible for data science tasks throughout an organization typically havedeep domain expertise about the speci c products or services that they support, but oftendo  not  have  training  in  time  series  forecasting

<img src="Untitled1.png" class="inline" alt="centered image">

•      Figure 1: Schematic view of the analyst-in-the-loop approach to forecasting at scale, which
best makes use of human and automated tasks 



Classical time series forecasting techniques
--------------------------------------------

•      1.Classical time series forecasting techniques build on stats models 
which requires lots of effort to tune models and expect in data and 
industry.

•      2. The person has to tune the parameters of the method with regards 
to the specific problem when a forecasting model doesn’t perform 
as expected.

•      3. the underlying time series models work. It’s difficult for some 
organizations to handling those forecasting without data science 
teams.



Highlights of Facebook Prophet
--------------------------------------------

•      Very fast, since it’s built in Stan, a programming language for statistical 
inference written in C++

•      An additive regression model where non-linear trends are fit with 
yearly, weekly, and daily seasonality, 
•      plus, holiday effects: 1. A piecewise linear or logistic growth curve 
trend. Prophet automatically detects changes in trends by selecting 
changepoints 
•      from the data 2. A yearly seasonal component modeled using 
•      Fourier series 3. A weekly seasonal component using dummy 
variables 4. A user-provided list of important holidays.
• Robust to missing data and shifts in the trend, and typically handles 
outliers.
•      Easy procedure to tweak and adjust forecast while adding domain 
knowledge or business insights.




The Prophet Forecasting Model
--------------------------------------------

The Prophet uses a decomposable time series model with three main 
model components: trend, seasonality, and holidays. They are combined 
in the following equation:

•      y(t)= g(t) + s(t) + h(t) + εt

•      g(t): piecewise linear or logistic growth curve for modeling nonperiodic changes in time series
•      s(t): periodic changes (e.g., weekly/yearly seasonality)
•      h(t): effects of holidays (user provided) with irregular schedules
•      εt: error term accounts for any unusual changes not accommodated 
by the model
•      Using time as a regressor, Prophet is trying to fit several linear and 
nonlinear functions of time as components.



Saturating growth
--------------------------------------------

•      Set a carrying capacity captor specify the maximum achievable point 
due to the business scenarios or constraints: market size, total 
population size, maximum budget, etc.

•      A saturating minimum, which is specified with a column floor in the 
same way as the cap column specifies the maximum


Trend Changepoints
--------------------------------------------

•      The model could be overfitting or underfitting while working with 
the trend component. The input of changepoints built in Prophet 
allowed is increased the fit becomes more flexible.


Seasonality, Holiday Effects, And Regressors
--------------------------------------------
Seasonal effects s(t) is approximated by the following function:
------------------------------------------------------------------












