# FinancialTopicModelling

*FinancialTopicModelling* is a java application which does topic modelling with Latent Dirichlet Allocation (LDA). Unlike the project "FinancialDocumentClassifier" this application is not able to label the files. It seperates the topics with respect to the occurance of words.

The library from [MALLET] is used during the development.

*FinancialTopicModelling* is based on the example class "TopicModel" on MALLET.

For safety concerns, the financial documents are replaced with Onur Dayıbaşı's Turkish [blogs].

*FinancialTopicModelling is used for a summer internship project.

### Resources for FinancialTopicModelling
The resources should be added under a folder FinancialTopicModelling/sampleData/ [FILE]

*FinancialTopicModelling* contains a 79 file dataset from 4 different main topics, under sampleData/tr
  
Although the topics are not labeled with this application, the main topics in the dataset for testing are:

- AWS
- Games & Graphics
- IOS and Mobile applications
- Software Design Patterns

**It is recommended to have equal amount of resources from every topic, in order to increase reliability.

### Stopwords

Since the application is used to find the topic distribution of Turkish financial documents, the stoplist contains Turkish words. However, the stoplist can be edited for any language and used accordingly.

By default, the application uses the Turkish stopwords from the class *TokenSequenceRemoveStopwords*, however you can also use stopwords from a txt file under the location: *stoplists/ [FILE]* 
(you should edit the code accordingly)

### Process of FinancialTopicModelling
Once you have added your resources under sampleData/ [FILE] 

and added your stoplist *(optional)* you can run the application for topic modelling.


The application asks 3 inputs from the user;

- Number of *topics* to analyze
- Number of *threads*
- Number of *iterations*

The test is advised to run with **4** main **topics**, **2 threads** and **1000 iterations**. 
(This can be adjusted according to the dataset)

According to these inputs, *FinancialTopicModelling* gives an output of most frequent words under every main topic.

*FinancialTopicModelling* runs successfully on multilingual texts.

### INFO - Using MALLET for Topic Modelling

MALLET contains a toolset for topic modelling. The [tutorial] provides information about how to set MALLET on your computer and use topic modelling for your own dataset. 

Furthermore about using MALLET, you should locate your MALLET file under C:

You should add your dataset and stopwords accordingly.

Once you have done that, the 2 basic commands you should run for topic modelling can be summarized as,

    bin\mallet import-dir --input C:\mallet-2.0.8>bin\mallet import-dir --input C:\mallet-2.0.8\sample-data\web\tr --output data\tutorial.mallet --keep-sequence --remove-stopwords

and
    
    bin\mallet train-topics --input data\tutorial.mallet --num-topics 4 --optimize-interval 80 --output-doc-topics data\docTopics.txt --xml-topic-report data\topicReport.xml

The outputs:

- docTopics.txt
- topicReport.xml

provide useful information for data analysis.

According to the observations, the results of topic modelling by using MALLET over the command promt, were higher and faster than using *FinancialTopicModelling*. 



   [MALLET]: <http://mallet.cs.umass.edu/>
   [tutorial]: <http://programminghistorian.org/lessons/topic-modeling-and-mallet>
   [blogs]: <https://medium.com/@odayibasi/>
