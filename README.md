# code
### Code for Compression Model Training 
To train BERT-based models, simply run the following and the best model according to dev set will be saved in ```model_save``` folder (please create one).

```bash
python main.py 
```
You may specify hyperparameters in ```config.py```.


### Code for constructing 151k data
We describe how to yield 151k pairs of sentence and headline using Chinese Gigaword Third Version as follows. Just run the following scripts to go through step 1 - 4 to get 151k pairs of sentence and compression.

```bash
python data_processing.py 
```

 - Step 1: Extract raw data from Chinese Gigaword Third Version. There are four folders, i.e., ```afp_cmn```, ```cna_cmn```, ```xin_cmn```, ```zbn_cmn``` under gigawords dataset folder. The first sentence and headline of each article will be extracted.
 - Step 2: Text cleansing by removing non-English text and unusual punctuation.
 - Step 3: Tokenize the headline and the first sentence using Stanza NLP pipeline to identify content words through its part-of-speech tags.
 - step 4: Filter out the cases where length requirement is not satisfied according to the rules in Appendix A of the paper.

