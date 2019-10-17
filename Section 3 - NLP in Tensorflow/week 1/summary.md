## Week one summary

- The class object to tokkenize sentences is named "Tokenizer", which can be used, to read all of the words in the list of sentences, then assign a code/token to eahc new word. 
    - For this purpose, you need to use *fit_on_texts(list_of_sentences)* method of this class.
    - The list of sentences is called *Corpus*. 
    - After fiting the tokenizer on your corpus, you can call this tokenizer to generate the list of tokens for any target sentence, inside or outside the corpus. 
    - For this purpose, and to encode the list of sentences, you need to use *texts_to_sequences(list_of_sentences)*. 


Some additional notes:
    - Exclamation and question mark have not tokenized.
    - Every word will be changed to non-capital small letter in the tokanization dictionary.
    - If any out of the vocabulary or corpus case is happening during sequence generation, the tokenizer sequence is completly dismiss the word and will output nothing, so it is important to handle such cases by defining "out of vocab" or 'oov_token'.
    
    
Padding is based on the longest sentence lenght or a pre-fixed maximum lenght.

Codes at: https://colab.research.google.com/drive/xxxx
