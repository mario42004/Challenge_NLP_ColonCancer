# Challenge_NLP_ColonCancer
Code for the challenge of Colon Cancer detection

<h3>Detailed method to select 12 colon cancer files.</h3>
The “CodiEsp” downloaded repository has the directory structure. To select the important cases regarding the AI4EU challenge, we had to identify the ICD-10 codes related to all the clinical cases belonging to the colon cancer category. In this way, according to 2021 ICD-10-CM/PCS Medical Coding [1], malignant neoplasm of the colon is coded with C18. Clinical information refers to these cases as primary or metastatic malignant neoplasm involving the colon; besides the representative examples that include carcinoma, lymphoma and sarcoma. 

In the Test, Dev and Train folders, CodiEsp provides, besides the folders with the files (text_files and text_files_en), information about ICD10-CM (Diagnosis) and ICD10-PCS (Procedure). This information was used  to identify each clinical case. The codes are delivered in the devD and devP .tsv files respectively with subsequent information to the clinical case ID, 
separated by tabs. According to this information, we have selected the colon cancer cases in the Test, Dev and Train folders. To do this, a Python script was created to read the file (devD), looking for the clinical cases in all 3 folders labelled with C18. They were selected by the ID of the clinical case, and then, they were relocated in a colon_cancer_texts created folder . 

<h3>References</h3>
[1] KUSNOOR, Sheila V., et al. A narrative review of the impact of the transition to ICD-10 and ICD-10-CM/PCS. JAMIA open, 2020, vol. 3, no 1, p. 126-131.
