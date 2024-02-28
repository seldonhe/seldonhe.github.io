---
layout: page
title: Strategic Energy Management:Forecasting for Sustainability at Vancouver Airport
description: Time Series Analysis/Linear Regression
img: assets/img/ubc_campus/ubc_okanagan-aerial-1.jpg
importance: 5
category: work
related_publications: false
---

<div class="container-fluid mt-3 md-3">

<h2>Executive Summary</h2>

<p>The project's goal is to precisely forecast energy consumption at Vancouver Airport (YVR) to enhance energy efficiency, reduce costs, and support environmental sustainability. Through precise energy demand forecasts, YVR can refine energy management, minimize its carbon footprint, and meet global sustainability objectives—critical in the aviation industry's shift towards greener practices.</p>

<p>
Our analytical approach integrates Exponential Smoothing State Space (ETS) and Autoregressive Integrated Moving Average (ARIMA) models, leveraging historical energy usage data, airport area, passenger traffic, and temperature. Initial assessments involved basic forecasting methods, followed by fine-tuning ETS and ARIMA models using criteria such as AIC, BIC, and MAPE.</p>

<p>
Comparative analysis of ETS and ARIMA models led to the selection of the most accurate model for forecasting YVR's energy usage. This model is a key instrument in guiding YVR's strategic initiatives, budgeting, and environmental programs.</p>

<p>
The outcome of this analysis provides Vancouver Airport with the predictive insights required for effective energy management and reinforces its commitment to efficiency and sustainability.</p>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Forecasts</h2>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0008.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

{% raw %}

```r

energy.maa.forecast <- forecast(ets(energy.ts, model=energy.maa, use.initial.values=TRUE), h=36)
energy.maa.forecast

plot(energy.maa.forecast, main="YVR Energy Use with Forecasts from ETS(M,A,A)", ylab = "Energy Use (thousand kWh)", xlab = "Year", xlim=c(1997, 2014), ylim=c(4800, 10800))

legend("topleft", legend= c("Actual", "Forecasts"),
       col=c("black", "blue"), lty=c(1, 1), bty="n")

```
{% endraw %}

<p>The model predicts a continuation of the increasing trend in energy use at YVR. The seasonal pattern is also expected to continue, which is consistent with typical energy use patterns influenced by heating and cooling needs related to passenger numbers. The prediction intervals suggest that while the model is fairly confident in the near term (narrower intervals), the level of certainty decreases as we move further out (wider intervals).</p>

<h2>Impacts</h2>

1. **Data-Driven Decision Making**: The use of historical consumption data, passenger traffic, and temperature allows YVR to make informed decisions based on past patterns and predictable seasonal variations. This data-driven approach can lead to more effective scheduling of energy-intensive operations and better planning for energy procurement.<br>
2. **Cost Efficiency**: Accurate forecasts enable YVR to negotiate better energy contracts, avoid peak tariffs, and potentially invest in energy futures, leading to significant cost savings.<br>
3. **Operational Optimization**: By predicting energy needs, YVR can optimize the operation of HVAC systems, lighting, and other energy-dependent facilities, ensuring they are used only when needed and at optimal levels, reducing both waste and operating costs.<br>
4. **Sustainability Planning**: Insights from the energy forecasts can inform long-term sustainability initiatives, such as investments in renewable energy sources, energy storage systems, and retrofitting projects to improve efficiency.<br>
5. **Regulatory Compliance and Reporting**: The ability to forecast energy consumption helps YVR in complying with environmental regulations, participating in carbon markets, and fulfilling reporting requirements for greenhouse gas emissions.<br>
6. **Public Engagement and Transparency**: Sharing insights from the forecasting project can enhance public trust and corporate reputation, demonstrating YVR's commitment to sustainability.<br>


<div class = "mt-3 md-3">
<h2>Models and Codes</h2>
</div>

<h3>STL Decomposition</h3>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0001.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="caption">
    Plot of the electricity use data
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0002.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="caption">
    STL decomposition plot
    </div>
</div>

<h3>Linear Model</h3>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0003.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0004.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    The linear model indicates that the `total area` of all terminals and the `total number of passengers` are significant predictors of energy use at the airport.
</div>

{% raw %}

```r
# Data Exploration
pairs(~ energy + mean.temp + total.area + total.passengers, data = data)

# Linear Model
energy.lm <- lm(energy ~ mean.temp + total.area + total.passengers, 
            data = data)
summary(energy.lm)

# Diagnostic plot
par(mfrow=c(2,2))
plot(energy.lm)

plot(data$energy, type='l', col='blue'
    , main = "Actual vs. Predicted Values of YVR Energy Use"
    , ylab = "Energy use (thousand kWh)")
lines(fitted(energy.lm), type='l', col='red')
```
{% endraw %}


