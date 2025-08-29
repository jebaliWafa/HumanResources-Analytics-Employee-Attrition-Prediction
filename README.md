# 👩‍💼 Analyse RH : Prédiction de l’Attrition des Employés  

> ℹ️ **Note : La version anglaise de ce README est disponible plus bas**.  


## 👥 Contributeurs  

- **Jebali Wafa**  
- **Eya Ben Doudou**  
- **Abir Lassoued**  
- **Belanez Hamdi**  

---

## 📌 Aperçu  
L’attrition des employés est un défi majeur pour **HumanForYou**, une entreprise pharmaceutique indienne connaissant un **taux de rotation annuel de 15%**.  
Ce projet applique l’**analyse RH basée sur la donnée** pour prédire l’attrition et fournir des recommandations afin d’améliorer la rétention.  

Nous avons suivi la méthodologie **CRISP-DM** et utilisé plusieurs jeux de données internes (données générales, enquêtes, pointages entrée/sortie) pour développer un modèle prédictif et le déployer sous forme d’**application interactive Streamlit**.  

---

## 🔍 Préparation & Analyse des Données  

- **Jeux de données** : Données générales, enquêtes managers, enquêtes employés, horaires entrée/sortie  
- **Valeurs manquantes** : Traitement par imputation KNN & médiane  
- **Ingénierie des variables** : Fusion des 5 datasets + nouvelles variables (ex. `Heures_moy_journalières`)  
- **Normalisation & Encodage** : StandardScaler + LabelEncoder  
- **Analyse des valeurs extrêmes** : Justification par régression et cohérence métier (revenus, ancienneté)  

---

## 📊 Analyse Exploratoire (EDA)  

- **Taux d’attrition** : 16.12% (déséquilibre des classes)  
- **Résultats clés** :  
  - L’attrition est **plus élevée chez les 28–35 ans**  
  - Taux élevé chez les employés ayant **1–10 ans d’expérience**  
  - Les salaires entre **10k–50k ₹** sont associés à une forte rotation  
  - **Heures de travail longues + faible ancienneté** = fort risque d’attrition  

---

## 🤖 Modélisation  

- **Modèles testés** : Régression logistique, Arbre de décision, Random Forest, XGBoost  
- **Modèle final** : **Random Forest Classifier** (meilleur compromis performance/interprétabilité)  
- **Performances** :  
  - Précision : **97.5%**  
  - F1-score : **0.917**  
  - AUC-ROC : **0.928**  
- **Variables les plus importantes** :  
  1. Âge  
  2. Années totales d’expérience  
  3. Revenu mensuel  

---

## 🚀 Déploiement  

- **Framework** : Streamlit  
- **Backend** : Pipeline de prétraitement + Random Forest sauvegardé avec `joblib`  
- **Fonctionnalités de l’app** :  
  - Interface simple pour saisir les infos d’un employé  
  - Prédiction du **risque d’attrition (Élevé/Faible)**  
  - Recommandations personnalisées pour améliorer la rétention



---

# 👩‍💼 Human Resources Analytics: Employee Attrition Prediction  

*(English version — see note above)*  

## 📌 Overview  
Employee attrition is a major challenge for **HumanForYou**, an Indian pharmaceutical company with a **15% annual turnover rate**.  
This project applies **data-driven HR analytics** to predict attrition and provide recommendations to improve employee retention.  

We followed the **CRISP-DM methodology** and used multiple datasets (general data, surveys, in/out clocking records) to build a predictive model and deploy it as an **interactive Streamlit web app**.  

---

## 🔍 Data Preparation & Analysis  

- **Datasets**: General employee data, manager surveys, employee surveys, clock-in/out records  
- **Missing Values**: KNN & Median imputation  
- **Feature Engineering**: Merged datasets + derived features (e.g., `Average_Daily_Work_Hours`)  
- **Normalization & Encoding**: StandardScaler + LabelEncoder  
- **Outlier Analysis**: Validated via regression & domain logic (salary, tenure)  

---

## 📊 Exploratory Data Analysis (EDA)  

- **Attrition Rate**: 16.12% (class imbalance)  
- **Key Insights**:  
  - Highest attrition in **28–35 age group**  
  - Employees with **1–10 years of experience** most affected  
  - Salary range **₹10k–₹50k** = higher attrition  
  - **Long hours + short tenure** = high attrition risk  

---

## 🤖 Modeling  

- **Models Tested**: Logistic Regression, Decision Tree, Random Forest, XGBoost  
- **Final Model**: **Random Forest Classifier**  
- **Performance**:  
  - Accuracy: **97.5%**  
  - F1-Score: **0.917**  
  - AUC-ROC: **0.928**  
- **Top Features**:  
  1. Age  
  2. Total Working Years  
  3. Monthly Income  

---

## 🚀 Deployment  

- **Framework**: Streamlit  
- **Backend**: Preprocessing + trained Random Forest (`joblib`)  
- **App Features**:  
  - Input employee details via UI  
  - Predict **Attrition Risk (High/Low)**  
  - Provide **personalized retention recommendations** 
