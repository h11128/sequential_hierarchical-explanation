# sequential_hierarchical-explanation

# sequential_hierarchical-explanation
 Layer-wise Analysis of Bert Model for Sentiment Analysis
 
Download the trained models as follow:

Download the pytorch_model.bin and put it in bert/model_sst/

```shell script
wget web.cse.ohio-state.edu/~samavatian.1/VaiS/pytorch_model.bin 
```
Download models Folder and put it in ./
```shell script
wget web.cse.ohio-state.edu/~samavatian.1/VaiS/models.zip 
```
The output of the explains.py script will be uploaded soon in outputs directory. soc_result is ready now. 

# for BERT

For running bert the descreption is vague:

Not sure how to train language model based on bert?? what should change? I added only added '--use_bert_tokenizer' 
```shell script
export lm_path=models/sst_lstm_lm
python -m lm.lm_train --task sst --save_path models/${lm_path} --no_subtrees --lr 0.0002
```
for running explain.py this is how to do it: 

```shell script
export model_path=models_sst

python explain.py --resume_snapshot ${model_path} --method ${algo} --lm_path models/${lm_path} --batch_size 1 --start 0 --stop 50 --exp_name ${exp_name} --task sst --explain_model bert --nb_range 10 --sample_n 20 --use_bert_tokenizer
```

Note: --agg tag does not for for scd in LSTM and for both soc and scd for bert. (in other words only work for LSTM soc)
