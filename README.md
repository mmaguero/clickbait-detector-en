# clickbait-detector-en
Clickbait detector for English tweets, trained on [Webis-17 dataset](https://webis.de/data/webis-clickbait-17.html). This repo contains three data-centric approaches with Robustly optimized BERT-Bidirectional Encoder Representations from Transformers- approach (RoBERTa). More particular, we use XLM-RoBERTa-base version (multi/cross-lingual version with 12 attention layers trained on ~100 languages - including English) from [Hugging Face](https://huggingface.co/xlm-roberta-base).

## Dataset:
- [Webis website](https://webis.de/data/webis-clickbait-17.html#download), or
- [Here](https://ml-coding-test.s3.eu-west-1.amazonaws.com/webis_train.csv) and [here](https://ml-coding-test.s3.eu-west-1.amazonaws.com/webis_test.csv).

## Code
Up-to-date [Colab notebook](https://colab.research.google.com/drive/1zaLUrZWT2Yr4y3u0bOv2p_sw_qtbHAFb?usp=sharing) or [here](tweets_clickbait.ipynb).

## Results

| Run | F1*       | macro-F1 | Acc.     | macro-Acc. |
|-----|----------|----------|----------|------------|
|<td colspan=5>"Dataset completo" (XROBERTa_clickbait)</td>
| 0   | **0.6846** | **0.7914** | 0.846    | **0.7966**   |
| 1   | 0.6738   | 0.7889   | 0.8517     | 0.7802     |
| 0(2)| 0.3844   | 0.1922   | 0.2379     | 0.5 |
| 0(3)| 0.3844   | 0.1922   | 0.2379     | 0.5 |
| 1(3)| 0.6743   | 0.7901   | **0.854**  | 0.7788 |
| 2   | 0.6609   | 0.783    | 0.8516     | 0.7678 |
|  <td colspan=5>"Sin outliers" (XROBERTa_clickbait_wo_outlier)|
| 0   | 0.6664 | 0.7852 | 0.8509 | 0.7735 |
| 1   | 0.663  | 0.783  | 0.8494 | 0.7714 |
| 2   | **0.685**  | **0.796**  | **0.8564** | **0.7876** |
| 3   | 0.6704 | 0.7877 | 0.8524 | 0.7763 |
| 4   | 0.6653 | 0.7861 | 0.8543 | 0.7699 |
|  <td colspan=5>"Con buen acuerdo entre anotadores" (XROBERTa_clickbait_agree)|
| 0   | 0.6677 | 0.7879 | 0.8559 | 0.7709 |
| 1   | 0.7064 | 0.8107 | 0.8683 | 0.7987 |
| 2^   | <u>**0.7112**</u> | <u>**0.8134**</u> | <u>**0.8693**</u> | <u>**0.803**</u>  |
| 3   | 0.6969 | 0.8067 | 0.869  | 0.7879 |
| 4   | 0.7053 | 0.8104 | 0.8686 | 0.7971 |
  
(*) binary.
(^) best result.
  
  
## Error analysis
  Confusion matrix [here](confusion_matrix.pdf).


## Training
[Here](https://wandb.ai/mmaguero/clickbait/table?workspace=user-mmaguero) you can see the detailed hyper-params and all results.



