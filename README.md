# 🎓 Student Performance Probability Analysis

<p align="center">
  <b>Probability & Statistical Analysis using Python</b><br>
  An exploratory data analysis project studying student outcomes through probability concepts.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge" alt="Matplotlib">
  <img src="https://img.shields.io/badge/Project-Statistics%20%26%20Probability-6C5CE7?style=for-the-badge" alt="Statistics">
</p>

---

## 📌 Project Overview

This project explores a student-performance dataset using Python and foundational probability techniques. It investigates how study hours, attendance, group discussion participation, previous test scores, and final exam outcomes can be examined with descriptive statistics and probability.

The notebook demonstrates how to translate statistical concepts into reproducible, code-based analysis. It is a learning-focused analytics project and does **not** claim to build a predictive machine-learning model.

## 🎯 Objectives

- Calculate the observed probabilities of passing and failing.
- Compare empirical and dataset-based pass probabilities.
- Build a probability distribution for the number of passes among three randomly selected students.
- Calculate the distribution's expected value (mean) and variance.
- Visualize the overlap between study hours and attendance using a Venn diagram.
- Build a contingency table for group discussion and final exam results.
- Calculate joint, marginal, and conditional probabilities.
- Compare conditional and overall pass probabilities to discuss possible dependence.
- Demonstrate Bayes' theorem with the values documented in the notebook.

## 📂 Repository Structure

```text
.
├── PR.1 Expectation Decider.ipynb
├── expectation_decider_dataset.csv
└── README.md
```

> Keep the notebook and CSV file in the same project folder. Update the notebook's data-loading cell to use a relative path so the project works on another computer.

## 🧰 Technology Stack

| Tool / Library | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Loading, filtering, and tabulating data |
| NumPy | Numerical calculations and probability distribution |
| Matplotlib | Plotting and visualization |
| matplotlib-venn | Venn diagram for two student groups |
| Jupyter Notebook | Interactive analysis and documentation |

## 🗃️ Dataset

The supplied dataset contains **200 rows and 5 columns**.

| Column | Description |
|---|---|
| `study_hours` | Study hours recorded for a student |
| `attendance` | Attendance percentage |
| `group_discussion` | Whether the student participated in group discussion (`Yes` / `No`) |
| `previous_test_score` | Score from a previous test |
| `final_exam_pass` | Final exam outcome (`Pass` / `Fail`) |

### Dataset Snapshot

- Records: **200**
- Pass outcomes: **57**
- Fail outcomes: **143**
- Group discussion: **105 Yes**, 95 No
- Mean study hours: **9.903**
- Mean attendance: **78.071%**

These figures describe the supplied CSV and may change if the dataset is updated.

## 🔬 Analysis Workflow

### 1. Load the data

Pandas loads the CSV file into a DataFrame for filtering and analysis.

Recommended portable file path:

```python
import pandas as pd

DF = pd.read_csv("expectation_decider_dataset.csv")
DF.head()
```

### 2. Basic probability

The notebook calculates probabilities such as:

\[
P(\text{Fail})=\frac{\text{Number of Fail outcomes}}{\text{Total students}}
\]

\[
P(\text{Pass})=\frac{\text{Number of Pass outcomes}}{\text{Total students}}
\]

It also calculates the observed probability of studying more than 10 hours and failing the final exam.

### 3. Empirical probability

A sample of 100 records is selected with `random_state=42` to calculate the sample pass rate. This is compared with the pass rate from the complete dataset.

### 4. Random variable and probability distribution

Let \(X\) be the number of students who pass out of three randomly selected students. The notebook considers \(X \in \{0,1,2,3\}\) and calculates the binomial-style probabilities using the observed pass and fail rates.

It then calculates the expected value and variance of this distribution.

### 5. Venn diagram

The notebook compares two groups:

- Students studying more than 10 hours.
- Students with attendance above 80%.

The overlapping region represents students meeting both conditions.

### 6. Contingency table and probability

A contingency table compares `group_discussion` with `final_exam_pass`. The notebook uses it to explore:

- **Joint probability:** group discussion participation and passing together.
- **Marginal probability:** the overall probability of passing.
- **Conditional probability:** the probability of passing among students who participated in group discussion.

### 7. Relationship between events

The notebook compares \(P(\text{Pass})\) with \(P(\text{Pass} \mid \text{Group Discussion}=\text{Yes})\). A difference can indicate an association in the observed data, but does not by itself establish causation.

### 8. Bayes' theorem

The final section demonstrates Bayes' theorem using the conditional probabilities and high-attendance probability written in the notebook. These values are presented as supplied assumptions; they are not all derived from the CSV in the current notebook.

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab

### Installation

1. Clone or download this repository.
2. Open a terminal in the project folder.
3. Install the required libraries:

```bash
pip install pandas numpy matplotlib matplotlib-venn jupyter
```

4. Launch Jupyter:

```bash
jupyter notebook
```

5. Open `PR.1 Expectation Decider.ipynb` and run the cells from top to bottom.

### Important portability note

The original notebook includes a computer-specific Windows path. Replace it with the relative-path example shown above, or the notebook may not run on another machine.

## 📊 Key Takeaways

- The supplied dataset has more `Fail` outcomes than `Pass` outcomes.
- Probability calculations provide a compact way to describe observed student outcomes.
- Contingency tables and conditional probabilities help examine relationships between categorical variables.
- Visualizing overlapping groups makes event relationships easier to communicate.
- Statistical association should not be interpreted as proof that one factor causes exam success.

## ⚠️ Limitations & Responsible Interpretation

- This is an exploratory educational analysis, not a validated student-risk or exam-prediction system.
- Results describe the supplied dataset and may not generalize to other student populations.
- The notebook's binomial-style distribution assumes a common pass probability and independent selections; interpret it as a simplified model.
- The Bayes' theorem section uses stated probabilities. Validate that the assumptions are mutually consistent and supported by data before using the result in a real analysis.
- No causal conclusions can be drawn from these calculations alone.

## 🔮 Future Improvements

- Add a data-quality check for missing values, duplicates, and unexpected categories.
- Derive the Bayes' theorem inputs from clearly defined dataset events.
- Add charts comparing pass rate by attendance, study-hour ranges, and group discussion participation.
- Include a reproducible results summary with rounded percentages.
- Add unit tests for probability calculations and validate assumptions explicitly.

## 👤 Author

**Harshit Dara**  
Data Analytics | Python | Statistics & Probability

- GitHub: [Add your GitHub profile URL]
- LinkedIn: [Add your LinkedIn profile URL]

## 📄 License

No license is specified yet. If you want others to reuse or modify this project, add a suitable open-source `LICENSE` file.

---

<p align="center">
  <i>Turning student data into statistical insight — one probability at a time.</i>
</p>
