---
layout: page
title: NYPD Collision Analysis - Google Hackathon
description: Public-Safety Analytics / BigQuery / Looker Studio / Time-Series Forecasting
img: assets/img/project_img/Hackathon/card.png
importance: 3
category: work
related_publications: false
---

<div class="container-fluid mt-3 md-3">

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/Hackathon/0001.png" class="img-fluid rounded z-depth-1" alt="Overview of the NYC collision dashboard with collision, injury, map, vehicle, cause, and borough analyses" caption="The dashboard connected citywide trends, contributing factors, vehicle types, locations, and outcomes in one decision-support view." %}
    </div>
</div>

<div class="mt-4">
    <a class="btn btn-primary" href="https://data.cityofnewyork.us/widgets/h9gi-nx95" target="_blank" rel="noopener noreferrer">Explore the official dataset</a>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Project Overview</h2>

<p>This team project was developed for a Google hackathon using the New York City Motor Vehicle Collisions dataset. We asked a public-safety question: <b>How can the NYPD and city stakeholders use collision data to reduce harm and target interventions more effectively?</b></p>

<p>We used BigQuery for data preparation and aggregation, Looker Studio for interactive analysis, geospatial views for hotspot identification, and time-series methods for near-term injury forecasting. The result was a five-part analytical experience covering overview, seasonality, vehicles and contributing factors, geography, and prediction.</p>

<div class="row text-center mt-4">
    <div class="col-md-4 mb-3">
        <h3>2.07M</h3>
        <p>Collision records in the dashboard snapshot</p>
    </div>
    <div class="col-md-4 mb-3">
        <h3>630K+</h3>
        <p>Recorded injuries analyzed</p>
    </div>
    <div class="col-md-4 mb-3">
        <h3>5 views</h3>
        <p>From patterns to intervention planning</p>
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Analytical Approach</h2>

<h4>Data Preparation</h4>
<p>We structured collision records in BigQuery, standardized time and location fields, grouped vehicle and contributing-factor categories, and created measures for collisions, injuries, and fatalities.</p>

<h4>Descriptive and Seasonal Analysis</h4>
<p>The dashboard compared long-term and recurring patterns by year, quarter, month, weekday, and hour. Filters let users move from a citywide view to specific causes, vehicles, boroughs, and periods.</p>

<h4>Geospatial Analysis</h4>
<p>Borough, street, and heat-map views highlighted concentrations that could support localized enforcement, public education, street-design review, and emergency-response planning.</p>

<h4>Predictive Analysis</h4>
<p>An ARIMA workflow explored short-term injury forecasts, while a weekday-by-hour matrix translated temporal patterns into operationally useful windows.</p>

</div>

<div class="container-fluid mt-3 md-3">

<h2>From Patterns to Action</h2>

<p><b>Prioritize high-risk locations.</b> Collision heat maps and street rankings can help agencies focus limited enforcement, engineering, and outreach resources.</p>

<p><b>Target driver behavior.</b> Driver skill, experience, and attention appeared prominently among recorded contributing factors, supporting focused public-safety messaging.</p>

<p><b>Protect vulnerable road users.</b> The outcome analysis showed that pedestrians and cyclists carried a disproportionate share of severe consequences relative to their collision volume.</p>

<p><b>Plan around peak periods.</b> Seasonal and hourly patterns can inform campaign timing, staffing, and emergency-response readiness.</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/Hackathon/0004.png" class="img-fluid rounded z-depth-1" alt="Geographic collision analysis with borough shares, street rankings, casualty rates, and a Bronx heat map" caption="Geographic analysis connected borough and street-level patterns with injury and fatality outcomes." %}
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Forecasting and Operational Planning</h2>

<p>The forecasting view paired an ARIMA injury forecast with a weekday-by-hour matrix. This was designed as a planning aid rather than a deterministic prediction: agencies could compare expected ranges, identify recurring high-volume periods, and test whether staffing or public campaigns aligned with observed risk patterns.</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/Hackathon/0005.png" class="img-fluid rounded z-depth-1" alt="ARIMA injury forecast and weekday-by-hour injury matrix for New York City collisions" caption="The predictive view made forecast uncertainty visible and paired it with a practical time-of-day planning matrix." %}
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Limitations</h2>

<p>The dashboard reflects the team dataset snapshot covering July 2012 through early 2024; totals should not be interpreted as current live counts. Collision records may contain missing, delayed, or inconsistently categorized fields, and contributing factors document reported associations rather than causal proof.</p>

<p>The original interactive Looker Studio report is no longer publicly accessible, so this portfolio page uses static views from the completed project. Forecasts are exploratory and should be validated against holdout data, operational context, and updated records before informing deployment decisions.</p>

<h3>Team</h3>
<p>This project was completed with <a href="https://www.linkedin.com/in/tsz-huen-bai-beth/" target="_blank" rel="noopener noreferrer">Beth Bai</a>, <a href="https://www.linkedin.com/in/ruochenshen/" target="_blank" rel="noopener noreferrer">Ruochen Shen</a>, and <a href="https://www.linkedin.com/in/yizhouliang/" target="_blank" rel="noopener noreferrer">Petra Liang</a>.</p>

</div>
