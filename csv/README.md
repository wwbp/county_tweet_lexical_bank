# County Tweet Lexical Bank CSV

CSV version. All tables are in sparse (long) format.

## Data

### 1grams

File name: `feat.1gram.msgs.cnty.16to16.csv`

* `group_id`: County FIPS code
* `feat`: 1gram
* `value`: Number of times the 1gram was used by the county
* `group_norm`: Average number of times the feature was used by the county (`value / number of users in county`)

### Facebook Topics

File name: `feat.cat_met_a30_2000_cp_w.msgs.cnty.1gra.csv`

* `group_id`: County FIPS code
* `feat`: Topic id
* `value`: Number of times a word in the topic was used by the county
* `group_norm`: Relative frequency of topic use by county

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

