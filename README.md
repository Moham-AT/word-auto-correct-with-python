# word auto-correct with python
This is a simple word auto-correct block which is based on Shakespeare's text and does not use any of advanced NLP libraries.

the code is consist of several functions in order to create different variations of the input misspelled word.
the delete, insert and replace functions are used for editting the misspelled word and produce new variation.
this three functions can delete, insert or replace just one letter from/to the misspelled word.

after creating this different variations, we check them in our refrence vocabulary (which is shakespeare words here) and remove the meaning-less words.
then we need to define a cost for any change in the input misspelled word. for example here we define 1 for deleting each letter, 1 for inserting each letter and 2 for replacing any letter. we also used the "levenshtein distance algorithm" for calculating the distance between two words based on this penalties.

after that we define the auto_correct function which results the best matched word for each misspelled input. this function first finds the matching word with minimum penalty and return it, and if we have multiple words with same penalty it chooses the most frequent one in the refrence text.

in order to speed up the code, we used sets and operation between sets, instead of lists and list comprehention.
