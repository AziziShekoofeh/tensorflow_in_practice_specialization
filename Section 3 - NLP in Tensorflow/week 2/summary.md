### Natural Language Processing in TensorFlow  [Course Link](https://www.coursera.org/learn/natural-language-processing-tensorflow)

### Week two summary

- TensorFlow library containing common data

-  IMDB dataset:
    - 50,000 records
    - 25,000 each test and train
    - labels are binary 0,1 indicating bad or good reviews (binary crossentropy)
  
- Embedding:
    - Meaning: Word embedding is the collective name for a set of language modeling and feature learning techniques in natural language processing (NLP) where words or phrases from the vocabulary are mapped to vectors of real numbers [defenition in wikipedia].
    - Embedding dimension: indication the number of dimensions for the vector representing the word encoding.
    - You can perform embedding using *tf.keras.layers.Embedding* layer.

Some other notes:
    - Subword usage can cause a poor results, because sequence becomes much more important when dealing with subwords, but we're ignoring word positions. 
    - As previousely mentioned, you can also pass the *num_words=max_number* to indicate the maximum number of words to be tokenized, and the tokenizer will pick the **most** common max_number words to make the dictionary.

Codes at: https://colab.research.google.com/drive/xxxx
