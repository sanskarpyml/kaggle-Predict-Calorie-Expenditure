<h1>Calorie Expenditure Prediction</h1>

<p><strong>Author:</strong> Sanskar Gupta</p>
<p><strong>Objective:</strong> Predict the number of calories burned during physical activity using machine learning models.</p>

<h2>Overview</h2>
<p>This project involves building a regression model to estimate calorie expenditure based on features like gender, age, height, weight, duration, and heart rate metrics.</p>

<h2>Models Used</h2>
<ol>
  <li>
    <strong>Model 1:</strong> HistGradientBoostingRegressor<br>
    A tree-based gradient boosting algorithm from <code>scikit-learn</code> optimized for speed and performance.
  </li>
  <li>
    <strong>Model 2:</strong> StackingRegressor<br>
    A stacked model combining:
    <ul>
      <li>Base: HistGradientBoostingRegressor</li>
      <li>Final Estimator: LinearRegression</li>
    </ul>
  </li>
</ol>

<h2>Evaluation Metric</h2>
<p><strong>Root Mean Squared Logarithmic Error (RMSLE)</strong> is used to evaluate the model performance.</p>

<h2>Project Structure</h2>
<ul>
  <li><code>train_model.py</code> – Script for training models</li>
  <li><code>model1.pkl</code> – Saved model using HistGradientBoostingRegressor</li>
  <li><code>model2.pkl</code> – Saved Stacking model</li>
  <li><code>requirements.txt</code> – Python dependencies</li>
</ul>

<h2>How to Use</h2>
<pre>
git clone https://github.com/your-username/calorie-prediction
cd calorie-prediction
pip install -r requirements.txt
python train_model.py
</pre>

<h2>Results</h2>
<p>The stacked model (Model 2) provided better accuracy and lower RMSLE compared to the single-model approach.</p>

<h2>Conclusion</h2>
<p>Stacking different regression algorithms can enhance prediction accuracy by combining strengths of multiple models.</p>