<h3>Exponential Smoothing (ETS) Model</h3>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0005.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0006.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


{% raw %}

```r
# ETS(M,A,A)
energy.maa <- ets(energy.ts.train, model='MAA', damped=FALSE)
summary(energy.maa)

plot(forecast_maa, main="YVR Energy Use with Forecasts from ETS(M,A,A)", ylab = "Energy Use (thousand kWh)", xlab = "Year")
lines(fitted(energy.maa), col="blue")
lines(energy.ts.test)

legend("topleft", legend= c("Actual data", "ETS fitted/forcast"),
       col= c("black", "blue"), lty=c(1, 1), bty="n")

# Accuracy measures
accuracy(forecast(energy.maa, h=36), energy.ts.test)[,c(2,3,5,6)]

# Residual diagnostics
mean.res <- mean(residuals(energy.maa), na.rm = TRUE); mean.res
checkresiduals(energy.maa)
```
{% endraw %}


<h3>ARIMA Model</h3>

{% raw %}

```r
# ARIMA(1,1,0)(0,1,1)[12]
energy.arima <- Arima(energy.ts.train, order=c(1, 1, 0), seasonal = c(0, 1, 1))
summary(energy.arima)

options(repr.plot.width=18, repr.plot.height=5)
par(mfrow=c(1,3))

plot(diff(diff(energy.ts.train, 12))) 
Acf(diff(diff(energy.ts.train, 12)), lag.max=36)
Pacf(diff(diff(energy.ts.train, 12)), lag.max=36)

plot(forecast(energy.arima, h=36), main="YVR Energy Use with Forecasts from ARIMA", ylab = "Energy Use (thousand kWh)", xlab = "Year")
lines(fitted(energy.arima), col="blue")
lines(energy.ts.test)

legend("topleft", legend= c("Actual data", "ARIMA fitted/forcast"),
       col= c("black", "blue"), lty=c(1, 1), bty="n")

# Accuracy measures
accuracy(forecast(energy.arima, h=36), energy.ts.test)[,c(2,3,5,6)]

# Residual diagnostics
mean.res <- mean(residuals(energy.arima), na.rm = TRUE); mean.res
checkresiduals(energy.arima)
```
{% endraw %}


<h3>Model Comparison</h3>

<p>
The plot shows the actual recorded energy use (black line) and the forecasts from different methods. The ETS and ARIMA models (purple and green lines) are closely tracking the actual energy use, particularly towards the latter years, while the basic methods (dotted lines) deviate significantly from the actual use.
</p>

<p>
Our best forecasting method is the `ETS(M,A,A)` model, which has the lowest RMSE, MAE, MAPE, and MASE values fortesting set, albeit by a small margin compared to the ARIMA(1,1,0)(0,1,1)[12] model. This suggests that the ETS model has the best overall forecasting performance among the models considered. The errors are lower, and the model is more effective at capturing the seasonality and trend in the data.
</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BABS502/0007.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

{% raw %}

```r
options(repr.plot.width=18, repr.plot.height=9)
c_palette <- brewer.pal(5, "Dark2")
colors <- append(c("black", "purple"), c_palette)
methods = c("Actual", "ETS", "ARIMA", "Mean", "Drift", "Naive", "Seasonal naive")

plot(energy.ts.train, main="YVR Energy with Different Forecasts", ylab = "Energy Use (thousand kWh)", xlab = "Year", xlim=c(1997, 2011), ylim=c(4800, 8800))
lines(energy.ts.test, col = colors[1])
lines(forecast(energy.arima, h=36)$mean, col = colors[2])
lines(forecast(energy.maa, h=36)$mean, col = colors[3])
lines(energy.mean$mean,col= colors[4], lty = 2)
lines(energy.drift$mean,col= colors[5], lty = 2)
lines(energy.naive$mean,col= colors[6], lty = 2) 
lines(energy.snaive$mean,col= colors[7], lty = 2)

legend("topleft", legend= methods,
       col=colors, lty=c(1, 1, 1, 2, 2, 2, 2), bty="n")
```
{% endraw %}


<div class="container-fluid mt-3 md-3">

<h2>Other Team Member</h2>
    <div class="row">
        <a href = "https://www.linkedin.com/in/wendyxu09/">Wendy Xu</a>
    </div>
</div>