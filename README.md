# MSBD5008: Introduction to Social Computing

## Project
- Analyse the data (examine the degree distribution, path length, clustering properties, etc), and then perform one or more of the following tasks:
  - Link prediction
  - Clustering (community detection)

## Dataset

### Spotify Artist Feature Collaboration Network [[Link](https://www.kaggle.com/datasets/jfreyberg/spotify-artist-feature-collaboration-network)]

#### A network-dataset covering features between leading global artists on spotify.

This dataset contains artist data for ~20k artists whose songs made it to the Spotify weekly charts and ~136k additional artists who had at least one feature with at least one of the chart artists.

Further, information on the occurrence of features between all of these artists is included, allowing to generate a network with 135k+ musicians as nodes and 300k+ collaboration edges between them.


## edges.csv

Edges (features) between artists in nodes.csv. Edges are undirected and only stored once. Note that `id_0 < id_1` according to alphabetical order, i.e. a collaboration between artist A and artist B is stored as `id_0:A, id_1:B`.

Note that only the features of the original 20k seed artists were scraped, i.e. non-seed artists do not have features between them in this dataset even if they have them in reality.


| Column   | Description                                                                               |
| :------- | :---------------------------------------------------------------------------------------- |
| `id_0` | Spotify ID of the first artist in a collaboration (alphabetically first ID of the pair)   |
| `id_1` | Spotify ID of the second artist in a collaboration (alphabetically second ID of the pair) |

## nodes.csv

Artist information, scraped from the Spotify API and kworb.net.


| Column         | Description                                                          |
| :------------- | :------------------------------------------------------------------- |
| `spotify_id` | Unique Spotify identifier for the artist                             |
| `name`       | Name of the artist                                                   |
| `followers`  | Number of followers (according to Spotify API)                       |
| `popularity` | Artist popularity (according to Spotify API)                         |
| `genres`     | List of genres associated with the artist                            |
| `chart_hits` | List showing the number of Spotify chart hits in different countries |
