# 🌲 Forest-Fire-Risk-Classification-Model

# 📌 Project Overview
This project aims to predict the risk of forest fires using meteorological data, helping improve resource allocation and public awareness. Originally focused on Portugal's national forests, this model explores fire risk prediction using binary logistic regression to classify areas as high or low fire risk. The project was developed during the Spring 2023 semester. 

# 👥 Authors
Madhuri, Will, Jinnie, Emir, Tianze
Mentor: Ethan

# 🔥 What is a Forest Fire?
Forest fires, also known as wildfires or bushfires, are uncontrolled fires in combustible vegetation areas. They often occur in dry regions with high temperatures and can have severe economic, environmental, and social impacts, especially as climate change intensifies their frequency and scale.

# 🎯 Motivation
Given the prevalence and impact of wildfires, especially in regions like California, this project aims to create a predictive model that can improve fire risk assessment. Accurate predictions can significantly enhance decision-making for communities and agencies managing fire-prone areas.

# 📊 Dataset
**Source**: Forest Fires Dataset - Burned area data from northeast Portugal.
**Reference**: P. Cortez and A. Morais, "A Data Mining Approach to Predict Forest Fires Using Meteorological Data," 13th EPIA Conference on Artificial Intelligence, 2007. Link to dataset

**Key Features**:

- **Geographic**: X, Y coordinates within Montesinho park map
- **Temporal**: Month (jan-dec), Day (mon-sun)
- **Weather**: Temperature (°C), Relative Humidity (%), Wind Speed (km/h), Rain (mm/m²)
- **Fire Weather Indices**: FFMC, DMC, DC, ISI
- **Target**: Burned Area (ha)

**Fire Weather Indices Explained**:

- **FFMC**: Fine Fuel Moisture Code, moisture content of surface fuels.
- **DMC**: Duff Moisture Code, moisture in moderate soil layers.
- **DC**: Drought Code, moisture in deeper organic soil layers.
- **ISI**: Initial Spread Index, expected rate of fire spread.

# ⚙️ Modeling Approach
The project uses binary logistic regression to classify fires as high risk (1) or low risk (0) based on the burned area.

# 🚧 Challenges
1. **Feature Variability**: Different units across features and categorical variables.
2. **Multicollinearity**: Features with high correlation.
3. **Class Imbalance**: Higher occurrence of low-risk fires compared to high-risk ones.

# 🛠️ Solutions
- **Feature Engineering**: Used helper functions to identify risk and create seasonal features. Standardized numerical features for consistency.
- **Multicollinearity Mitigation**: Removed features with correlations >0.5.
- **Class Imbalance Adjustment**: Lowered the probability threshold to prioritize recall, reducing false negatives.

# 📈 Evaluation
Classification includes:

- **True Positives**: High-risk fires correctly identified.
- **False Positives**: Low-risk areas incorrectly classified as high risk.
- **False Negatives**: High-risk fires missed, but minimized by adjusting the model's threshold.
The final threshold was set at 0.15, focusing on a "better safe than sorry" approach to maximize recall.

# 📝 Conclusion and Limitations
- **High-Risk Threshold**: Fires with burned areas over 10 hectares are labeled as high risk.
- **Generalization**: Model is trained on data from Portugal and may not generalize to regions like California without further adaptation.
- **Impact of Location**: Fire damage potential varies by region, so risk levels might need to adjust for population density or forest type.

# 🔍 Future Work
- Expand dataset to include other regions for a more generalized model.
- Explore alternative models like neural networks to improve prediction accuracy.
