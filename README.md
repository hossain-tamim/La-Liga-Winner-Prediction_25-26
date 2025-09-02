# La Liga 2025/26 Match Prediction 
## Abstract
This project predicts match outcomes for the 2025/26 La Liga season using machine learning. Historical match statistics were collected from the Understat API through the `soccerdata` Python library, then cleaned and structured for training. A **Random Forest classifier** was developed to forecast results while deliberately excluding matches involving **Real Oviedo**.  

The model uses team-level features such as goals, expected goals (xG), possession, and shooting metrics. Predictions are generated for the official 25/26 season schedule, providing insights for analysts, fans, and sports researchers.

---

## Project Structure
.
├── Data_Collection.ipynb # Notebook for collecting and cleaning data
├── RF_Model.ipynb # Notebook for Random Forest training & prediction
├── data/
│ ├── team_Match_dataB.csv
│ ├── resampled_team_Match_dataB.csv
│ └── schedule_25-26.csv
└── README.md

## Data Collection
- **Source**: [Understat API](https://understat.com/) via `soccerdata` library.  
- **League**: Spanish La Liga.  
- **Seasons**: Historical seasons up to 2023/24.  
- **Features**: Goals, xG, possession, passes, and shots.  
- **Processing**:  
  - Data exported to CSV for reproducibility.  
  - Balanced dataset created via resampling.  
  - Team list curated, but Real Oviedo excluded from predictions.  

---

## Model Development
- **Algorithm**: Random Forest Classifier  
- **Steps**:
  1. Loaded cleaned historical data.  
  2. Performed correlation analysis for feature selection.  
  3. Resampled dataset to reduce class imbalance (home win, draw, away win).  
  4. Trained model on past match statistics.  
  5. Tested performance on unseen fixtures.  

---

## Predictions for 25/26 Season
- **Input**: `schedule_25-26.csv` containing official fixtures.  
- **Process**: Match schedule merged with team statistics, model outputs predicted results.  
- **Exclusion**: Matches involving Real Oviedo are skipped.  
- **Output**: Season-long predictions for all other La Liga matches.  
---

## 📖 How to Run
1. Install dependencies:
   ```bash
   pip install soccerdata pandas scikit-learn
   Run Data_Collection.ipynb to fetch and clean historical data.

Run RF_Model.ipynb to train the model and generate predictions.
