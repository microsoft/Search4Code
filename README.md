# Search4Code: Web queries dataset for code search

Search4Code is a dataset built using weak supervision on data extracted from anonymized Microsoft's Bing search engine logs to promote further research in the area of Natural Language based Code Search. We briefly describe the data below, for more details, refer to [our paper](LINK TO ARXIV) (under review).

* [Dataset Information](#dataset-information)
* [Dataset Schema](#dataset-schema)


## Dataset Information

Search4Code is a large-scale dataset focused on the area of natural language to code search. We provide a dataset composed of real-world user queries and the corresponding click urls. Each query also has a label, predicted using the weak supervision model described in the paper, denoting whether the query has a code search intent or not. Since the dataset contains both code-search and non code-search queries, it could also be used to analyze other user intents, as shown in our [prior work](https://arxiv.org/abs/1912.09519).

Currently the Search4Code dataset contains 6596 Java queries. Please note that we will be soon adding a dataset for C# queries as well.

What are some of the advantages of Search4Code dataset:
- Real queries: All queries are sampled from anonymized Bing queries which we believe is a realistic representation of how individuals would search for code.
- Click URLs: All queries have have a list of the the most frequently clicked urls from the search results. Since queries are grouped, the most frequently clicked url presents a good "solution" to the search query that most users selected.
- Popularity score: Each query is assigned a popularity rank calculated based on it's frequency. 
- Large scale: Currently the dataset contains thousands of queries with plans to further increase it as more data is run through the pipeline.


## Dataset Schema

Each data file has the following fields:

Field | Description
------------ | -------------
Id | Unique GUID to reference a query.
QueryString | Raw search query.
TopClickedUrls | The top 3 most frequently clicked on result urls.
PopularityRank | A popularity score based on the frequency of the query in the raw data. Most popular query is ranked 1.
PredictedLabel | Boolean label where 'True' denotes the query has a code search intent.


## Terms of Use:  

Please see the LICENSE file for more details. If you choose to use the data, please cite:

```
@inproceedings{rao-2020-codeintent,
    title = "Code Search Intent Classification Using Weak Supervision",
    author = "Nikitha Rao, Chetan Bansal and Joe Guan",
    booktitle = "arXiv",
    year = "2020",
    address = "Online",
    url = "TODO",
}
```

## Contact:

Please contact the authors of the paper if you have any questions or feedback.