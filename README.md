<H3>NAME : Santhosh U</H3>
<H3>REGISTER NO : 212222240092</H3>
<H3>EX. NO.6</H3>
<H3>DATE:</H3>
<H1 ALIGN =CENTER>Implementation of Semantic Analysis</H1>
<H3>Aim:</H3> 
 To perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.

<H3>Program:</H3>

```py
!pip install nltk
import nltk
nltk.download( 'punkt_tab' )
nltk.download('WordNet')
nltk.download('omw-1.4')
from nltk.tokenize import word_tokenize
nltk.download( 'averaged_perceptron_tagger_eng' )
from nltk.corpus import wordnet

sentence=input()
words = word_tokenize(sentence)
pos_tags= nltk.pos_tag(words)
for word, tag in pos_tags:
    print(f"{word:<6} - {tag}")

synonyms =[]
antonyms =[]
for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append (lemma.name())
            if lemma.antonyms():
                antonyms.append (lemma.antonyms()[0].name())
print ( "Synonyms : " ,set(synonyms))
print ( "Antonyms : " ,set(antonyms))
```

<H3>Output</H3>

![Output1](https://github.com/user-attachments/assets/033014ea-6903-4a60-9227-94a639e27954)

<H3>Result:</H3>
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
