In [1]:

    import os
    import pandas as pd
    from statsmodels.formula.api  import ols

### Reading the data[¶](https://moodle.technion.ac.il/pluginfile.php/1077687/mod_resource/content/1/Tutorial2-LinearRegression.html#Reading-the-data) {#Reading-the-data}

In [2]:

    df = pd.read_csv('Cirrhosis_death_rate.csv')

In [3]:

    df.columns

Out[3]:

    Index(['population', ' Late_births', ' Wine_consumption',
           ' Liquor_consumption', ' Cirrhosis_death_rate'],
          dtype='object')

In [4]:

    df = df.rename(index=str, columns={' Late_births': 'Late_births',
                                       ' Wine_consumption': 'Wine_consumption',
                                       ' Liquor_consumption':'Liquor_consumption',
                                       ' Cirrhosis_death_rate': 'Cirrhosis_death_rate'})

In [5]:

    df.describe()

Out[5]:

population

Late\_births

Wine\_consumption

Liquor\_consumption

Cirrhosis\_death\_rate

count

46.000000

46.000000

46.000000

46.000000

46.000000

mean

56.260870

41.476087

11.586957

57.500000

63.493478

std

15.747218

7.044342

6.920424

22.140712

23.447979

min

27.000000

31.200000

2.000000

26.000000

28.000000

25%

44.250000

35.625000

6.250000

41.500000

48.900000

50%

55.000000

42.250000

10.000000

56.000000

57.650000

75%

65.000000

45.825000

15.750000

68.750000

75.700000

max

87.000000

56.100000

31.000000

149.000000

129.900000

In [6]:

    df['Cirrhosis_death_rate']

Out[6]:

    0      41.2
    1      31.7
    2      39.4
    3      57.5
    4      74.8
    5      59.8
    6      54.3
    7      47.9
    8      77.2
    9      56.6
    10     80.9
    11     34.3
    12     53.1
    13     55.4
    14     57.8
    15     62.8
    16     67.3
    17     56.7
    18     37.6
    19    129.9
    20     70.3
    21    104.2
    22     83.6
    23     66.0
    24     52.3
    25     86.9
    26     66.6
    27     40.1
    28     55.7
    29     58.1
    30     74.3
    31     98.1
    32     40.7
    33     66.7
    34     48.0
    35    122.5
    36     92.1
    37     76.0
    38     97.5
    39     33.8
    40     90.5
    41     29.7
    42     28.0
    43     51.6
    44     55.7
    45     55.5
    Name: Cirrhosis_death_rate, dtype: float64

In [7]:

    df['Cirrhosis_death_rate'].values.reshape(-1, 1)

Out[7]:

    array([[  41.2],
           [  31.7],
           [  39.4],
           [  57.5],
           [  74.8],
           [  59.8],
           [  54.3],
           [  47.9],
           [  77.2],
           [  56.6],
           [  80.9],
           [  34.3],
           [  53.1],
           [  55.4],
           [  57.8],
           [  62.8],
           [  67.3],
           [  56.7],
           [  37.6],
           [ 129.9],
           [  70.3],
           [ 104.2],
           [  83.6],
           [  66. ],
           [  52.3],
           [  86.9],
           [  66.6],
           [  40.1],
           [  55.7],
           [  58.1],
           [  74.3],
           [  98.1],
           [  40.7],
           [  66.7],
           [  48. ],
           [ 122.5],
           [  92.1],
           [  76. ],
           [  97.5],
           [  33.8],
           [  90.5],
           [  29.7],
           [  28. ],
           [  51.6],
           [  55.7],
           [  55.5]])

In [8]:

    est = ols(formula = ' Cirrhosis_death_rate ~  population', data = df).fit()
    est.summary()

Out[8]:

OLS Regression Results

Dep. Variable:

Cirrhosis\_death\_rate

R-squared:

0.561

Model:

OLS

Adj. R-squared:

0.551

Method:

Least Squares

F-statistic:

56.25

Date:

Sun, 28 Oct 2018

Prob (F-statistic):

2.13e-09

Time:

23:33:10

Log-Likelihood:

-190.94

No. Observations:

46

AIC:

385.9

Df Residuals:

44

BIC:

389.5

Df Model:

1

Covariance Type:

nonrobust

coef

std err

t

P\>|t|

[0.025

0.975]

Intercept

0.7407

8.681

0.085

0.932

-16.756

18.237

population

1.1154

0.149

7.500

0.000

0.816

1.415

Omnibus:

19.664

Durbin-Watson:

2.203

Prob(Omnibus):

0.000

Jarque-Bera (JB):

36.860

Skew:

1.165

Prob(JB):

9.91e-09

Kurtosis:

6.715

Cond. No.

219.

\
\
Warnings:\
[1] Standard Errors assume that the covariance matrix of the errors is
correctly specified.

In [9]:

    est = ols(formula = ' Cirrhosis_death_rate ~  population + Liquor_consumption', data = df).fit()
    est.summary()

Out[9]:

OLS Regression Results

Dep. Variable:

Cirrhosis\_death\_rate

R-squared:

0.715

Model:

OLS

Adj. R-squared:

0.702

Method:

Least Squares

