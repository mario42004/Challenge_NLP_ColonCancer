# Challenge_NLP_ColonCancer
Code for the challenge of Colon Cancer detection
<h3>Summary</h3>
In this Challenge, we used the Codiesp database to apply two NLP approaches for quick identification of colon cancer, such as, text summarization and
classification. In terms of recall, Bart model obtained 87% for the text summarization job, and two trainings were done for the
classification task, such on the summaries manually made by experts on the basis of the Codiesp dataset and on the original text of
the same database. The Distilbert base uncased model performed with 83% of accuracy on the summaries subset and 67% of
accuracy on the non-summarized documents.

<h3>Dataset</h3>
The “CodiEsp”[1] corpus or data used for this AI4EU challenge consists of 1000 files including clinical case studies manually selected by a practicing physician and a clinical documenter, comprising 16,504 sentences and 396,988 words, with an average of 396.2 words per clinical case. Interestingly, this type of narrative has properties of both biomedical and medical literature and clinical records. Moreover, the clinical cases are not limited to a single medical discipline, and thus cover a variety of medical topics, including oncology, urology, cardiology, pulmonology, or infectious diseases. The “CodiEsp” corpus is distributed as plain text in UTF8 encoding, where each clinical case is stored in a unique file whose name is the clinical case identifier [2]. The 1000 files available on the “CodiEsp” database are all coded in ICD-10 code. In ICD-10, the codes are grouped into disease families and subfamilies in the structure of a tree.  The disease family that colon cancer (the target of this challenge) belongs to, is Neoplasm [4].

Looking at the all 1000 available files in the “CodiEsp” database, there are only 12 texts for colon cancer ,  48 files for all types of cancer and 348 files for all neoplasms.


<h3>Detailed method to select 12 colon cancer files.</h3>
The “CodiEsp” downloaded repository has the directory structure. To select the important cases regarding the AI4EU challenge, we had to identify the ICD-10 codes related to all the clinical cases belonging to the colon cancer category. In this way, according to 2021 ICD-10-CM/PCS Medical Coding [3], malignant neoplasm of the colon is coded with C18. Clinical information refers to these cases as primary or metastatic malignant neoplasm involving the colon; besides the representative examples that include carcinoma, lymphoma and sarcoma. 

In the Test, Dev and Train folders, CodiEsp provides, besides the folders with the files (text_files and text_files_en), information about ICD10-CM (Diagnosis) and ICD10-PCS (Procedure). This information was used  to identify each clinical case. The codes are delivered in the devD and devP .tsv files respectively with subsequent information to the clinical case ID, 
separated by tabs. According to this information, we have selected the colon cancer cases in the Test, Dev and Train folders. To do this, a Python script was created to read the file (devD), looking for the clinical cases in all 3 folders labelled with C18. They were selected by the ID of the clinical case, and then, they were relocated in a colon_cancer_texts created folder . 

<h3>References</h3>
[1]MIRANDA-ESCALADA, Antonio, et al. Overview of Automatic Clinical Coding: Annotations, Guidelines, and Solutions for non-English Clinical Cases at “CodiEsp” Track of CLEF eHealth 2020. En CLEF (Working Notes). 2020 <br/>
[2] MIRANDA-ESCALADA, Antonio; GONZALEZ-AGIRRE, Aitor. CodiEsp: Clinical Case Coding in Spanish Shared Task (eHealth CLEF 2020). 2020. <br/>

[3] KUSNOOR, Sheila V., et al. A narrative review of the impact of the transition to ICD-10 and ICD-10-CM/PCS. JAMIA open, 2020, vol. 3, no 1, p. 126-131.<br/>
[4] PECERE, Silvia, et al. Accuracy of colon capsule endoscopy for advanced neoplasia. Gastrointestinal endoscopy, 2020, vol. 91, no 2, p. 406-414. e1.

