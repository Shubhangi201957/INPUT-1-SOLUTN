# INPUT-1-SOLUTN


PROBLEM STATEMENT:-
Given a sorted list of words, find the longest compound word in the list that is constructed by concatenating the words in the list. For example, if the input list is: ['cat', 'cats', 'catsdogcats', 'catxdogcatsrat', 'dog', 'dogcatsdog', 'hippopotamuses', 'rat', 'ratcat', 'ratcatdog', 'ratcatdogcat']. Then the longest compound word is ‘ratcatdogcat’ with 12 letters. Note that the longest individual words are ‘catxdogcatsrat’ and ‘hippopotamuses’ with 14 letters, but they’re not fully constructed by other words. Former one has an extra ‘x’ letter, and latter is an individual word by itself not a compound word.

APPROACH FOR SOLVING:
->Construct a Trie out of all the words in the input list. Each node represents one character.
->Now I have another method to examine each input word to find out number of components (let's say compound length) it is made of. For example, in the above example ratcatdogcat is made of individual words in the input list rat, cat, dog and cat. I do this by recursively parsing out valid prefix of input word and finding the compound length of rest of the word i.e., parse rat and get compound length for catdogcat. If the compound length of rest is zero, meaning rest is not a valid construct, I try the next prefix ratcat and recurse on dogcat.

