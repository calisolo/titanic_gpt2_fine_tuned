kaggle titanic tutorial by gpt2 fine-tune
=====================================
Titanic
https://www.kaggle.com/competitions/titanic

### Approach(editing)

(input forminput forminput forminput form )
concatenate each features as natural languages   

instead of using special tokens like [UNUSED01],   
rather assign unused vocabulary for its semantic embeddings.   

```python
  pclass = 'seat class'    
  sibsp = 'with sibling'   
  parch = 'parents onboard'   #didn't use same word hoping model won't confuse
  cabin = 'cabin number'   
  embarked = 'embarked port'   
```

If feature name already looks like it has semantic connotation, used it as is.(ex. name, sex, age, ticket, fare)



inference passenger live or dead with gpt2classification model
























### HyperParameters
```
epochs = 200
learning_rate = 0.026
eps = 1e-8
weight_decay = 0
batch_size = 8
cycles = 9 (cosine annealing with warmup)
warmup = training steps/10
```
### Curious things


1. pad_token  = eos_token makes sense?
2. special token length matter?  (1 or more)


### Result




🤮Score: 0.67464🤮



### Why it sucks?
- maybe no sufficient training data
- maybe inappropriate model for task (i think this task not much related to word embeddings)
- maybe wrong hyperparameters

### Reference

1. GPT2 fine tuning for classification
https://github.com/gmihaila/ml_things/blob/master/notebooks/pytorch/gpt2_finetune_classification.ipynb

2. Simple Chit-Chat based on KoGPT2
https://github.com/haven-jeon/KoGPT2-chatbot
