# Student Performance Prediction 

## Project Overview
A simple desktop application that predicts a student's final exam score (out of 100) using a linear regression model trained on historical student data. The model uses three input features:
- `hours_studied` — average hours studied per day
- `attendance` — attendance percentage (0–100)
- `previous_score` — previous exam score (0–100)

A Tkinter GUI provides a user-friendly interface for entering inputs and seeing the predicted final score along with a short interpretation.

---

## Files
- `app_gui.py` — Tkinter application (the GUI and prediction logic).
- `train_model.py` — (optional) script to train the model and save it for the GUI to load.
- `students.csv` — dataset (must contain columns: `hours_studied`, `attendance`, `previous_score`, `final_score`).
- `requirements.txt` — list of Python dependencies (see below).
- `README.md` — this file.

> Note: In your provided script the model is trained at runtime when the GUI runs. For production use, you may want to separate training and GUI (serialize model to `model.pkl`).

---

## Requirements
Tested with Python 3.8+. Required packages:
```
pandas
scikit-learn
tkinter   # usually included with Python on Windows/macOS; on Linux install via package manager.
```

Create `requirements.txt`:
```
pandas>=1.0
scikit-learn>=1.0
```

On Ubuntu/Debian install tkinter:
```
sudo apt-get install python3-tk
```

---

## How to Run (Quick)
1. Place `students.csv` in the same folder as the scripts.
2. Run the GUI:
```bash
python app_gui.py
```
3. Enter:
- Hours Studied per Day
- Attendance (%)
- Previous Exam Score
Then click **Predict Final Score**. The predicted score and an interpretation will be shown.

---

## How It Works (Short)
1. The script loads `students.csv`.
2. It selects features `["hours_studied","attendance","previous_score"]` and target `final_score`.
3. The dataset is split into train/test with `train_test_split(..., test_size=0.2, random_state=42)`.
4. A `LinearRegression` model is trained on the training set.
5. Model performance is printed/shown as MSE and R² on the GUI footer.
6. GUI accepts input, builds a 1-row DataFrame, calls `model.predict(...)`, and displays the result and comment.

---

## Dataset Format Example
CSV with header, for example:
```csv
hours_studied,attendance,previous_score,final_score
2.5,78,60,62
5.0,92,84,88
1.0,55,40,38
```

---

## Recommended Improvements
- **Serialize model**: Train once and save using `joblib.dump(model, "model.pkl")`, then load in GUI for faster startup.
- **Validation**: Validate input ranges (e.g., `attendance` between 0-100).
- **Scaling and Feature Engineering**: Add features like subject difficulty, sleep hours, weekly study pattern, etc.
- **Better models**: Try RandomForest, Gradient Boosting, or cross-validation to improve performance.
- **UI improvements**: Add input sliders, tooltips, and save prediction history.
- **Web app**: Convert GUI to Streamlit/Flask for remote use.

---

## Retraining Workflow (Optional)
1. Edit `train_model.py` to load `students.csv`.
2. Train and evaluate model, then save:
```python
from joblib import dump
dump(model, "model.pkl")
```
3. Modify `app_gui.py` to load `model.pkl`:
```python
from joblib import load
model = load("model.pkl")
```

---

## Troubleshooting
- **tkinter import error**: Install the OS package for tkinter, e.g. `sudo apt-get install python3-tk`.
- **Pandas/csv errors**: Ensure `students.csv` has correct headers and numeric values.
- **Model shows poor predictions**: Check dataset size, quality, and consider using more features or more complex models.

---

## License & Attribution
You can reuse and modify this code for learning and internal academic projects. Add an appropriate license (e.g., MIT) if you plan to publish or share widely.

---

##  Author
(Awatans Asthana) — 25BEC10075 
