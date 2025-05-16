<h1>Calorie Expenditure Prediction</h1>

<p><strong>Author:</strong> Sanskar Gupta</p>
<p><strong>Project Type:</strong> Machine Learning Regression</p>
<p><strong>Goal:</strong> To build predictive models that estimate the number of calories burned during physical exercise using physiological and exercise-related features.</p>

<hr>

<h2>Table of Contents</h2>
<ol>
  <li><a href="#problem-statement">Problem Statement</a></li>
  <li><a href="#dataset">Dataset</a></li>
  <li><a href="#data-preprocessing">Data Preprocessing</a></li>
  <li><a href="#models-used">Models Used</a></li>
  <li><a href="#evaluation-metric">Evaluation Metric</a></li>
  <li><a href="#results">Results</a></li>
  <li><a href="#usage">Usage</a></li>
  <li><a href="#project-structure">Project Structure</a></li>
  <li><a href="#future-work">Future Work</a></li>
  <li><a href="#contact">Contact</a></li>
</ol>

<hr>

<h2 id="problem-statement">1. Problem Statement</h2>
<p>Calorie tracking is essential for fitness and health. This project aims to predict the number of calories expended during a physical activity session, based on various biometric and activity-level inputs.</p>

<h2 id="dataset">2. Dataset</h2>
<p>The dataset contains the following features:</p>
<ul>
  <li><code>Gender</code> – Male/Female</li>
  <li><code>Age</code> – Age of the person</li>
  <li><code>Height</code> – Height in cm</li>
  <li><code>Weight</code> – Weight in kg</li>
  <li><code>Duration</code> – Duration of exercise in minutes</li>
  <li><code>Heart_Rate</code> – Heart rate during exercise</li>
  <li><code>Body_Temp</code> – Body temperature in °C</li>
  <li><code>Calories</code> – Target variable (calories burned)</li>
</ul>

<h2 id="data-preprocessing">3. Data Preprocessing</h2>
<ul>
  <li>Checked for missing values</li>
  <li>Encoded categorical variables (Gender)</li>
  <li>Feature scaling (optional – not needed for tree-based models)</li>
  <li>Split data into training and test sets</li>
</ul>

<h2 id="models-used">4. Models Used</h2>

<h3>Model 1: HistGradientBoostingRegressor</h3>
<ul>
  <li>Powerful tree-based model from <code>sklearn.ensemble</code></li>
  <li>Efficient for large datasets and handles missing values</li>
  <li>Used default parameters with hyperparameter tuning</li>
</ul>

<h3>Model 2: StackingRegressor</h3>
<ul>
  <li><strong>Base Learner:</strong> HistGradientBoostingRegressor</li>
  <li><strong>Final Estimator:</strong> LinearRegression</li>
  <li>Combines predictions from multiple models for better performance</li>
</ul>

<h2 id="evaluation-metric">5. Evaluation Metric</h2>
<p>We used <strong>Root Mean Squared Logarithmic Error (RMSLE)</strong> to evaluate model performance, as it penalizes under-predictions and handles skewed distributions well.</p>

<pre>
from sklearn.metrics import mean_squared_log_error
rmsle = np.sqrt(mean_squared_log_error(y_true, y_pred))
</pre>

<h2 id="results">6. Results</h2>
<ul>
  <li><strong>Model 1 RMSLE:</strong> 0.0594</li>
  <li><strong>Model 2 RMSLE:</strong> 0.0509 </li>
  <li>The stacking model generalized better on unseen data</li>
</ul>

<h2 id="usage">7. Usage</h2>

<pre>
# Clone the repository
git clone https://github.com/your-username/calorie-prediction

# Navigate to the folder
cd calorie-prediction

# Install dependencies
pip install -r requirements.txt

# Run the training script
python train_model.py
</pre>

<p>Replace <code>your-username</code> with your actual GitHub username.</p>

<h2 id="project-structure">8. Project Structure</h2>
<ul>
  <li><code>train_model.py</code> – Training pipeline for both models</li>
  <li><code>model1.pkl</code> – Trained HistGradientBoostingRegressor model</li>
  <li><code>model2.pkl</code> – Trained StackingRegressor model</li>
  <li><code>utils.py</code> – Helper functions (e.g., preprocessing, evaluation)</li>
  <li><code>requirements.txt</code> – List of required libraries</li>
  <li><code>README.html</code> – Project documentation</li>
</ul>

<h2 id="future-work">9. Future Work</h2>
<ul>
  <li>Integrate the model into a web application using Streamlit</li>
  <li>Experiment with additional ensemble techniques (e.g., XGBoost, LightGBM)</li>
  <li>Incorporate more real-time biometric features</li>
</ul>





