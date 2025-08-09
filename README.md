<h1>NeuroSpectra</h1>
<img src="[https://via.placeholder.com/800x200.png?text=NeuroSpectra+Autism+Detection](https://regencyhealthcare.in/blog/autism-causes-symptoms-and-how-to-manage/)" alt="NeuroSpectra Banner">
<p><em>Advancing autism detection through machine learning and neuroscience.</em></p>

<h2>Overview</h2>
<p>NeuroSpectra is a machine learning-powered web application designed to predict autism spectrum disorder (ASD) using behavioral and demographic data. Built with a robust SVM model trained on a dataset of 704 records, it achieves up to 100% accuracy in identifying ASD patterns. The platform combines a FastAPI backend with a React and Tailwind CSS frontend for a seamless user experience.</p>

<h2>Live Demo</h2>
<ul>
    <li><strong>Frontend</strong>: <a href="https://neurospectra.netlify.app/">https://neurospectra.netlify.app/</a></li>
    <li><strong>Backend API</strong>: <a href="https://neurospectra-backend-4.onrender.com/">https://neurospectra-backend-4.onrender.com/</a></li>
</ul>

<h2>Features</h2>
<ul>
    <li><strong>Accurate ASD Prediction</strong>: Uses a tuned SVM model with 100% accuracy and F-beta score (beta=0.5) on test data.</li>
    <li><strong>User-Friendly Interface</strong>: Input behavioral scores (A1-A10), age, gender, and other features via a responsive React frontend.</li>
    <li><strong>Scalable Backend</strong>: FastAPI handles predictions with CORS-enabled communication.</li>
    <li><strong>Data Preprocessing</strong>: MinMax scaling and one-hot encoding ensure robust input handling.</li>
    <li><strong>Cross-Validated Models</strong>: Evaluated multiple models (SVM, Random Forest, KNN, etc.) with SVM outperforming others.</li>
</ul>

<h2>Tech Stack</h2>
<ul>
    <li><strong>Backend</strong>: FastAPI, Python, Scikit-learn, Pandas, NumPy</li>
    <li><strong>Frontend</strong>: React, HTML, Tailwind CSS</li>
    <li><strong>Model</strong>: Support Vector Machine (SVM) with linear kernel</li>
    <li><strong>Deployment</strong>: Netlify (frontend), Render (backend)</li>
    <li><strong>Dataset</strong>: Autism screening data (704 records, 21 features)</li>
</ul>

<h2>Installation</h2>
<h3>Backend Setup</h3>
<ol>
    <li>Clone the repository:<br>
        <pre><code>git clone https://github.com/your-username/neurospectra.git
cd neurospectra/backend</code></pre>
    </li>
    <li>Create a virtual environment and install dependencies:<br>
        <pre><code>python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt</code></pre>
    </li>
    <li>Ensure <code>svm_model.pkl</code> and <code>feature_columns.pkl</code> are in the <code>MLModels/</code> directory (generated from <code>autism_detection.ipynb</code>).</li>
    <li>Run the FastAPI server:<br>
        <pre><code>uvicorn main:app --reload</code></pre>
        Access the API at <code>http://localhost:8000</code>.
    </li>
</ol>

<h3>Frontend Setup</h3>
<ol>
    <li>Navigate to the frontend directory:<br>
        <pre><code>cd neurospectra/frontend</code></pre>
    </li>
    <li>Install dependencies:<br>
        <pre><code>npm install</code></pre>
    </li>
    <li>Start the development server:<br>
        <pre><code>npm start</code></pre>
        Access the app at <code>http://localhost:3000</code>.
    </li>
</ol>

<h2>Usage</h2>
<ol>
    <li>Visit the frontend at <a href="https://neurospectra.netlify.app/">https://neurospectra.netlify.app/</a>.</li>
    <li>Enter the required inputs (A1-A10 scores, age, gender, ethnicity, jaundice, autism history, country, result, relation).</li>
    <li>Submit to receive an ASD prediction ("YES" or "NO").</li>
    <li>Explore the API at <a href="https://neurospectra-backend-4.onrender.com/docs">https://neurospectra-backend-4.onrender.com/docs</a> for detailed endpoint documentation.</li>
</ol>

<h2>API Endpoints</h2>
<ul>
    <li><strong>GET /</strong>: Returns a welcome message.</li>
    <li><strong>POST /predict</strong>: Accepts input data and returns an ASD prediction.<br>
        <pre><code>{
    "A1_Score": 1,
    "A2_Score": 1,
    "A3_Score": 0,
    ...
    "relation": "Self"
}</code></pre>
    </li>
</ul>

<h2>Dataset</h2>
<p>The model was trained on a dataset of 704 records with 21 features, including:</p>
<ul>
    <li>Behavioral scores (A1-A10)</li>
    <li>Demographic data (age, gender, ethnicity)</li>
    <li>Medical history (jaundice, autism)</li>
    <li>Target: <code>Class/ASD</code> (YES/NO)</li>
    <li>Preprocessing: Dropped 2 rows with missing age, applied MinMax scaling and one-hot encoding.</li>
</ul>

<h2>Model Performance</h2>
<ul>
    <li><strong>SVM (Optimized)</strong>: 100% accuracy, 100% F-beta score (beta=0.5)</li>
    <li><strong>Other Models Tested</strong>:</li>
    <ul>
        <li>Random Forest: 99.01% cross-validation score</li>
        <li>Logistic Regression: 99.71% cross-validation score</li>
        <li>KNN: 95.73% (best at k=19)</li>
        <li>Naive Bayes: 87.46% cross-validation score</li>
    </ul>
</ul>

<h2>Contributing</h2>
<p>Contributions are welcome! To contribute:</p>
<ol>
    <li>Fork the repository.</li>
    <li>Create a feature branch (<code>git checkout -b feature/new-feature</code>).</li>
    <li>Commit changes (<code>git commit -m 'Add new feature'</code>).</li>
    <li>Push to the branch (<code>git push origin feature/new-feature</code>).</li>
    <li>Open a pull request.</li>
</ol>

<h2>License</h2>
<p>This project is licensed under the MIT License.</p>
