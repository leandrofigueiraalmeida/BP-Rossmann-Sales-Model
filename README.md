# BP-Rossmann-Sales-Model
This is a sales prediction machine learning project
![sales-prediction-social-media](https://user-images.githubusercontent.com/85244180/135611366-dbfb5c66-91fc-4922-ba8e-836b1703b284.png)
# Business problem
The CFO of Rossmann Drug Stores requested a sales predction for each store for the next six weeks in order to define a budget for stores renovation. The current prediction was not satisfactory as there were several inconsistencies. In this context, I developed a machine learning model in order to provide more accurately forecast store sales.
# Business Assumptions
- The days when stores were closed were removed from the analysis.
- Only stores with sales values bigger than 0 were considered.
- For stores which did not have Competition Distance information, it was considered that the distance should be two times bigger than the bigger distance from the nearest competitor.
# Attribute List
- Id - an Id that represents a (Store, Date) duple within the test set
- Store - a unique Id for each store
- Sales - the turnover for any given day (this is what you are predicting)
- Customers - the number of customers on a given day
- Open - an indicator for whether the store was open: 0 = closed, 1 = open
- StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
- SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools
- StoreType - differentiates between 4 different store models: a, b, c, d
- Assortment - describes an assortment level: a = basic, b = extra, c = extended
- CompetitionDistance - distance in meters to the nearest competitor store
- CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened
- Promo - indicates whether a store is running a promo on that day
- Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating
- Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2
- PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store
# Solution Strategy
The method used for the project was CRISP-DM, apply as the steps below:

**Step 01**. **Data Description:** The goal is to use statistical metrics to identify outliers in the business scope and also analyze basic statistical metrics such as: mean, median, maximum, minimum, range, skew, curtosis and standard deviation.

**Step 02**. **Feature Engineering**: The goal of this step is to obtain new attributes based on the original variables, in order to better describe the phenomenon to be modeled.

**Step 03**. **Data Filtering**: The goal of this step it to filter rows and delete columns that are not relevant for the model or are not part of the business scope.

**Step 04**. **Exploratory Data Analysis**: The goal of this step is to explore the data to find insights and better understand the impact of variables on model learning.

**Step 05**. **Data Preparation**: The goal of this step is to prepare the data prepare data for application of the machine learning model.  

**Step 06**. **Feature Selection**: The goal of this step is to select the better attributes to train the model. It was used Boruta Algorithm to make the selection.

**Step 07**. **Machine Learning Modeling**: The goal of this step is to do the machine learning model training.

**Step 08**. **Hyperparameter Fine Tunning**: The goal of this step is to choose the best values for each of the parameters of the model selected in the previous step.

**Step 09**. **Convert model performance to business values**:  The goal of this step is to convert model performance to a business result.

**Step 10**. **Deploy Model to Production**: The goal of this step is to publish the model in a cloud environment so that other people or services can use the results to improve the business decision. The cloud application platform choosed was Heroku.

**Step 11**. **Telegram Bot**: The goal of this step is to create a bot on the telegram app, that make possible to consult the forecast at any time.

# Top Three Data Insigths
**H1**: Lojas com maior sortimentos deveriam vender mais

**FALSA**: Lojas com maior sortimento vendem MENOS.

![image](https://user-images.githubusercontent.com/85244180/135637281-5f0d6160-e245-49e8-8f3d-f1dbccba12ea.png)

**H9**: Lojas deveriam vender mais ao longo dos anos.

**FALSA**: Lojas vendem menos ao longo dos anos.

![image](https://user-images.githubusercontent.com/85244180/135638046-9dd85666-fa4e-4b6f-8caa-7549a5903de3.png)

 **H11**: Lojas deveriam vender mais depois do dia 10 de cada mês.
 
**VERDADEIRA**: Lojas vendem mais depois do dia 10 de cada mes.

![image](https://user-images.githubusercontent.com/85244180/135639149-69db891d-ba66-465f-b732-54f58909d312.png)

# Tested Machine Learning Models 

- Average Model
- Linear Regression Model
-  Linear Regression Regularized Model (Lasso)
-  Random Forest Regressor
-  XGBoost Regressor

# Machine Learning Models Performance

![image](https://user-images.githubusercontent.com/85244180/135642546-f625a607-a1c8-45bd-b4f5-b2432fff6915.png)


