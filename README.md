# EC504 Project: Language Checker

## Documentation

### Description

  The Language Checker is used to check language errors including spelling mistakes, capitalizing the first letter and unusual phrases. It can check the language errors in text file or sentences input by yourself.

### Group Members:

| Name          | E-mail      | Task                       |
| ------------- |-------------|----------------------------|
| Yuankun Li    | lykbu@bu.edu|  Crawler, N-gram Model     |
| Xianglin Zhou | zxl@bu.edu  |  UI Design, Trie Design    |


### Datastructure and Algorithm
#### Prefix Tree
  The Prefix Tree is a kind of search tree—an ordered tree data structure that is used to store a dynamic set or associative array where the keys are usually strings. We implenments the trie as a dictionary to check spelling mistake, because of its high-efficiency which takes O(k) lookup time for k-length words. 
  
  Three elements in the trie: the character stored in the node, child nodes, count of the number of child nodes and end flag. 
  
  Two methods in the trie: 
  
  * Insert function: Used to insert words form dictionary we crawl online. Every character of input key is inserted as an individual Trie node. The children is an array of pointers (or references) to next level trie nodes. The key character acts as an index into the array children. If the input key is new or an extension of existing key, we need to construct non-existing nodes of the key, and mark end of word for last node. If the input key is prefix of existing key in Trie, we simply mark the last node of key as end of word. The key length determines Trie depth. 
  
  * Search function: Used to search whether a word exists in the trie. we compare the characters and move down. The search can terminate due to end of string or lack of key in trie. In the former case, if the isEndofWord field of last node is true, then the key exists in trie. In the second case, the search terminates without examining all the characters of key, since the key is not present in trie.

#### UI
 We implemented Swing library which can provide a graphical user interface (GUI) for our project. Our GUI is shown blew:
 
 Three buttons:
 
 * Read data: Read a text file, show the text on the inputwords area, check the language errors automatically and show the errors one the outputwords text area.
 
 * Check: After write something in the inputwords area, click on the check, the language errors automatically and show the errors one the outputwords text area.
 
 * Exit: Close the application.
  
 Text Area:
 
  * Inputwords Area: Show the text read from a text file or input by yourself.
  * Outputwords Area: Show the errors.



  
##### N-gram
##### Regualr Grammar

### Feature



## Code



## Work Breakdown
* Yuankun Li

 1.
 2.
 3.
  
* Xianglin Zhou

 1.UI
 2.
 3.

## Jira Links

