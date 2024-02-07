---
layout: page
title: Optimized, Dynamic & Transformative HR Strategy for CanadaRetail
description: Linear Regression/Machine Learning/Random Forest
img: assets/img/ubc_campus/ubc_robson-square.jpg
importance: 1
category: work
related_publications: false
---

<div class="container-fluid mt-3 md-3">

<h2>Executive Summary</h2>

<p>Despite being a key player in the competitive Canadian retail market, CanadaRetail struggles to attract and retain top talent, especially among sales associates, who are vital for revenue generation and customer interaction. High turnover rates and a lack of a strong employer brand are impeding the company's ability to achieve its strategic goals.</p>

<p>The purpose of this project is to devise actionable, evidence-based HR strategies within a limited budget that will strengthen CanadaRetail's employer brand. This will involve enhancing recruitment, selection, training, development, compensation, and performance management practices. The aim is to attract and retain talented sales associates who align with the company's strategic objectives, thereby creating a sustainable competitive advantage.</p>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Key Take-aways</h2>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0001.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0002.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0003.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0004.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0005.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0006.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0007.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0008.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0009.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0010.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
</div>

<div class = "mt-3 md-3">

<h2>Codes</h2>

{% raw %}

```python
# Random Forest 
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report, confusion_matrix
from sklearn.model_selection import train_test_split

# Splitting the data
X_train, X_test, y_train, y_test = train_test_split(predictors, target, test_size=0.3, random_state=42)

# Training the model
model = RandomForestClassifier(random_state=42)
model.fit(X_train, y_train)

# Making predictions and evaluating the model
y_pred = model.predict(X_test)
print(classification_report(y_test, y_pred))
cm = confusion_matrix(y_test, y_pred)

# Visualizing the confusion matrix
sns.heatmap(cm, annot=True, fmt='d', cmap='Blues')
plt.xlabel('Predicted')
plt.ylabel('True')
plt.show()
```

```python
# Linear Regression
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression, Ridge, Lasso
from sklearn.metrics import mean_squared_error, r2_score

# Splitting the dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Training the model
model = LinearRegression()
model.fit(X_train, y_train)

# Making predictions
y_pred = model.predict(X_test)

# Evaluating the model
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)
print(mse, r2)
#0.32300445993148585 0.3747974569505925

# Plotting actual vs predicted values
plt.figure(figsize=(6, 6))
plt.scatter(y_test, y_pred, alpha=0.5)
plt.xlabel('Actual Values')
plt.ylabel('Predicted Values')
plt.title('Actual vs Predicted Values')

# Plotting a reference line for perfect predictions
plt.plot([y_test.min(), y_test.max()], [y_test.min(), y_test.max()], 'k--', lw=2)
plt.show()
```

```python
# OLS: Tenure vs Unitmonth_hrlyrate 

import statsmodels.api as sm

# After removing outliers
X = grouped_data['unitmonth_hrlyrate']
y = grouped_data['tenure']

# Adding a constant to the model (for the intercept)
X = sm.add_constant(X)

# Fitting the model
model = sm.OLS(y, X).fit()
print(model.summary())

# OLS: Voluntary_turnover vs Inequality 

from statsmodels.formula.api import ols

data = store
# Calculate the inequality metric
data['inequality_metric'] = (abs(data['rmgrwhite'] - data['unitmonth_white']) + 
                           abs(data['rmgrfemale'] - data['unitmonth_female']))

# Prepare the data for hypothesis testing
data['inequality_metric'] = pd.qcut(data['inequality_metric'], q=2, labels=['High Equality', 'Low Equality'])

# OLS regression
model = ols('Voluntary_turnover ~ C(inequality_metric)', data=data).fit()
results_summary = model.summary()
print(results_summary)
```

{% endraw %}

</div>

<div class="container-fluid mt-3 md-3">

<h3>Other Team Members</h3>
    <div class="row">
        <div class="col-sm-4">
        <a href = "https://www.linkedin.com/in/qi-li-51b92227a/">Qi Li</a></div>
        <div class="col-sm-4">
        <a href = "https://www.linkedin.com/in/shunyiyao/">Shunyi Yao</a></div>
        <div class="col-sm-4">
        <a href = "https://www.linkedin.com/in/christi-mariam/">Christi Mariam Denny</a></div>
    </div>
</div>