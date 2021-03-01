## Evaluation
In the evaluation we use the code snippets in the [*adaptation*](https://figshare.com/articles/dataset/ICSE_artifact/7722068/2?file=14372909) dataset constructed by Zhang et al. Their purpose was to study the reuse and adaptation of the code snippets on Stack Overflow and the code snippets were identified by linking code snippets on Stack Overflow to their counterparts in GitHub repositories. The dataset includes 629 Java code snippets and each of them is a method with 32.7 lines of code on average. We choose this dataset as these code snippets have been widely reused and adapted and the reuse and adaptation are based on in-depth comprehension of the code.

To evaluate the accuracy, significance and usefulness of CoLiCo (i.e., **Co**ncept **Li**nking for **Co**de), we conduct a series of experimental studies which answer the following research questions.
- **RQ1 (Accuracy):** How accurate are the concept linkings and explanations uncovered by CoLiCo? Can it outperform existing word sense disambiguation and entity linking approaches for general text?
- **RQ2 (Significance):** How significant can Wikipedia-based concept linking help program comprehension? More specifically, how frequent do the mentions of Wikipedia concepts exist in reusable source code?
- **RQ3 (Usefulness):** Can the linked concepts and extracted explanations help developers comprehend the implicit knowledge behind code?

### RQ1
To evaluate the accuracy of CoLiCo, we randomly select 50 code snippets that are included in different Stack Overflow posts from the adap tation dataset. These code snippets cover different domains such as encryption, network, image, GUI.
We use CoLiCo to identify Wikipedia concept linkings and explanations for the 50 code snippets. We choose a word sense disambiguation and entity linking approach called Babelfy as the baseline.

The results and annotations are as follows:<br>
- [Concept Linking by CoLiCo]()
- [Explanantion Excerption by CoLiCo]()
- [Concept Linking by Babelfy]()

### RQ2
We run CoLiCo for all the 629 code snippets in the dataset and identify 8,520 concept mentions, which are linked to 2,007 distinct Wikipedia concepts. On average, CoLiCo can identify 13.55 concept mentions for each code snippet and one for every 2.5 lines of code (empty lines excluded).

The results of CoLiCo on the all 629 code snippets are as follows:<br>
[Linking Result]()

### RQ3
We use 5 reading and comprehension tasks with 13 questions to evaluate the usefulness of CoLiCo, the tasks and questions are as follows:<br>
[Reading and Comprehension Tasks]()
