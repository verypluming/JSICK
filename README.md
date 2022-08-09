# Japanese Sentences Involving Compositional Knowledge (JSICK) Dataset/JSICK-stress Test Set

## Japanese Sentences Involving Compositional Knowledge (JSICK) Dataset
JSICK is the Japanese NLI and STS dataset by manually translating the English dataset [SICK](https://marcobaroni.org/composes/sick.html) (Marelli et al., 2014) into Japanese.
We hope that our dataset will be useful in research for realizing more advanced models that are capable of appropriately performing multilingual compositional inference.
The dataset is splitted into `train.tsv` and `test.tsv`.

|Name|Description|
|----|-----|
|pair_ID|ids (the same with oriinal SICK)|
|sentence_A_En|first sentence in English|
|sentence_B_En|second sentence in English|
|entailment_label_En|original entailment label in English|
|relatedness_score_En|original relatedness score in the range [1-5] in English|
|corr_entailment_labelAB_En|corrected entailment label from A to B in English by [(Karouli et al., 2017)](http://vcvpaiva.github.io/includes/pubs/2017-iwcs.pdf)|
|corr_entailment_labelBA_En|corrected entailment label from B to A in English by [(Karouli et al., 2017)](http://vcvpaiva.github.io/includes/pubs/2017-iwcs.pdf)|
|sentence_A_En|first sentence in Japanese|
|sentence_B_En|second sentence in Japanese|
|entailment_label_Ja|entailment label in Japanese|
|relatedness_score_Ja|relatedness score in the range [1-5] in Japanese|
|image_ID|original image in [8K ImageFlickr dataset](https://www.kaggle.com/datasets/adityajn105/flickr8k)|
|original_caption|original caption in [8K ImageFlickr dataset](https://www.kaggle.com/datasets/adityajn105/flickr8k)|
|semtag_short|linguistic phenomena tags in Japanese|
|semtag_long|details of linguistic phenomena tags in Japanese|

## JSICK-stress Test Set
The JSICK-stress test set is a dataset to investigate whether models capture word order and case particles in Japanese. 
The JSICK-stress test set is provided by transforming syntactic structures of sentence pairs in JSICK, where we analyze whether models are attentive to word order and case particles to predict entailment labels and similarity scores.
The JSICK test set contains 1666, 797, and 1006 sentence pairs (A, B) whose premise sentences A (the column `sentence_A_Ja_origin`) include the basic word order involving ga-o
(nominative-accusative), ga-ni (nominative-dative), and ga-de (nominative-instrumental/locative) relations, respectively.
We provide the JSICK-stress test set by transforming syntactic structures of these pairs by the following three ways: 
- `scrum_ga_o`: a scrambled pair, where the word order of premise sentences A is scrambled into o-ga, ni-ga, and de-ga order, respectively.
- `ex_ga_o`:  a rephrased pair, where the only case particles (ga, o, ni, de) in the premise A are swapped
- `del_ga_o`: a rephrased pair, where the only case particles (ga, o, ni) in the premise A are deleted

The file `jsick/jsick-all-annotations.tsv` contains the JSICK raw annotations, and the file `jsick-stress/jsick-stress-all-annotations.tsv` is a subset of JSICK-stress test sets annotated with human judgements.

## References
1. Hitomi Yanaka, Koji Mineshima. Compositional Evaluation on Japanese Textual Entailment and Similarity.
    Transactions of the Association for Computational Linguistics, 2022. (TACL2022)
    [[arXiv]]()
2. 谷中瞳, 峯島宏次. [JSICK: 日本語構成的推論・類似度データセットの構築](https://www.jstage.jst.go.jp/article/pjsai/JSAI2021/0/JSAI2021_4J3GS6f02/_pdf/-char/ja). 人工知能学会第35回全国大会, 2021.

If you use this dataset in any published research, please cite the following:
```
@article{Yanaka_tacl2022,
  title = "Compositional Evaluation on Japanese Textual Entailment and Similarity",
  author = "Hitomi Yanaka and Koji Mineshima",
  journal = {Transactions of the Association for Computational Linguistics},
  year = "2022",
  note = "to appear"
}
```

## License
This work is licensed under a [Creative Commons Attribution 4.0 International License](LICENSE.txt).