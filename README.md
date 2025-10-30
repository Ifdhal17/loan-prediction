# Loan Prediction 

This project is a case study in financial technology industries. This model was trained to classy loan applications as **Approved (1)** or **Rejected (0)**.

**Background & Purpose**
Main problems in a financial technology industries is a risk of Non Performing Loan (NPL). The manual evaluation process for eligibility time is too much wasting time and can be incosistent because there's a chance that will be a human error.

So this project is aiming to create an *automated credit scoring* for helping the company quickly and accurately identify high risk applicants and reducing Non Performing Loan applicants, also acceletate the decision making process.

The dataset that i've been using is from kaggle : https://www.kaggle.com/datasets/ninzaami/loan-predication

**Workflow**

  1. Data Cleaning :
     - Identified and handling the missing values
       
  2. Exploratory Data Analysis :
     - Finding pattern and insight from the cleaned data
       The most feature that has a good predictor is a Credit History
       <img width="571" height="433" alt="image" src="https://github.com/user-attachments/assets/e462b8a1-d66c-4177-aeba-393916cf204c" />
       As we can see if the person has a bad credit history (0) the probability of being                rejected is higher, but if the person has a good credit history (1.0) the probability of         being approved is high but it doesn't rule out the possibility of being rejected, usually        due to other factors such as Self Employed, Applicant Income, etc...
       
  3. Adding Feature Engineering
     In order to help the Machine Learning process, I created a new feature called
       - **Total_Income** by combining **ApplicantIncome** and **CoapplicantIncome**.  
       - **Loan_to_Income_Ratio** to measure the loan burden relative to total income, using the formula: **(LoanAmount / Total_Income)**.
       - **Loan_Term_Ratio** as an estimate of the monthly installment, calculated using the formula: **(LoanAmount / Loan_Amount_Term)**.
       
  4. Modelling
     - Splitting data into 80/20 (Train/Test)
     - Check & Evaluate initial model using Logistic Regression and Random Forest
     <img width="558" height="561" alt="image" src="https://github.com/user-attachments/assets/1b86f3fc-79f4-40b7-92fb-61a14c14537c" />
     As we can see there's a problem that has been identified. The Data is imbalanced, there are more "Approved" (1.0) samples than "Rejected" (0) ones. So the initial model is bias and has a very low recall class for "Rejected" (0), only 0.42 it means the model fails to detect 58% of high rick applicants.

  5. Model Improvement
     - Resampling the data using SMOTE: Balancing the training dataset by generating synthetic data for class "Rejected" (0).
     - Feature Engineering: Creating new features that are more logical from business perspective (Total_Income, Loan_to_Income_Ratio, and Loan_Term_Ratio) so it can be more predictive.
     <img width="551" height="559" alt="image" src="https://github.com/user-attachments/assets/b6ee05c9-7526-403a-ae47-161472d0a346" />
     Even though the accuracy has been decreased but the recall of "Rejected" has been improved, it means the model isn't biased, more stable and balanced so this model is the best for identify high risk applicants.

**Result and Evaluation**


  



       

