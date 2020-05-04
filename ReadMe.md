# The Myth of NLP and What Matters in Bug Triage
***
### Project summary
***
Bug report assignment has been a hot research topic that researchers have proposed various approaches. Despite of their success, there is adequate room for improvement. To the best of our knowledge, no prior study analyzes which features are more important, nor the insights behind such features. So, in this project, we conduct an empirical study to explore what matters in assigning bug reports. We introduce a classical feature selection approach to explore the impact of NLP techniques in bug triage.

In this project, we analyzed of 5 projects in [JIRA](https://issues.apache.org/jira)

### Dataset
***
[SHIRO](/dataset/shiro.csv) [PDFBOX](/dataset/pdfbox.csv) [LUCENE](/dataset/lucene.csv) [HBASE](/dataset/hbase.csv) [CASSANDRA](/dataset/cassandra.csv)

[List of related papers](/research papers/Paper list.xlsx)

### Tools
***
[WEKA, a mature machine learning environment](https://www.cs.waikato.ac.nz/ml/weka/)

As Jonsson used WEKA in his research work, we also leverage this tool for reproduction by following the preprocessing steps in his work.