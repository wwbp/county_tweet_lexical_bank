# County Tweet Lexical Bank

County level word and topic loading derived from a 10% Twitter sample from 2009-2015. Anonymized linguistic features extracted from over 1.5 billion English U.S County mapped tweets.

Read the full publication [here](http://wwbp.org/publications.html#p122). 

## Data

Available in both csv format and as a MySQL dump. All tables are in sparse (long) format.

### Unigrams

Approximately 24,000 most frequenct unigrams. All urls replaced with `<URL>` and @-mentions replaced with `<USER>`.

* `group_id`: County FIPS code
* `feat`: unigram
* `value`: Number of times the unigram was used by the county
* `group_norm`: Average number of times the feature was used by the county (`value / number of users in county`)

### Facebook Topics

Topic loadings per county using a set of 2000 topics captured in over 14 million Facebook status updates derived via Latent Dirichlet Allocation (LDA) ([see full reference](http://wwbp.org/publications.html#p7)). Topics, words per topic and conditional probailities available [here](https://github.com/wwbp/facebook_topics).

* `group_id`: County FIPS code
* `feat`: Topic id
* `value`: Number of times a word in the topic was used by the county
* `group_norm`: Relative frequency of topic use by county

## Data Processing

Twitter data was processed using the following rules:

1. Each tweet was mapped to a U.S. County using tweet level latitude / longitude information and user level profile free text ([full details here](http://wwbp.org/publications.html#p8)).
2. Filtered for English using [langid](https://github.com/saffsd/langid.py).
3. Users with less than 30 tweets were removed.
4. Counties with less than 100 users were removed.

Linguistic features process:

1. Unigram relative frequencies extracted for each user.
2. User level relative frequencies are averaged to the county.
3. Topic loadings calculated using county level unigram relative frequencies.

## Citation

Please cite the following paper if you use this data. 

```
@inproceedings{giorgi2018remarkable,
    title={The Remarkable Benefit of User-Level Aggregation for Lexical-based Population-Level Predictions}, 
    author={Giorgi, Salvatore and Preotiuc-Pietro, Daniel and Buffone, Anneke and Rieman, Daniel and Ungar, Lyle H. and Schwartz, H. Andrew}, 
    booktitle={Proceedings of the 2018 Conference on Empirical Methods in Natural Language Processing}, 
    year={2018}
}
```

## License

Licensed under a GNU General Public License v3 (GPLv3).

## Background

Developed by the [World Well-Being Project](http://www.wwbp.org) based out of the University of Pennsylvania and Stony Brook University.