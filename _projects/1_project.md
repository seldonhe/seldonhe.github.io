---
layout: page
title: CanadaRetail Workforce Strategy and Talent Analytics
description: People Analytics / Workforce Strategy / Regression / Random Forest
img: assets/img/project_img/BA550/card.png
importance: 4
category: work
related_publications: false
---

<div class="container-fluid mt-3 md-3">

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0006.jpg" class="img-fluid rounded z-depth-1" alt="Talent selection modeling workflow from data preparation and feature selection through evaluation, prediction, and business insight" caption="The project combined workforce strategy with an interpretable talent-selection modeling workflow." %}
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Project Overview</h2>

<p>CanadaRetail was a case-based academic project focused on a fictional Canadian retailer facing high employee turnover, an inconsistent talent pipeline, and limited resources for strengthening its employer brand.</p>

<p>Our team combined people analytics with workforce strategy to examine compensation, tenure, representation, employee development, skill gaps, recruitment, and labor efficiency. The goal was not simply to predict employee outcomes, but to translate evidence into a practical and responsible talent strategy.</p>

<div class="row text-center mt-4">
    <div class="col-md-4 mb-3">
        <h3>85%</h3>
        <p>Random Forest test accuracy</p>
    </div>
    <div class="col-md-4 mb-3">
        <h3>0.375</h3>
        <p>Linear model R-squared</p>
    </div>
    <div class="col-md-4 mb-3">
        <h3>4 pillars</h3>
        <p>Pay, equity, development, and selection</p>
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Analytical Approach</h2>

<h4>Workforce Diagnosis</h4>
<p>We compared turnover, tenure, compensation, employee attitudes, training status, representation, skills, and store-level outcomes to identify where the employee experience and business needs diverged.</p>

<h4>Statistical Analysis</h4>
<p>Correlation and regression methods tested relationships such as hourly pay and tenure, as well as representation gaps and voluntary turnover. Results were treated as evidence for further investigation rather than proof of causation.</p>

<h4>Talent Selection Modeling</h4>
<p>We prepared candidate and performance features, reviewed multicollinearity and fairness considerations, split training and test data, and compared linear regression with a Random Forest classifier.</p>

<h4>Strategy Translation</h4>
<p>Findings were converted into actions across compensation, promotion, training, mentorship, recruitment, and performance management, with attention to budget constraints and implementation practicality.</p>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Compensation and Retention</h2>

<p>The store-level analysis found a modest positive relationship between average hourly pay and tenure. Compensation alone did not explain retention, but the pattern supported market benchmarking and a broader review of benefits, recognition, wellness, and progression opportunities.</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0001.jpg" class="img-fluid rounded z-depth-1" alt="Correlation matrix and scatterplot examining hourly pay, turnover, hiring, and employee tenure" caption="Compensation showed a modest relationship with tenure, reinforcing the need for a total-rewards rather than pay-only response." %}
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Equity and Advancement</h2>

<p>The analysis identified persistent gaps between employee and managerial representation. A regression test also found an association between the constructed representation-gap measure and voluntary turnover in the case data.</p>

<p>We recommended transparent promotion criteria, consistent evaluation processes, bias-aware decision training, representation targets, and regular progress reporting. These controls are also important when predictive models are used in selection: protected characteristics and proxy variables require careful governance.</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0002.jpg" class="img-fluid rounded z-depth-1" alt="Managerial representation trends and regression results comparing workforce and management demographics" caption="Representation analysis connected advancement equity with transparent promotion and evaluation practices." %}
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Skills and Development</h2>

<p>Top performers scored higher across several customer-facing capabilities, including persuasion, sales, cognitive ability, and communication. Rather than using this result only as a hiring filter, we recommended targeted training and a peer-mentorship program that could transfer skills internally and create leadership opportunities.</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project_img/BA550/0005.jpg" class="img-fluid rounded z-depth-1" alt="Comparison of skill levels between top performers and other employees across five capabilities" caption="Skill-gap analysis informed focused development and mentorship recommendations." %}
    </div>
</div>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Recommendations</h2>

<p>1. <b>Benchmark total rewards.</b> Review pay and benefits together, prioritizing roles and stores with the greatest retention pressure.</p>
<p>2. <b>Make advancement transparent.</b> Standardize promotion criteria, evaluation documentation, and representation monitoring.</p>
<p>3. <b>Develop critical skills.</b> Pair role-specific sales and communication training with an ongoing peer-mentorship program.</p>
<p>4. <b>Use models as decision support.</b> Keep human review, fairness testing, and periodic validation around any candidate-scoring workflow.</p>
<p>5. <b>Measure implementation.</b> Track retention, internal mobility, training participation, representation, model performance, and adverse impact over time.</p>

</div>

<div class="container-fluid mt-3 md-3">

<h2>Model Interpretation and Limitations</h2>

<p>The Random Forest classifier reached approximately 85% accuracy on the project test split, while the linear model explained about 37.5% of the observed performance variation. These results are academic proof-of-concept measures, not evidence that either model is ready for production hiring decisions.</p>

<p>The case data may contain historical bias, class imbalance, omitted variables, and store-level dependencies. Accuracy alone is insufficient for a high-impact employment use case; subgroup performance, adverse impact, explainability, privacy, legal review, and ongoing monitoring would all be required before deployment.</p>

<h3>Team</h3>
<p>This project was completed with <a href="https://www.linkedin.com/in/qi-li-51b92227a/" target="_blank" rel="noopener noreferrer">Qi Li</a>, <a href="https://www.linkedin.com/in/shunyiyao/" target="_blank" rel="noopener noreferrer">Shunyi Yao</a>, and <a href="https://www.linkedin.com/in/christi-mariam/" target="_blank" rel="noopener noreferrer">Christi Mariam Denny</a>.</p>

</div>
