# Toxicity-Scores-and-Bias-in-Data

### Goal of project:
The purpose of this assignment was to explore the concept of bias by examining and querying the Perspective API released by Google Jigsaw for comment toxicity. The API dataset included a unique comment id, the text of the comment, a toxicity score, and the following binary labels applied by human raters: "toxic," "severe_toxic," "obscene," "threat," "insult," and "identity_hate."

### License:
The dataset of Wikipedia comments made available by Jigsaw, a subsidiary of Google, is available under a CC0 license.

### Labels and thresholds:
After visual inspection of the comments, it appeared there could be some bias with regards to words related to LGBTQ. Based on this inspection, the binary labels selected to examine and query that would be most applicable to LGBTQ were “toxic” and “identity_hate”. Through data parsing of the CSV file in a Jupyter notebook using python, the selected binary labels “toxic” and “identity_hate” were filtered for “1” and the toxicity scores were sorted from smallest to largest in order to determine toxicity score thresholds. The threshold for toxicity score for each of these labels was determined in order to see when scores equal to and above a specific point were considered toxic or abusive. The threshold of the selected labels in the model are as follows:

* toxic:		      0.05439934
* identity_hate:	0.31089434

### Design, performance of tests and hypothesis:
This assignment tests the Perspective's model for bias by looking at performance of the labeled dataset and comparing toxicity scores from submitted original comment queries. Based on the data parsing and exploration, it was hypothesized that Perspective will be less likely to mark LGBTQ-female content as toxic when compared to LGBTQ-male content, identifying (in this context) females as using the word “lesbian” and males using the word “gay”. Queries were submitted to the Perspective API using the provided python code that was edited for my comment queries related to LGBTQ. The submitted comment queries and their toxicity scores for the model are as follows:

![image](https://user-images.githubusercontent.com/99284940/157593513-23dcd9ba-e59c-405e-b683-49573b977b68.png)

### Analysis:
Initial observations show the word “gay” and the phrases “he is gay” and “she is gay” to have the highest toxicity scores out of all the words and phrases queried. However, the word “lesbian” and the phrase “she is lesbian” have much lower scores than the word “gay” and the phrase “she is gay”. This appears to show a toxicity score bias towards the word “gay” with regards to LGBTQ. In order to prove the hypothesis as correct or incorrect queries such as the ones depicted in the tables above were tested. 

First, the general words "lesbian", "gay", "bisexual", "transgender", and "queer" from the first table were submitted as queries. Through using the CSV file and the API, my hypothesis that Perspective would be less likely to mark the LGBTQ-female word “lesbian” as toxic when compared to the LGBTQ-male word “gay” was proven to be correct. The hypothesis was further tested by submitting the specific phrases as shown in the subsequent two tables to the API. The focused LGBTQ-male phrases of "he is gay", "he is bisexual" "he is transgender", and "he is queer" in the second table resulted in toxicity scores that also supported the hypothesis. The focused LGBTQ-female phrases of “she is lesbian”, "she is gay", "she is bisexual", "she is transgender", and "she is queer" in the third table resulted in toxicity scores that also supported the hypothesis. 

Biases in the model based on intuitions or public documentation about how the model was created might exist due to a human rater’s personal ideology and negative or positive feelings about the LGBTQ community. One’s ideology and feelings could influence how they labeled comments and impact whether or not and to what extent comments were scored for toxicity. Another theory about potential bias in the model could be that most human raters were men, and they could take more offense to the word “gay” creating a higher toxicity score for the word and phrases containing that word.



