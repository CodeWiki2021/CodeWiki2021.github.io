<!-- # Replication Package of CoLiCo -->

In this replication package, we show the data used for evaluating CoLiCo (i.e., **Co**ncept **Li**nking for **Co**de) and the munually labeled results.
To evaluate the quality, accuracy, significance and usefulness of CoLiCo, we conduct a series of experimental studies which answer the following research questions.
- **RQ1 (Quality of Offline Mining):** What is the quality of relations mined in the offline phase?
- **RQ2 (Accuracy of Online Linking):** How accurate are the concept linkings and explanations uncovered by CoLiCo? Can it outperform existing word sense disambiguation and entity linking approaches for general text?
- **RQ3 (Significance):** How frequently do the mentions of Wikipedia concepts occur in reusable source code? How significantly do they affect the program comprehension?
- **RQ4 (Usefulness):** Can the linked concepts and extracted explanations help developers comprehend the implicit knowledge behind code?

For research questions (i.e., RQ2, RQ3 and RQ4) involving online linking, we use the code snippets in the [*adaptation*](https://figshare.com/articles/dataset/ICSE_artifact/7722068/2?file=14372909) dataset constructed by Zhang et al.
Their purpose was to study the reuse and adaptation of the code snippets on Stack Overflow and the code snippets were identified by linking code snippets on Stack Overflow to their counterparts in GitHub repositories.
The dataset includes 629 Java code snippets and each of them is a method with 32.7 lines of code on average.
We choose this dataset as these code snippets have been widely reused and adapted and the reuse and adaptation are based on in-depth comprehension of the code.

### RQ1
To evaluate quality of the abbreviation relations mined in offline phase, we select a manually constructed [*abbreviation dataset*](https://github.com/liuhuigmail/ParameterAbbreviation) provided by Jiang et al. for the evaluation.
We filter out the full names that are not a part of any Wikipedia concepts because these full names (e.g., "creation exception") usually represent project-specific concepts and are meaningless for our purposes.
The remaining 549 full names and their abbreviations are used as golden set.

To We randomly sample 50 aggregation relations for the evaluation. For each sampled aggregation relation, we randomly retrieve 100 distinct code snippets (not used for the mining of aggregation relations) that contain all the parts of the aggregation relation as its code contexts. The aggregation relation is considered to be meaningful if the combination of its parts (e.g., "r", "g" and "b") represents the meaning of its whole (e.g., "RGB") in at least one code snippet.
The results and manual annotations of aggregation relations are as follows:<br>
- [Aggregation Relations](./rq1_CoLiCo_linking.zip)


### RQ2
To evaluate the accuracy of CoLiCo's online linking, we randomly select 50 code snippets that are included in different Stack Overflow posts from the adap tation dataset. These code snippets cover different domains such as encryption, network, image, GUI.
We use CoLiCo to identify Wikipedia concept linkings and explanations for the 50 code snippets. We choose a word sense disambiguation and entity linking approach called Babelfy as the baseline.
The results and annotations are as follows:<br>
- [Concept Linking by CoLiCo](./rq1_CoLiCo_linking.zip)
- [Explanantion Excerption by CoLiCo](./rq1_CoLiCo_explanation.zip)
- [Concept Linking by Babelfy](./rq1_Babelfy_linking.zip)

### RQ3
We run CoLiCo for all the 629 code snippets in the dataset and identify 8,520 concept mentions, which are linked to 2,007 distinct Wikipedia concepts. On average, CoLiCo can identify 13.55 concept mentions for each code snippet and one for every 2.5 lines of code (empty lines excluded).
The results of CoLiCo on the all 629 code snippets are as follows:<br>
- [Linking Result](./rq2_linking_results.zip)

### RQ4
We use 5 reading and comprehension tasks with 13 questions to evaluate the usefulness of CoLiCo, the tasks and questions are as follows:<br>
- [Reading and Comprehension Tasks](./rq4_tasks.md)
