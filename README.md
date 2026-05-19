Praveena M
212223040153
EX. NO.6
19-05-2026
Implementation of Semantic ANalysis
Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques.

Algorithm:
Step 1: Import the nltk library.
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.
Step 3:Accept user input for the text.
Step 4:Tokenize the input text into words using the word_tokenize function.
Step 5:Iterate through each word in the tokenized text.
• Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.
• Print each word along with its corresponding part-of-speech tag.
• For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).
• Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.
• Print the unique sets of synonyms and antonyms.
Program:
Insert your code here
```
import nltk
from nltk.corpus import wordnet

# Downloads
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')
nltk.download('averaged_perceptron_tagger_eng')

sentence = input("Enter a sentence: ")

# Simple tokenization
words = sentence.split()

# POS tagging
pos_tags = nltk.pos_tag(words)

synonyms = []
antonyms = []

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())

            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

print("POS Tags:", pos_tags)
print("Synonyms:", set(synonyms))
print("Antonyms:", set(antonyms))
```
Output

Result:
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
