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
* Prefix Tree
  The Prefix Tree is a kind of search tree—an ordered tree data structure that is used to store a dynamic set or associative array where the keys are usually strings. We implenments the trie as a dictionary to check spelling mistake, because of its high-efficiency which takes O(k) lookup time for k-length words. 
  
  There are three elements in the trie structure: the character stored in the node, child nodes, count of the number of child nodes and end flag. 
  
  There are two method in the trie: 
  
  * Insert function: Used to insert words form dictionary we crawl online. Every character of input key is inserted as an individual Trie node. The children is an array of pointers (or references) to next level trie nodes. The key character acts as an index into the array children. If the input key is new or an extension of existing key, we need to construct non-existing nodes of the key, and mark end of word for last node. If the input key is prefix of existing key in Trie, we simply mark the last node of key as end of word. The key length determines Trie depth. 
  
  * Search function: Used to 


  
* N-gram
* Regualr Grammar
*
### Feature



## Code



## Work Breakdown
* Yuankun Li

 1.
 2.
 3.
  
* Xianglin Zhou

 1.
 2.
 3.

## Jira Links

