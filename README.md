## Summary for DrugWarningVA package 1.0
#### Author: Yiwen Guo, Yatong Chen
#### Date: 3/20/2018



### Description of the problem

Medication plays an important role in people’s daily lives. Through this project, we want to better understand and analyze the warning sections in drug labels. From the official website of U.S. Food and Drug Administration (FDA), we downloaded related data. To begin with, we divided warning sections into three sub-sections: warnings, contraindications, and boxed warnings. For each of these three categories, we combined the words of all drugs and visualized the key words/phrases through generating word clouds. Then, we developed a language model which classified the tone of these key words into three categories: mild, moderate, and severe. After that, we analyzed the tone across different drug types. For instance, we found that drugs containing arsenicum album tend to have boxed warnings, which can be viewed as an indicator of potential danger of the drugs. Hence, we would classify the tone of drugs with arsenicum album as severe. Note that the project is slightly different from what we proposed earlier. The former focuses on warning sections in drug labels, whereas the latter puts more emphasis on the drug itself. 

#### First part: Visualization and comparison of keywords for different levels of warnings(wordcloud)

The user may wish to visualize the set of key words related to a particular type of warnings (boxed warnings, contraindications, and warnings), which also corresponds to the severe, moderate and mild levels. Then, he or she can call the corresponding function 'boxWarnWC(box_warning_data, keystrings)', 'contraWC(contraindications_data, keystrings)', or 'warningWC(warning_data, keystrings)'. Then, a word cloud of that type will be generated and presented to the user. 

In addition to getting the probabilities of each key word, the user may want to get a bigger picture of comparing key words associated with the three categories. Then he can call the function 'visualizeLangModel(box_warning, contraindications, warnings, language)' and a plot of the following form will appear. Along the line, key words appear in both warnings in a similar frequency. However, words in the top left are more likely to appear in boxed warnings and words in the botttom right are more likely to appear in contraindications and warnings(left and right respectively).
Please refer to the following figures to see the results.




#### Second part: Development of a Language Model classfiying the tone of keywords

The user may want to know the tone of a particular word chosen from the key words set generated from the word cloud. Then, he can call the function 'langModelTable(box_warning_data,  contraindications_data, warning_data, keystrings)' to see all keywords' unnormalized probabilities of the three types of warnings; or he can also call the function 'languageModel(box_warning_data,  contraindications_data, warning_data, keystrings,"input_word")' with "input_word" replaced by his own chosen word. The function will then display probabilities of that word associated with each category of warnings. For instance, if the user calls languageModel(“coronary artery bypass”), the output shows that there is a  probability of 0.729947 that the word is severe, a probability of 0.2392389 that the word is moderate, and a probability of 0.03081411 that the word is mild. Please refer to the following tables for results.


	
#### Third part: Analysis of occurrences of boxed warnings in different ingredients of drugs

The user may want to know the tone of all kinds of ingredients -- namely how often does one particular ingredient appear in a box warning section, which can indicate the potential danger for it. Then, the user can call the function 'ingredientTable(generic_name, raw_box_warning_data)' to view the summary of frequency table for all frequenctly appeared ingredients that has at least appear three times in the box warning section. 

#### Contributions of team members

Yatong pre-processed data into usable forms and analyzed the tone across different drug types. 
Yiwen worked on classifying key words into three categories. 
Yatong and Yiwen collaborated on creating word clouds.


#### Contact information
If you have any questions, please contact Yatong at yatong@stanford.edu






