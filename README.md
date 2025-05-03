# MSBD5008: Introduction to Social Computing

## Project
- Analyse the data (examine the degree distribution, path length, clustering properties, etc), and then perform the following tasks:
  - Link prediction
  - Clustering (community detection)

## Dataset

### Spotify Artist Feature Collaboration Network [[Link](https://www.kaggle.com/datasets/jfreyberg/spotify-artist-feature-collaboration-network)]

#### A network-dataset covering features between leading global artists on spotify.

This dataset contains artist data for ~20k artists whose songs made it to the Spotify weekly charts and ~136k additional artists who had at least one feature with at least one of the chart artists.

Further, information on the occurrence of features between all of these artists is included, allowing to generate a network with 135k+ musicians as nodes and 300k+ collaboration edges between them.


### edges.csv

Edges (features) between artists in nodes.csv. Edges are undirected and only stored once. Note that `id_0 < id_1` according to alphabetical order, i.e. a collaboration between artist A and artist B is stored as `id_0:A, id_1:B`.

Note that only the features of the original 20k seed artists were scraped, i.e. non-seed artists do not have features between them in this dataset even if they have them in reality.


| Column   | Description                                                                               |
| :------- | :---------------------------------------------------------------------------------------- |
| `id_0` | Spotify ID of the first artist in a collaboration (alphabetically first ID of the pair)   |
| `id_1` | Spotify ID of the second artist in a collaboration (alphabetically second ID of the pair) |

### nodes.csv

Artist information, scraped from the Spotify API and kworb.net.


| Column         | Description                                                          |
| :------------- | :------------------------------------------------------------------- |
| `spotify_id` | Unique Spotify identifier for the artist                             |
| `name`       | Name of the artist                                                   |
| `followers`  | Number of followers (according to Spotify API)                       |
| `popularity` | Artist popularity (according to Spotify API)                         |
| `genres`     | List of genres associated with the artist                            |
| `chart_hits` | List showing the number of Spotify chart hits in different countries |


## Notebooks

### PROJECT_CODE_Predict.ipynb

This notebook uses a Graph Neural Network (GNN) with the Deep Graph Library (DGL) to predict potential future collaborations between Spotify artists.

**Workflow:**

1.  **Data Loading:** Loads artist collaboration data (nodes and edges) from a Kaggle dataset.
2.  **Preprocessing:** Filters for artists with chart hits and extracts the largest connected component of the collaboration graph.
3.  **Feature Engineering:** Calculates node features like degree, centrality measures, clustering coefficient, and follower count.
4.  **Link Prediction Model:**
    *   Splits existing collaborations (edges) into training, validation, and test sets.
    *   Generates negative samples (non-existing collaborations).
    *   Trains a GNN (GraphConv) model to predict the probability of a link between two artists.
5.  **Evaluation:** Assesses model performance using AUC and accuracy on the test set.
6.  **Prediction:** Demonstrates predicting the most likely collaborators for a given artist (e.g., Taylor Swift).

### PROJECT_CODE_Analysis.ipynb

This notebook performs a comprehensive analysis of the Spotify artist feature collaboration network using NetworkX.

**Workflow:**

1.  **Data Loading:** Loads artist data (nodes) and collaboration data (edges) from a Kaggle dataset.
2.  **Preprocessing:** Filters for artists with chart hits and extracts the corresponding subgraph. Cleans genre information.
3.  **Graph Creation:** Constructs a NetworkX graph representing artist collaborations.
4.  **Network Characterization:**
    *   Calculates basic properties (nodes, edges, density).
    *   Analyzes connectivity and identifies the largest connected component (LCC).
    *   Examines the degree distribution (linear and log-log scales).
    *   Computes path length metrics (average shortest path, diameter) on the LCC.
    *   Analyzes clustering (global, average local, distribution, degree vs. clustering).
    *   Calculates centrality measures (degree, betweenness, closeness) on the LCC and identifies key artists.
    *   Performs community detection using the Louvain algorithm on the LCC and analyzes community structure.
    *   Assesses small-world properties by comparing the network to a random graph.
5.  **Visualization:** Creates a visualization of a subgraph containing the most central artists.
6.  **Summary:** Provides a consolidated summary of the key network characteristics.