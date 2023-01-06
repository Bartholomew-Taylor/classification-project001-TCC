# classification-project001-TCC
TelCo churn classification project

Main project objective: dertermine the main drivers of churn in the provided customer dataset
to inform executives and marketing teams on how to reduce churn
Refine model to an MVP that performs better than baseline (74% accuracy)

Hypotheses (generated from exploration findings):
    There is a dependence between total charges and churn
    There is a dependence between internet service type and churn
    There is a dpendence between contract type and churn
    There is a correlation with age and churn

Data dictionary:
        gender: categorical; binary
        senior_citizen: categorical; binary
        partner: categorical; binary
        dependents: categorical; binary
        tenure: numerical; discrete; in months
        phone_service: categorical; binary
        multiple_lines: categorical; binary
        online_security: categorical; binary
        online_backup: categorical; binary
        device_protection: categorical; binary
        tech_support: categorical; binary
        streaming_tv: categorical; binary
        streaming_movies: categorical; binary
        paperless_billing: categorical; binary
        monthly_charges: numerical; float; discrete
        churn: categorical; binary
        contract_type: categorical; ternary
        internet_service_type: categorical; ternary
        payment_type: categorical; quinary
        signup_date: discrete, numerical; date
        total_charges: discrete, numerical; changed to float as product of tenure and monthly charges



Project Planning and Pipeline:
    Identified goal of finding support for what features in data set drives churn
    Data acquisition and preparation accomplished through functions in acquire.py and prepare.py
        Customer ID removed from data set before analysis and testing
        signup_date also not used
    Data exploration accomplished through visualizations, feature isolation, and statistical analysis
        contract type, service type, charges, and age appear to have a trend when controlling for churn
        analysis of the former three show dependence in Chi square test
        age appears to have dependence but isn't explicit enough for deep analysis
    Decision Tree, KNN, and Random Forest selected for initial modeling
    All perform better than baseline with Random Forest performing the best

    
Instruction for Recreation (module and notebook sections):
    Random seed: 99
    Alpha: 0.05
    See acquire file for acquisition functions used
    See prepare file for modules, cleaning of data, and generation of dummy features from dataset.
    See modeling sections of final notebook for modeling specs used.

    

Key Findings and Conclusions:
        Importance of fiber optics and contract type weigh heavily as features in the Random Forest model
        Exploration also revealed that the majority of churned customers were also fiber optics customers
            with high monthly bills and month to month contracts

