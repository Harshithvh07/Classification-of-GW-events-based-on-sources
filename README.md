# Classification-of-GW-events-based-on-sources

## **1. Introduction**
This project aims to classify gravitational wave events into three categories: **Binary Black Hole (BBH), Binary Neutron Star (BNS), and Neutron Star-Black Hole (NSBH)** mergers. The dataset contains various astrophysical parameters extracted from gravitational wave observations [GWOSC]. The goal is to build a robust classification model to distinguish between these event types accurately. 

## **2. Methodology**

### **3.1 Data Preprocessing**
#### **Class Labeling:**
- **BBH**: Both objects have mass ≥ 3 M☉
- **BHNS**: One object is a black hole (≥ 3 M☉), the other is a neutron star (< 3 M☉)
- **BNS**: Both objects have mass < 3 M☉

#### **Handling Missing Data:**
- Filled NaN values with median values.

#### **Feature Encoding:**
- Encoded class labels using LabelEncoder (**BBH = 0, BHNS = 1, BNS = 2**).

#### **Splitting Data:**
- 70% Training, 30% Testing

### **3.2 Dealing with Class Imbalance**
- Applied **Random Over-Sampling (ROS)** to balance the dataset before training models.

### **3.3 Model Training & Evaluation**
The following machine learning models were trained:
✅ **AdaBoost Classifier**
✅ **Gradient Boosting Classifier**
✅ **Logistic Regression**
✅ **Random Forest Classifier**
✅ **XGB**

#### **Metrics used for evaluation:**
- **Accuracy**
- **Precision, Recall, F1-Score**
- **Confusion Matrix Visualization**

## **3. Results**
The classification results demonstrated that **Random Forest , XGB and AdaBoost achieved perfect classification performance (100% accuracy, precision, and recall)**, successfully distinguishing between BBH, BNS, and NSBH events. However, this is likely due to the **small test set with only 18 samples (17 BBH, 1 BHNS, and no BNS), which may not generalize well to larger datasets**. 

**Gradient Boosting failed to classify BHNS**, meaning it couldn't predict any instances of the minority class, resulting in lower recall and F1-scores. **Logistic Regression showed a convergence warning**, suggesting it hit the iteration limit; increasing the `max_iter` parameter could help improve its performance. These results highlight the importance of ensemble learning techniques in classifying gravitational wave events effectively. Future work will explore advanced resampling techniques like **SMOTE**, improved feature engineering, and deep learning-based approaches to enhance classification performance.



