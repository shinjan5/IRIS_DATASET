<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Iris Flower Classification – README</title>
  <style>
    :root {
      --bg: #0b1220;
      --panel: #121a2b;
      --text: #e7eefc;
      --muted: #a8b3cf;
      --accent: #6ea8fe;
      --good: #2ecc71;
      --warn: #f1c40f;
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji", "Segoe UI Emoji";
      background: linear-gradient(180deg, #0b1220, #0d1526 50%, #0b1220);
      color: var(--text);
      line-height: 1.6;
    }
    .container {
      max-width: 920px;
      margin: 48px auto;
      padding: 0 20px;
    }
    header {
      background: radial-gradient(1200px 400px at 50% 0, rgba(110,168,254,0.18), transparent 60%);
      padding: 24px 0 6px;
      margin-bottom: 22px;
      border-bottom: 1px solid #1f2a44;
    }
    h1 { font-size: 2rem; margin: 0 0 6px; }
    .subtitle { color: var(--muted); margin-top: 0; }
    section {
      background: var(--panel);
      border: 1px solid #1f2a44;
      border-radius: 14px;
      padding: 18px 18px;
      margin: 14px 0;
      box-shadow: 0 6px 24px rgba(0,0,0,0.28);
    }
    h2 { font-size: 1.2rem; margin: 0 0 10px; color: var(--accent); }
    ul { margin-top: 8px; }
    code, pre {
      font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace;
      background: #0c1324;
      border: 1px solid #1c2742;
      color: #eaf2ff;
      border-radius: 10px;
    }
    code { padding: 2px 6px; }
    pre { padding: 12px; overflow: auto; }
    table {
      width: 100%;
      border-collapse: collapse;
      margin: 10px 0 0;
      border: 1px solid #213055;
    }
    th, td {
      border: 1px solid #213055;
      padding: 10px 12px;
      text-align: left;
    }
    th { background: #0f1931; }
    .tag {
      display: inline-block;
      font-size: 0.85rem;
      color: #cfe1ff;
      background: #0f1a33;
      border: 1px solid #23345d;
      padding: 4px 8px;
      border-radius: 999px;
      margin-right: 8px;
    }
    .callout {
      border-left: 4px solid var(--accent);
      padding: 8px 12px;
      background: #0e1830;
      color: #dbe6ff;
      margin: 10px 0 0;
      border-radius: 8px;
    }
    .kpi {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 10px;
      margin-top: 10px;
    }
    .kpi > div {
      background: #0f1a33;
      border: 1px solid #22335a;
      border-radius: 12px;
      padding: 12px;
    }
    .kpi h3 { margin: 0; font-size: 1.6rem; color: var(--good); }
    .kpi p { margin: 6px 0 0; color: var(--muted); }
    a { color: #9cc4ff; text-decoration: none; }
    a:hover { text-decoration: underline; }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>🌸 Iris Flower Classification</h1>
      <p class="subtitle">End-to-end ML workflow: EDA → Model Training → Evaluation → Results</p>
      <div>
        <span class="tag">Python</span>
        <span class="tag">scikit-learn</span>
        <span class="tag">Pandas</span>
        <span class="tag">Matplotlib/Seaborn</span>
      </div>
    </header>

    <section>
      <h2>Overview</h2>
      <p>
        This project applies several machine learning algorithms to the classic
        <strong>Iris dataset</strong> to classify flowers into three species:
        <em>Setosa</em>, <em>Versicolor</em>, and <em>Virginica</em>.
        The dataset has 150 samples and 4 features:
        <code>sepal_length</code>, <code>sepal_width</code>, <code>petal_length</code>, <code>petal_width</code>.
      </p>
      <div class="kpi">
        <div>
          <h3>98.33%</h3>
          <p>Best mean CV accuracy (SVM)</p>
        </div>
        <div>
          <h3>97.50%</h3>
          <p>LDA mean CV accuracy</p>
        </div>
        <div>
          <h3>4</h3>
          <p>Features used</p>
        </div>
      </div>
      <div class="callout">
        <strong>Key EDA insight:</strong> Petal-based features (length &amp; width) show
        the clearest separation between species; sepal features overlap more.
      </div>
    </section>

    <section>
      <h2>Project Structure</h2>
      <ul>
        <li><strong>Exploratory Data Analysis (EDA)</strong> — histograms, boxplots, pairplots to understand distributions and relationships.</li>
        <li><strong>Model Training</strong> — multiple algorithms evaluated via <code>k</code>-fold cross validation.</li>
        <li><strong>Evaluation</strong> — accuracy, confusion matrix, and classification report.</li>
      </ul>
    </section>

    <section>
      <h2>Algorithms &amp; Cross-Validation Results</h2>
      <p>Mean accuracy and standard deviation across folds:</p>
      <table>
        <thead>
          <tr>
            <th>Model</th>
            <th>Mean Accuracy</th>
            <th>Std. Deviation</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>Logistic Regression (LR)</td><td>94.17%</td><td>±6.59%</td></tr>
          <tr><td>Linear Discriminant Analysis (LDA)</td><td>97.50%</td><td>±3.82%</td></tr>
          <tr><td>K-Nearest Neighbors (KNN)</td><td>95.83%</td><td>±4.17%</td></tr>
          <tr><td>Decision Tree (CART)</td><td>94.17%</td><td>±5.34%</td></tr>
          <tr><td>Naive Bayes (NB)</td><td>95.00%</td><td>±5.53%</td></tr>
          <tr><td>Support Vector Machine (SVM)</td><td><strong>98.33%</strong></td><td>±3.33%</td></tr>
        </tbody>
      </table>

      <div class="callout">
        <strong>Takeaway:</strong> SVM achieved the highest accuracy with low variance. LDA performed nearly as well and very consistently.
      </div>
    </section>

    <section>
      <h2>Sample Validation Metrics (SVM)</h2>
      <pre><code>Accuracy: 0.9667
Confusion Matrix:
[[11  0  0]
 [ 0 12  1]
 [ 0  0  6]]

Per-class report:
- Iris-setosa:    precision=1.00, recall=1.00, f1=1.00, support=11
- Iris-versicolor: precision=1.00, recall=0.92, f1=0.96, support=13
- Iris-virginica:  precision=0.86, recall=1.00, f1=0.92, support=6
</code></pre>
      <p class="callout">Only one misclassification: a Versicolor predicted as Virginica.</p>
    </section>

    <section>
      <h2>How to Run</h2>
      <ol>
        <li>
          <p><strong>Clone</strong>:</p>
          <pre><code>git clone https://github.com/yourusername/iris-flower-classification.git
cd iris-flower-classification
</code></pre>
        </li>
        <li>
          <p><strong>Install dependencies</strong>:</p>
          <pre><code>pip install -r requirements.txt
</code></pre>
        </li>
        <li>
          <p><strong>Run</strong>:</p>
          <pre><code># Notebook
jupyter notebook iris_classification.ipynb
