# Search4Code: Web queries dataset for code search

Search4Code is a large-scale web query based dataset of code search queries for C# and Java. The Search4Code data is mined from Microsoft Bing's anonymized search query logs using weak supervision technique. We hope the dataset will aid future research in the area of Natural Language based Code Search. We briefly describe the data below, for more details, refer to [our paper](https://arxiv.org/abs/2011.11950) (under review).

* [Dataset Information](#dataset-information)
* [Dataset Schema](#dataset-schema)


## Dataset Information

Search4Code dataset is composed of real-world user queries and the corresponding most frequently clicked URLs. Each query additionally has a label denoting whether the query has a code search intent or not, as predicted by the weak supervision model described in the paper. 

Currently, the Search4Code dataset contains 6596 Java queries and 4974 C# queries.

Here are some of the advantages of Search4Code dataset:
- Real queries: The queries are sampled from anonymized Bing search logs. We believe this provides a realistic representation of how individuals would search for code.
- Click URLs: Each query has a list of the three most frequently clicked URLs from the search results. For a given search query, the most frequently clicked URLs are representative of search results that provide satisfactory solutions.
- Popularity score: Each query is assigned a popularity rank based on the frequency of occurrence. 
- Large scale: The dataset contains thousands of queries. Hence, enabling the use of more complex models that require large amounts of training data.

Since the dataset contains both code-search and non code-search queries, it could also be used to analyze other user intents, as described in our [prior work](https://arxiv.org/abs/1912.09519). 


## Dataset Schema

Each data file has the following fields:

Field | Description
------------ | -------------
Id | Unique GUID to reference a query.
QueryString | Raw search query.
TopClickedUrls | The top 3 most frequently clicked on result urls.
PopularityRank | A popularity score based on the frequency of the query in the raw data. Most popular query is ranked 1.
PredictedLabel | Boolean label where 'True' denotes the query has a code search intent.

You can find a sample of the data [here](https://github.com/microsoft/Search4Code/blob/main/data/java_sample.csv).

## Terms of Use:  

Please see the LICENSE file for more details. If you choose to use the data, please cite:

```
@misc{rao2020code,
      title={Code Search Intent Classification Using Weak Supervision}, 
      author={Nikitha Rao and Chetan Bansal and Joe Guan},
      year={2020},
      eprint={2011.11950},
      archivePrefix={arXiv},
      primaryClass={cs.SE}
}
```

## Contact:

Please contact the authors of the [paper](https://arxiv.org/abs/2011.11950), if you have any questions or feedback.