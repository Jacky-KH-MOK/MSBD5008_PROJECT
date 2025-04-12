# MSBD5008: Introduction to Social Computing

## Project

- Each group should have 4 students.
- You can get the data from:
  - [Stanford Large network dataset collection](https://snap.stanford.edu/data/)
  - [Kaggle](https://www.kaggle.com/datasets) (in particular, note the new [datasets on COVID-19](https://www.kaggle.com/covid19))
  - [KDD archive](https://kdd.ics.uci.edu/): e.g., web data
  - [Google dataset search](http://toolbox.google.com/datasetsearch)
  - [Elsevier datasearch](https://datasearch.elsevier.com/#/)
  - Paper authors
  - The web
  - Others (e.g., from your contacts)
- The graph should have at least 500 nodes.
- You have to analyse the data (examine the degree distribution, path length, clustering properties, etc), and then perform one or more of the following tasks:
  - Node classification
  - Graph classification
  - Link prediction
  - Clustering (community detection)
  - Other graph-related tasks
- The report should be formatted using the [ACM template](https://www.acm.org/publications/proceedings-template).  
  Each report should have 7–8 pages, including all figures and tables; plus additional pages for references and appendix (if applicable).
- Grading will be based on:
  - Technical quality
  - Novelty
  - Performance results
  - Clarity
- Schedule (to be announced)
- Presentation guideline (to be announced)

## Dataset

<details> 
<summary><strong> Social circles: Facebook (https://snap.stanford.edu/data/ego-Facebook.html) </strong></summary>
  
This dataset consists of 'circles' (or 'friends lists') from Facebook. Facebook data was collected from survey participants using this Facebook app. The dataset includes node features (profiles), circles, and ego networks.

Facebook data has been anonymized by replacing the Facebook-internal ids for each user with a new value. Also, while feature vectors from this dataset have been provided, the interpretation of those features has been obscured. For instance, where the original dataset may have contained a feature "political=Democratic Party", the new data would simply contain "political=anonymized feature 1". Thus, using the anonymized data it is possible to determine whether two users have the same political affiliations, but not what their individual political affiliations represent.

| Metric                                | Value                     |
|---------------------------------------|---------------------------|
| Nodes                                 | 4039                      |
| Edges                                 | 88234                     |
| Nodes in largest WCC                  | 4039 (1.000)              |
| Edges in largest WCC                  | 88234 (1.000)             |
| Nodes in largest SCC                  | 4039 (1.000)              |
| Edges in largest SCC                  | 88234 (1.000)             |
| Average clustering coefficient        | 0.6055                    |
| Number of triangles                   | 1612010                   |
| Fraction of closed triangles          | 0.2647                    |
| Diameter (longest shortest path)      | 8                         |
| 90-percentile effective diameter      | 4.7                       |

</details>

<details> 
<summary><strong> email-Eu-core network (https://snap.stanford.edu/data/email-Eu-core.html) </strong></summary>
  
The network was generated using email data from a large European research institution. We have anonymized information about all incoming and outgoing email between members of the research institution. There is an edge (u, v) in the network if person u sent person v at least one email. The e-mails only represent communication between institution members (the core), and the dataset does not contain incoming messages from or outgoing messages to the rest of the world.

The dataset also contains "ground-truth" community memberships of the nodes. Each individual belongs to exactly one of 42 departments at the research institute.

This network represents the "core" of the email-EuAll network, which also contains links between members of the institution and people outside of the institution (although the node IDs are not the same).


| Metric                                | Value               |
|---------------------------------------|---------------------|
| Nodes                                 | 1005                |
| Edges                                 | 25571               |
| Nodes in largest WCC                  | 986 (0.981)         |
| Edges in largest WCC                  | 25552 (0.999)       |
| Nodes in largest SCC                  | 803 (0.799)         |
| Edges in largest SCC                  | 24729 (0.967)       |
| Average clustering coefficient        | 0.3994              |
| Number of triangles                   | 105461              |
| Fraction of closed triangles          | 0.1085              |
| Diameter (longest shortest path)      | 7                   |
| 90-percentile effective diameter      | 2.9                 |

</details>
