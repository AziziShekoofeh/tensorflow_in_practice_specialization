## Week one summary

- The class object to tokkenize sentences is named "Tokenizer", which can be used, to read all of the words in the list of sentences, then assign a code/token to eahc new word. 
    - For this purpose, you need to use *fit_on_texts(list_of_sentences)* method of this class.
    - The list of sentences is called *Corpus*. 
    - After fiting the tokenizer on your corpus, you can call this tokenizer to generate the list of tokens for any target sentence, inside or outside the corpus. 
    - For this purpose, and to encode the list of sentences, you need to use *texts_to_sequences(list_of_sentences)*.
    - You can use *oov_token= Token*, to specify a token to use for unknown words,specially, in case of out of corpuse sentences. 

- If you have a number of sequences of different lengths, you need to ensure that they are understood when fed into a neural network, and have the same lenght. For this purpose you can use *pad_sequences* object from the *tf.keras.preprocessing.sequences*.

- Some additional notes:
    - Exclamation and question mark have not tokenized.
    - Every word will be changed to non-capital small letter in the tokanization dictionary.
    - If any out of the vocabulary or corpus case is happening during sequence generation, the tokenizer sequence is completly dismiss the word and will output nothing, so it is important to handle such cases by defining "out of vocab" or 'oov_token'. So, the word isn't encoded, and is skipped in the encoded sequence.  
    - Padding is based on the longest sentence lenght or a pre-fixed maximum lenght which cause truncation of the long sentences.
    - The default behaviour of padding is to add zeros to the begenning of the shorter ones, which is a *pre* param.
    - You can pass padding='post' to pad sequences by adding zeros at the end of short sentencess.
    
- Link to lessons from the coursera week 1: 

    - [Lesson 1](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%201%20-%20Lesson%201.ipynb)
    - [Lesson 2](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%201%20-%20Lesson%202.ipynb)
    - [Lesson 3](https://colab.research.google.com/github/lmoroney/dlaicourse/blob/master/TensorFlow%20In%20Practice/Course%203%20-%20NLP/Course%203%20-%20Week%201%20-%20Lesson%203.ipynb)


Codes at: https://colab.research.google.com/drive/xxxx



