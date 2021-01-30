# What are the key features of prior bug assignment approaches?
# A reflection study
***
### Project summary
***
In recent years, the assignment of bug report has been a hot research topic. In the literature, researchers have
proposed various approaches, and some approaches have been
evaluated on thousands of real bugs that are collected from
commercial companies. As bug reports are mostly written in
natural languages, the prior approaches typically use natural language processing (NLP) to handle textual features. But this technical choice is not built on solid empirical evidences. In this experience work, we conduct the first empirical study to explore the impact of textual features in bug triage. 

By enabling and disabling the textual features of a state-of-the-art approach, we analyze their impacts on assigning thousands bug reports of six widely used open source projects. The result is shocking, because we find that instead of improving it, textual features in fact reduce the effectiveness. To figure out the reasons, we make manual inspection. Furthermore, we also analyze which features are important in assigning bug reports.

In this work, we analyze 5 projects in [JIRA](https://issues.apache.org/jira) and list the datasets below.

### Dataset
***
[ALL](./dataset)
[SHIRO](./dataset/SHIRO) [PDFBOX](./dataset/PDFBOX) [LUCENE](./dataset/LUCENE) [HBASE](./dataset/HBASE) [CASSANDRA](./dataset/CASSANDRA)

List of related papers:
-[bug triage](./researchPapers/KeyWord=bugTriage.txt)
-[bug assignment](./researchPapers/KeyWord=bugAssignment.txt)
-[change request triage](./researchPapers/KeyWord=changeRequestTriage.txt)
-[change request assign](./researchPapers/KeyWord=changeRequestAssign.txt)

### Tools
***
[WEKA, a mature machine learning environment](https://www.cs.waikato.ac.nz/ml/weka/)

As Jonsson[<sup>1</sup>](#refer-anchor-1) used WEKA in his research work, we also leverage this tool for reproduction by following the preprocessing steps in his work.

### Results
***
**Effectiveness of Texts and Explanations**

Compared with the baseline, we find that disabling its NLP techniques improves its effectiveness by 8%, and reduces its execution time by 89%.

After manual inspections, we find two reasons:
-1. The classic textural analysis techniques are insufficient to handle bug reports
-2. Some bug reports have no useful descriptions to determine assignments

**Key Features**

<table>
   <tr>
      <td>CASSANDRA</td>
      <td>HBASE</td>
      <td>LUCENE</td>
      <td>PDFBOX</td>
      <td>SHIRO</td>
      <td></td>
      <td>ALL</td>
   </tr>
   <tr>
      <th>Commenter</th>
      <th>Commenter</th>
      <th>Commenter</th>
      <th>Commenter</th>
      <th>Commenter</th>
      <td></td>
      <th>Commenter</th>
   </tr>
   <tr>
      <th>Reporter</th>
      <th>Reporter</th>
      <th>Reporter</th>
      <th>Version</th>
      <th>Reporter</th>
      <td></td>
      <th>Reporter</th>
   </tr>
   <tr>
      <th>Component</th>
      <th>Component</th>
      <th>Version</th>
      <th>Reporter</th>
      <th>Version</th>
      <td></td>
      <th>Version</th>
   </tr>
   <tr>
      <th>Priority</th>
      <td>Platform</td>
      <th>Component</th>
      <th>Component</th>
      <td>Component</td>
      <td></td>
      <th>Component</th>
   </tr>
   <tr>
      <td>Platform</td>
      <td>Priority</td>
      <td>Platform</td>
      <td>Platform</td>
      <td>Platform</td>
      <td></td>
      <td>Platform</td>
   </tr>
   <tr>
      <td>Version</td>
      <td>Version</td>
      <td>Priority</td>
      <td>Priority</td>
      <td>Priority</td>
      <td></td>
      <td>Priority</td>
   </tr>
   <tr>
      <td>Summary</td>
      <td>Comment</td>
      <td>Comment</td>
      <td>Comment</td>
      <td>Comment</td>
      <td></td>
      <td>Project</td>
   </tr>
   <tr>
      <td>Comment</td>
      <td>Summary</td>
      <td>Summary</td>
      <td>Description</td>
      <td>Summary</td>
      <td></td>
      <td>Comment</td>
   </tr>
   <tr>
      <td>Description</td>
      <td>Description</td>
      <td>Description</td>
      <td>Summary</td>
      <td>Description</td>
      <td></td>
      <td>Description</td>
   </tr>
   <tr>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td></td>
      <td>Summary</td>
   </tr>
   <tr>
      <td></td>
   </tr>
</table>

Table shows the key features for individual projects and all projects. The items in bold are key features. The features with higher ranking in the list show higher impact.

### References
<div id="refer-anchor-1"></div>

-[1]  Jonsson, Leif, et al. "[Automated bug assignment: Ensemble-based machine learning in large scale industrial contexts.](https://link.springer.com/article/10.1007/s10664-015-9401-9)" Empirical Software Engineering 21.4 (2016): 1533-1578]
