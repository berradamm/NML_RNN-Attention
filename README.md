# NMT_RNN-Attention
Natural Machine Translation using RNNs and Attention 
## Preparing the datas
-  Every word is a hot vector and we will inditify it as the index of the single one
-  Turning the Unicode to Ascii characters
-  Every word will be lowercased
-  Getting the lines and splitting a first time to get all the lines of the files and to get the pair "to translate-> translate"
-  Counting the largest input for the Attention Layer
This preparation makes this program flexible in terms of languages it can train to translate any languages you just need the right data but more relevant it can reverse the translation.
## The layers
<img width="1058" alt="seq2seqwthatt" src="https://user-images.githubusercontent.com/45148200/50037100-5ceba500-000e-11e9-9fcb-604bdbf65008.png">

### The encoder

The encoder will be reading the input sequence and then outputs a single vector and a hidden state. The hidden state wil be used by the Attention and the decoder.

### The decoder
The decoder will read the resulted vector to produce an output sequence. 
The End token is used by the decoder in order to know when to stop while predicting

### So what is the Attention layer 
It was first elaborated by Dzmitry Bahdanau in 2014 and presented trough this article:

-[Neural Machine translation by jointly learning to align and translate](https://arxiv.org/pdf/1409.0473.pdf)

However, right now the most know article about the Attention would the famous [Attention is all you need](https://arxiv.org/pdf/1706.03762.pdf) 
So basically it add the notion of focus to our sequence to sequence model. In other words it will attribute some weight that will lead it to a distrbution. This output which is obtained by the multiplaying encoder and attention layer's output will help deciding which other is important in the translation.
Furthemore there two kinds of Attention :
- The soft one where we can focus on more than one object. It is deterministic with this same inputs we will always focus on the same objects
- The hard one where we focus only on one object. It is the stochastic where with the same inputs we can have different results which means here focusing on different objects

### Results

So that's basically it 
