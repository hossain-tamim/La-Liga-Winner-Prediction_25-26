# La Liga 2025/26 Match Prediction 
## Abstract
This project focuses on predicting match outcomes for the 2025/26 La Liga season using a machine learning approach. Historical match data was collected from the Understat API through the soccerdata Python library. The dataset includes team-level match statistics, past performance metrics, and scheduling information. A Random Forest classifier was developed and trained to predict match results. The model leverages resampled team match data to handle class imbalance and uses features such as goals, possession, and shooting statistics to generate predictions. The final system provides automated forecasts for all league matches in the 25/26 season, except those involving Real Oviedo, offering insights for analysts, fans, and sports researchers.

---

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
2. Run Data_Collection.ipynb to fetch and clean historical data.
3. Run RF_Model.ipynb to train the model and generate predictions.
