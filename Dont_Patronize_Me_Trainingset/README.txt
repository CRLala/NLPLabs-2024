					######################## SEMEVAL 2022 INFORMATION ###########################
					# If you are participating on SemEval 2022-Task 4, this is the training     #
					# set provided for the task (there are no trial and no dev sets provided).  #
					# The full test set can be made avaiable upon request after SemEval 2022    #
					# ends.                                                                     #
					#                                                                           #
					# Further details about the task can be found at the following sites:       #
					# Task website: https://sites.google.com/view/pcl-detection-semeval2022/    #
					# Codalab website: https://competitions.codalab.org/competitions/34344      #
					# Google Group: https://groups.google.com/g/pcl-detection-task4-semeval2022 #
					# Organizers email: semeval2022.task4.pcldetection@gmail.com                #
					#############################################################################

This README.txt file describes version 1.5 of the training set for the dataset "Don't Patronize Me! An Annotated Dataset with Patronizing and Condescending Language towards Vulnerable Communities", an annotated corpus with PCL (Patronizing and Condescending Language) in the newswire domain. The training set of the dataset consists of the following files:

-- README.txt
-- dontpatronizeme_pcl.tsv *
-- dontpatronizeme_categories.tsv *

* Please note that both files have a Disclaimer at the top. The actual data starts at line 5 for both files.

where

-- README.txt is this file.

-- dontpatronizeme_pcl.tsv contains paragraphs annotated with a label from 0 (not containing PCL) to 4 (being highly patronizing or condescending) towards vulnerable communities.
It contains one instance per line with the following format:

	- <par_id> <tab> <art_id> <tab> <keyword> <tab> <country_code> <tab> <text> <tab> <label>

	where
	- <par_id> is a unique id for each one of the paragraphs in the corpus.
	- <art_id> is the document id in the original NOW corpus (News on Web: https://www.english-corpora.org/now/).
	- <keyword> is the search term used to retrieve texts about a target community.
	- <country_code> is a two-letter ISO Alpha-2 country code for the source media outlet.
	- <text> is the paragraph containing the keyword.
	- <label> is an integer between 0 and 4. Each paragraph has been annotated by two annotators as 0 (No PCL), 1 (borderline PCL) and 2 (contains PCL). The combined annotations have been used in the following graded scale:

	0 -> Annotator 1 = 0 AND Annotator 2 = 0
	1 -> Annotator 1 = 0 AND Annotator 2 = 1 OR Annotator 1 = 1 AND Annotator 2 = 0
	2 -> Annotator 1 = 1 AND Annotator 2 = 1
	3 -> Annotator 1 = 1 AND Annotator 2 = 2 OR Annotator 1 = 2 AND Annotator 2 = 1
	4 -> Annotator 1 = 2 AND Annotator 2 = 2

	The experiments reported in the paper consider the following tag grouping: 
	- {0,1}   = No PCL
	- {2,3,4} = PCL

-- dontpatronizeme_categories.tsv is the *PCL multilabel classification* dataset. It contains one instance per line with the following format:

	- <par_id> <tab> <art_id> <tab> <text> <tab> <keyword> <tab> <country_code> <tab> <span_start> <tab> <span_finish> <tab> <span_text> <tab> <pcl_category> <tab> <number_of_annotators>

	- <par_id> is a unique id for each one of the paragraphs in the corpus (matching the ids of the dontpatronizeme_pcl subdataset).
	- <art_id> is the document id in the original NOW corpus (News on Web: https://www.english-corpora.org/now/).
	- <text> is the paragraph containing the keyword.
	- <keyword> is the search term used to retrieve texts about a target community.
	- <country_code> is a two-letter ISO Alpha-2 country code for the source media outlet.
	- <span_start> is the start character position of the span identified as pcl.
	- <span_finish> is the end character position of the span identified as pcl.
	- <span_text> is the span identified as pcl.
	- <pcl_category> is the pcl category** of the <text_span> at position <text>[<span_start>:<span_finish>]
	- <number_of_annotators> is the number of annotators agreeing on that <pcl_category> (1 or 2).




	###################################################################################################
	** For more information about the categories or the dataset, please see our papers:

	--- Pérez-Almendros, Carla, Luis Espinosa Anke, and Steven Schockaert. "Don’t Patronize Me! An Annotated Dataset with Patronizing and Condescending Language towards Vulnerable Communities." Proceedings of the 28th International Conference on Computational Linguistics. 2020. ---

	--- Pérez-Almendros, Carla, Luis Espinosa Anke, and Steven Schockaert. "SemEval-2022 task 4: Patronizing and condescending language detection." Proceedings of the 16th International Workshop on Semantic Evaluation (SemEval-2022). 2022. ---

	###################################################################################################



    ###################################################################################################
	
	For more information and code related to the DPM! dataset, please see 
	https://github.com/Perez-AlmendrosC/dontpatronizeme 
	
	###################################################################################################
