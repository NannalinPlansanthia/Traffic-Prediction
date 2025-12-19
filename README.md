# Traffic-Prediction
SARIMA, Exponential Smoothing and Prophet models were deployed in order to predict the vehicle volumes over time. Due to asynchronous collection and data sparsity at various junctions, this report focused on Junction 1. Lastly, holiday effects were modeled under the assumption that the data is from the United States, which may affect the accuracy of the results.
## Motivation
Traffic congestion is a rising global concern that negatively impacts countries globally. The widespread consequences include time loss, freight delays, exacerbated environmental impacts, increased fuel consumption, and a diminished quality of life. (INRIX, 2025) Accurate traffic prediction not only improves network capacity utilization but also helps alleviate congestion by empowering traffic management centers (TMCs) and road operators to control traffic more effectively. (Shaygan, Meese, Li, Zhao, & Nejad, 2022) 
## Overview
1. Data Pre-processing
2. Exploratory Data Analysis
3. SARIMA Model
4. Multiplicative Holt-Winter's Model
5. Prophet Model
6. Model Comparison
## Data
The dataset is available on Kaggle: <https://www.kaggle.com/datasets/fedesoriano/traffic-prediction-dataset> <br>
This dataset contains 48120 observations of the number of vehicles each hour in four different junctions. The sensors on each of these junctions were collecting data at different times. Hence, some of the junctions have provided limited or sparse data requiring thoughtfulness when creating future projections. <br>
Description
1. DateTime - Datetime in hourly frequency
2. Junction - Number of the junction, ranging from 1 to 4
3. Vehicles - Number of vehicles
4. ID - Unique id
## Result
/assets/images/sarima-forecast.png

| Metrics | SARIMA | Holt-Winter's | Prophet |
| :---:|:---:|:---:|:---:|
| RMSE|19.2464|51.3292|9.4667|
| MAE|14.8871|40.1727|7.4987|
| MAPE|0.2909|0.5692|0.1300|

The Prophet model is the most suitable for this dataset. It captures detailed seasonal patterns and holiday effects, facilitating a deeper understanding of the traffic volume over time. Furthermore, it outperforms both SARIMA and the multiplicative Holt-Winters model while requiring significantly less computational time and data preprocessing.
## References
1. Agarwal, A. (2004).  Weekend travel behavior is expected to be substantially different from the weekday travel behavior for difference in several spatial and temporal constraints. (Graduate dissertation, University of South Florida)
2. FOX40 News. (2025).  Many people are hitting the road for the holidays, instead of flying.  Retrieved December 13, 2025, from <https://www.youtube.com/watch?v=YQv9XwJbvVc>
4. GEOTAB. (2024).  What causes traffic congestion?.  Retrieved December 13, 2025, from <https://www.geotab.com/blog/traffic-congestion/>
5. Hyndman, R.J., & Athanasopoulos, G. (2021) Forecasting: principles and practice, 3rd edition, OTexts: Melbourne, Australia. OTexts.com/fpp3. Accessed on December 13, 2025.
6. INRIX. (2025).  INRIX 2025 Global Traffic Scorecard.  Retrieved December 13, 2025, from <https://inrix.com/scorecard/>
7. Shaygan, M., Meese, C., Li, W., Zhao, X., & Nejad, M. (2022).  Traffic prediction using artificial intelligence: Review of recent advances and emerging opportunities. Transportation Research Part C: Emerging Technologies. 145.
