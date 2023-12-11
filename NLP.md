# NLP

## Word2vec

* Key idea: word can be represented by vectors (embeddings)

  * model 1: skip-n-gram
  * model 2: continous bag of words
  * loss function: negative sampling -> computation efficiency
    * negative sampling sample certain number of out of range words

  <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126182439932.png" alt="image-20231126182439932" style="zoom:25%;" />



### feed-forward networks

* stochastic gradient descent

$$
\theta_{new} = \theta_{old} - \alpha \nabla_{\theta}J(\theta)
$$

* Non-linearty

  <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126183902126.png" alt="image-20231126183902126" style="zoom: 50%;" />



* cross-entropy

  <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184005797.png" alt="image-20231126184005797" style="zoom:50%;" />



* overfitting and regularization

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184153708.png" alt="image-20231126184153708" style="zoom:50%;" />



* dropout

  <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184231982.png" alt="image-20231126184231982" style="zoom:50%;" />

* vectorization

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184325247.png" alt="image-20231126184325247" style="zoom:50%;" />

* parameter initialization

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184335639.png" alt="image-20231126184335639" style="zoom:50%;" />

* optimizer

  <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184436185.png" alt="image-20231126184436185" style="zoom:50%;" />



## language model

* language model: task of predicting what word comes next

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184617143.png" alt="image-20231126184617143" style="zoom:50%;" />

### Recurrent networks

* teacher forcing: use next word as label

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126184810464.png" alt="image-20231126184810464" style="zoom:50%;" />

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126185004956.png" alt="image-20231126185004956" style="zoom:50%;" />

* model evaluation

  <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126185356776.png" alt="image-20231126185356776" style="zoom:50%;" />

* issues in RNN

  * vanishing gradient

    <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126185513587.png" alt="image-20231126185513587" style="zoom:50%;" />Solution: LSTM

  * exploding gradient

    <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126185551500.png" alt="image-20231126185551500" style="zoom:50%;" />

​		solution:

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126185711553.png" alt="image-20231126185711553" style="zoom:50%;" />



### LSTM

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126190538378.png" alt="image-20231126190538378" style="zoom:50%;" />

other ways to solve gradient problem:	

* resudual network

  <img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126194145704.png" alt="image-20231126194145704" style="zoom:50%;" />

* layer normalization

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126194236279.png" alt="image-20231126194236279" style="zoom:50%;" />

### bidirectional and multi-layer RNN

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126190816353.png" alt="image-20231126190816353" style="zoom:50%;" />



## seq2seq (encoder-decoder)

* machine translation: task of translating a sentence x from one language to a sentence y in another language
* Summarization: long text -> short text
* Dialogue: previous utterances -> next utterances
* Parsing: input text -> output parse as sequence
* code generation: natural language -> python code

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126191617816.png" alt="image-20231126191617816" style="zoom:50%;" />

### attention

why we need to switch from RNN/LSTM to attention: information bottleneck -> the embedding cannot capture all information about the source sentence

Attention mechanism: use direct connection to the encoder to focus on a particular part of source sequence

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126192218913.png" alt="image-20231126192218913" style="zoom:50%;" />



### self-attention

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126193403459.png" alt="image-20231126193403459" style="zoom:50%;" />

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126193819967.png" alt="image-20231126193819967" style="zoom:50%;" />



### transformer

![image-20231126194316624](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126194316624.png)

![image-20231126194345730](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126194345730.png)

![image-20231126194421388](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126194421388.png)



### pretraining

![image-20231126202346809](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126202346809.png)



![image-20231126203902020](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126203902020.png)

* BERT

  ![image-20231126203957570](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126203957570.png)

![image-20231126204656619](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126204656619.png)

![image-20231126204852456](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126204852456.png)

![image-20231126205102046](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126205102046.png)

![image-20231126205240385](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126205240385.png)



### in-context learning

![image-20231126205506139](/Users/ke_wang/Library/Application Support/typora-user-images/image-20231126205506139.png)



## Natural language generation

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231127202502829.png" alt="image-20231127202502829" style="zoom:50%;" />

<img src="/Users/ke_wang/Library/Application Support/typora-user-images/image-20231127202611173.png" alt="image-20231127202611173" style="zoom:50%;" />