F-statistic:

53.92

Date:

Sun, 28 Oct 2018

Prob (F-statistic):

1.91e-12

Time:

23:33:10

Log-Likelihood:

-181.02

No. Observations:

46

AIC:

368.0

Df Residuals:

43

BIC:

373.5

Df Model:

2

Covariance Type:

nonrobust

coef

std err

t

P\>|t|

[0.025

0.975]

Intercept

-9.7477

7.405

-1.316

0.195

-24.681

5.185

population

0.8290

0.135

6.139

0.000

0.557

1.101

Liquor\_consumption

0.4626

0.096

4.817

0.000

0.269

0.656

Omnibus:

2.442

Durbin-Watson:

2.535

Prob(Omnibus):

0.295

Jarque-Bera (JB):

1.571

Skew:

0.423

Prob(JB):

0.456

Kurtosis:

3.321

Cond. No.

328.

\
\
Warnings:\
[1] Standard Errors assume that the covariance matrix of the errors is
correctly specified.

In [10]:

    est = ols(formula = ' Cirrhosis_death_rate ~ population + Late_births + Wine_consumption + Liquor_consumption',
              data = df).fit()
    est.summary()

Out[10]:

OLS Regression Results

Dep. Variable:

Cirrhosis\_death\_rate

R-squared:

0.814

Model:

OLS

Adj. R-squared:

0.795

Method:

Least Squares

F-statistic:

44.75

Date:

Sun, 28 Oct 2018

Prob (F-statistic):

1.95e-14

Time:

23:33:10

Log-Likelihood:

-171.25

No. Observations:

46

AIC:

352.5

Df Residuals:

41

BIC:

361.6

Df Model:

4

Covariance Type:

nonrobust

coef

std err

t

P\>|t|

[0.025

0.975]

Intercept

-13.9631

11.400

-1.225

0.228

-36.987

9.060

population

0.0983

0.244

0.403

0.689

-0.395

0.591

Late\_births

1.1484

0.583

1.970

0.056

-0.029

2.326

Wine\_consumption

1.8579

0.401

4.634

0.000

1.048

2.668

Liquor\_consumption

0.0482

0.133

0.361

0.720

-0.221

0.317

Omnibus:

3.887

Durbin-Watson:

2.549

Prob(Omnibus):

0.143

Jarque-Bera (JB):

1.988

Skew:

-0.211

Prob(JB):

0.370

Kurtosis:

2.073

Cond. No.

688.

\
\
Warnings:\
[1] Standard Errors assume that the covariance matrix of the errors is
correctly specified.

### Same model with sklearn[¶](https://moodle.technion.ac.il/pluginfile.php/1077687/mod_resource/content/1/Tutorial2-LinearRegression.html#Same-model-with-sklearn) {#Same-model-with-sklearn}

#### Split to train and test[¶](https://moodle.technion.ac.il/pluginfile.php/1077687/mod_resource/content/1/Tutorial2-LinearRegression.html#Split-to-train-and-test) {#Split-to-train-and-test}

In [11]:

    from sklearn.model_selection import train_test_split

In [12]:

    X = df[['population', 'Late_births', 'Wine_consumption', 'Liquor_consumption']]
    y = df[['Cirrhosis_death_rate']]
    X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=100)

#### Train linear regression model with sklearn[¶](https://moodle.technion.ac.il/pluginfile.php/1077687/mod_resource/content/1/Tutorial2-LinearRegression.html#Train-linear-regression-model-with-sklearn) {#Train-linear-regression-model-with-sklearn}

In [13]:

    from sklearn.linear_model import LinearRegression

In [14]:

    lr_model = LinearRegression()
    lr_model.fit(X_train['population'].values.reshape(-1, 1), y_train)

Out[14]:

    LinearRegression(copy_X=True, fit_intercept=True, n_jobs=1, normalize=False)

In [15]:

    y_pred = lr_model.predict(X_test['population'].values.reshape(-1, 1))

In [16]:

    lr_model.score(X_test['population'].values.reshape(-1, 1), y_test)

Out[16]:

    0.63582789566682374

In [17]:

    print('Coefficients: \n', lr_model.coef_)

    Coefficients: 
     [[ 1.04716568]]

In [18]:

    print('Intercept: \n', lr_model.intercept_)

    Intercept: 
     [ 6.67970349]

#### Full model[¶](https://moodle.technion.ac.il/pluginfile.php/1077687/mod_resource/content/1/Tutorial2-LinearRegression.html#Full-model) {#Full-model}

In [19]:

    lr_model_full = LinearRegression()
    lr_model_full.fit(X_train, y_train)

Out[19]:

    LinearRegression(copy_X=True, fit_intercept=True, n_jobs=1, normalize=False)

In [20]:

    y_pred = lr_model_full.predict(X_test)
    lr_model_full.score(X_test, y_test)

Out[20]:

    0.53503624951614825

In [21]:

    print('Coefficients: \n', lr_model_full.coef_)

    Coefficients: 
     [[-0.02001078  1.20986562  2.16892735  0.01454169]]

In [22]:

    print('Intercept: \n', lr_model_full.intercept_)

    Intercept: 
     [-9.11659585]
