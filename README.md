# FinSBD_RFC_r1
This is a Sentence Boundary Detection task for detecting the beginning and ending boundaries of domain-specific documents, i.e. scanned Financial prospectuses.

====

FinSBD-2019 Shared Task

# team name: PolyU_CBS-CFA_RFC
# team members: Churen Huang, Mingyu Wan, Emmanuele Chersoni, Rong Xiang, Natalia Klyueva, Bin Miao

----------------- System Description
We use the Random Forest Classifier (sklearn rfc) to train and test, with the following optimized parameter settings:
min_samples_split = 8, max_features = “log2”, oob_score = True, random_state = 10. 

Importantly, we do cross-lingual training (train on both en and fr Train datasets), as well as engineering seveal key features for fitting the model. 
The features we use for this task include feature fusion of punctuations, initially captalized words, acronyms, _Enter(\n), digits, letters (including Roman numbers) and pos tags (UPOS tagset). 

For run1, we post-process the predictions by doing rule-based validation with keyword list extracted from the Train and Dev datasets. 
