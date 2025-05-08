<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
  <h1 align="center">📊 Ad Bidding Model Evaluation at Criteo</h1>

  <h2>🛠 Technology Stack</h2>
  <div class="badges">
    <img src="https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python"/>
    <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
    <img src="https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-Learn"/>
    <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow"/>
    <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white" alt="Matplotlib"/>
    <img src="https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Seaborn"/>
    <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white" alt="SciPy"/>
  </div>

  <h2>🚀 <strong>Objective</strong></h2>
  <p>
    This project evaluates bidding optimization strategies for programmatic advertising at Criteo, comparing two model-based approaches — Linear Regression and Deep Learning — using a real-world-style Click-Through Rate (CTR) prediction dataset. It simulates a scenario where two brands, Hollister and Fridge, bid for 1,000 ad slots on CNN.com, aiming to maximize profitability, prediction accuracy, and business impact. The goal is to recommend the most effective bidding strategy for deployment in Criteo’s production environment.
  </p>

  <h2>📂 <strong>Project Summary</strong></h2>
  <p>
    The project implements an end-to-end data science workflow to compare Linear Regression and Deep Learning models for bidding optimization. It includes:
  </p>
  <ul>
    <li><strong>Data preprocessing</strong> and feature engineering for robust model inputs</li>
    <li><strong>Model development</strong> with Linear Regression (baseline) and Deep Learning (neural network)</li>
    <li><strong>Bidding simulation</strong> using predicted CTRs with revenue and cost assumptions</li>
    <li><strong>Simulated A/B testing</strong> to compare profit distributions</li>
    <li><strong>Comprehensive evaluation</strong> using metrics like Accuracy, F1 Score, AUC, and Profit</li>
  </ul>

  <h2>🛠️ <strong>Technology Stack</strong></h2>
  <table>
    <thead>
      <tr>
        <th>Technology</th>
        <th>Purpose</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Python 3.8+</strong></td>
        <td>Core programming language</td>
      </tr>
      <tr>
        <td><strong>Pandas</strong></td>
        <td>Data manipulation and preprocessing</td>
      </tr>
      <tr>
        <td><strong>Scikit-Learn</strong></td>
        <td>Linear Regression, preprocessing, and evaluation metrics</td>
      </tr>
      <tr>
        <td><strong>TensorFlow</strong></td>
        <td>Deep Learning model development</td>
      </tr>
      <tr>
        <td><strong>Matplotlib</strong></td>
        <td>Visualization of results</td>
      </tr>
      <tr>
        <td><strong>Seaborn</strong></td>
        <td>Enhanced visualizations (e.g., heatmaps, KDE plots)</td>
      </tr>
      <tr>
        <td><strong>SciPy</strong></td>
        <td>Statistical testing for A/B testing</td>
      </tr>
    </tbody>
  </table>

  <h2>📸 <strong>Screenshots</strong></h2>
  <p>
    Below are visualizations showcasing key results from the analysis.
  </p>

  <p><strong>Profit Distribution by Model</strong>: KDE plot comparing per-sample profit distributions.<br>
    <img src="https://i.imgur.com/zZuIXFZ.png" alt="Profit Distribution" width="600"/>
  </p>

  <p><strong>Model Performance Comparison</strong>: Bar plot of Accuracy, F1 Score, Precision, Recall, and AUC.<br>
    <img src="https://i.imgur.com/bzQATVv.png" alt="Model Performance" width="600"/>
  </p>

  <p><strong>Training vs. Validation Accuracy</strong>: Plot of Deep Learning model accuracy over epochs.<br>
    <img src="https://i.imgur.com/reMFZjr.png" alt="Accuracy Over Epochs" width="600"/>
  </p>

  <h2>📈 <strong>Methodology</strong></h2>

  <h3>Data Processing Pipeline</h3>
  <ol>
    <li><strong>Data Loading</strong>: Loads <code>pcb_dataset_final.tsv</code> with 16.5M impressions</li>
    <li><strong>Cleaning</strong>: Handles invalid values (e.g., <code>-1</code> replaced with NaN) and creates <code>is_first_click</code> flag</li>
    <li><strong>Sampling</strong>: Stratified sampling of 1M impressions by <code>click</code> for class balance</li>
    <li><strong>Feature Engineering</strong>: Applies frequency encoding (<code>cat2</code>, <code>cat3</code>, <code>cat7</code>) and one-hot encoding (<code>cat1</code>, <code>cat4</code>, <code>cat5</code>, <code>cat6</code>, <code>cat8</code>, <code>cat9</code>)</li>
    <li><strong>Data Splitting</strong>: 70% Train, 10% Validation, 20% Test</li>
    <li><strong>Preprocessing</strong>: Standardizes numeric features and imputes missing values</li>
  </ol>

  <h3>Model Architecture</h3>
  <ul>
    <li>
      <strong>Linear Regression</strong>:
      <ul>
        <li>Baseline model for CTR prediction</li>
        <li>Pipeline with preprocessing (imputation, scaling, encoding)</li>
      </ul>
    </li>
    <li>
      <strong>Deep Learning</strong>:
      <ul>
        <li>Neural network with 128 and 64-unit dense layers</li>
        <li>Batch normalization, dropout (0.3), and sigmoid activation</li>
        <li>Trained with Adam optimizer, binary cross-entropy loss</li>
        <li>Callbacks: Early stopping, learning rate reduction</li>
      </ul>
    </li>
  </ul>

  <h2>🔍 <strong>Implementation Details</strong></h2>

  <h3>Bidding Simulation</h3>
  <pre><code>Data → Preprocessing → Model Prediction → Bid Calculation (base_bid × predicted_CTR) → Profit Evaluation</code></pre>

  <p>Bids are simulated as follows:</p>
  <ol>
    <li>Predict CTR using Linear Regression or Deep Learning model</li>
    <li>Calculate bid: <code>base_bid ($1.00) × predicted_CTR</code></li>
    <li>Evaluate profit: <code>(conversions × $1.00) - (bids × $0.05)</code></li>
    <li>Optimize thresholds to maximize F1 Score</li>
  </ol>

  <h3>A/B Testing</h3>
  <table>
    <thead>
      <tr>
        <th>Test</th>
        <th>Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Shapiro-Wilk</td>
        <td>Checks normality of profit distributions (rejected)</td>
      </tr>
      <tr>
        <td>Mann-Whitney U</td>
        <td>Non-parametric test for significant profit differences (p < 0.0001)</td>
      </tr>
    </tbody>
  </table>

  <h3>Evaluation Metrics</h3>
  <ul>
    <li><strong>Classification</strong>: Accuracy, F1 Score, Precision, Recall, AUC</li>
    <li><strong>Regression</strong>: R², Mean Squared Error, Mean Absolute Error</li>
    <li><strong>Business</strong>: Estimated Profit ($)</li>
  </ul>

  <h2>📊 <strong>Key Features</strong></h2>
  <ul>
    <li><strong>Dual Models</strong>: Linear Regression for simplicity, Deep Learning for predictive power</li>
    <li><strong>Robust Preprocessing</strong>: Handles high-cardinality features and missing data</li>
    <li><strong>Bidding Simulation</strong>: Realistic bid calculations with revenue and cost assumptions</li>
    <li><strong>A/B Testing</strong>: Statistical comparison of profit distributions</li>
    <li><strong>Comprehensive Visualizations</strong>: Profit distributions, model performance, and accuracy trends</li>
  </ul>

  <h2>📚 <strong>Dataset Structure</strong></h2>
  <p>The project uses the Criteo Attribution Modeling dataset (<code>pcb_dataset_final.tsv</code>) with the following schema:</p>
  <p>Dataset source: <a href="https://www.kaggle.com/datasets/sharatsachin/criteo-attribution-modeling/data" target="_blank">Criteo Attribution Modeling on Kaggle</a></p>

  <table>
    <thead>
      <tr>
        <th>Field</th>
        <th>Description</th>
        <th>Type</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>timestamp</code></td>
        <td>Relative timestamp of impression</td>
        <td>integer</td>
      </tr>
      <tr>
        <td><code>uid</code></td>
        <td>User identifier</td>
        <td>string</td>
      </tr>
      <tr>
        <td><code>campaign</code></td>
        <td>Campaign identifier</td>
        <td>integer</td>
      </tr>
      <tr>
        <td><code>conversion</code></td>
        <td>Binary indicator of conversion</td>
        <td>integer</td>
      </tr>
      <tr>
        <td><code>click</code></td>
        <td>Binary indicator of click</td>
        <td>integer</td>
      </tr>
      <tr>
        <td><code>cost</code></td>
        <td>Transformed display cost</td>
        <td>float</td>
      </tr>
      <tr>
        <td><code>cat1</code> to <code>cat9</code></td>
        <td>Categorical contextual features</td>
        <td>integer</td>
      </tr>
    </tbody>
  </table>

  <p>The dataset contains 16.5M impressions, 45K conversions, and 700 campaigns, sampled to 1M impressions for analysis.</p>

  <h2>📢 <strong>Conclusion</strong></h2>
  <p>
    This project delivers a comprehensive evaluation of bidding strategies for Criteo’s programmatic advertising platform. The Linear Regression model offers higher profitability ($50,372.45 vs. $48,510.15) and simplicity, making it ideal for short-term deployment. The Deep Learning model excels in predictive performance (69.5% accuracy vs. 58.2%), offering scalability for long-term improvements. A Mann-Whitney U test (p < 0.0001) confirms significant profit differences, favoring Linear Regression. Future work includes online A/B testing and dynamic bidding strategies.
  </p>

  <h2>📜 <strong>Reference</strong></h2>
  <p>
    <em>“Attribution Modeling Increases Efficiency of Bidding in Display Advertising”</em><br/>
    Eustache Diemert, Julien Meynet, Damien Lefortier, Pierre Galland<br/>
    Published at <strong>AdKDD & TargetAd Workshop, ACM KDD 2017</strong>.
  </p>
<h2>Connect With Me</h2>
<div align="center">
  <a href="https://www.linkedin.com/in/ecembayindir" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:ecmbyndr@gmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
</div>

<br>
<p align="center">© 2025 Ecem Bayındır. All rights reserved.</p>
<hr/>
<p align="center">
  <img src="https://komarev.com/ghpvc/?username=ecembayindir&repo=Ad-Bidding-Model-Evaluationl&label=Repository%20views&color=0e75b6&style=flat" alt="Repository Views">
</p>

</body>
</html>
