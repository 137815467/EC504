# Language Checker

## Documentation

### Description:
This Language Checker is designed to detected express error in english text, specifically in: 1. Check if the first letter in one sentence is captial and output the error word. 2. Check if there exists mis-spelling problems and output the mis-spelled words. 3. Check if there exists unusual phrases and output them. 

### Group members:
| Name           | E-mail                | Phone                           |
| ---------- |------------| --------------------- |
| Yuankun Li    | lykbu@bu.edu  |      |
| Xianglin Zhou | zxl@bu.edu     |  8572539268    |

### Details:
#### Implementation summary:
Main algorithm: N-gram algorithm (2-gram), Linear Search
Data Structure: Graph, Adjacency matrix

#### Features achieved:

##### 1. Crawler that stores information about at least 10GB of text from the Internet. 
 Crwalered English books from website(http://www.readcentral.com/) and other websites by using library of Jsoup. Data collected are over 10GB and are stored in text file as plain text. (The reason we chose not to store them in sql database is that it would be way too slow for javantp connect sql and read huge file from it.)
 ArrayList were used to store url links.
 
 
##### 2. Detecting unusual express error in text.

**Data sturcture:**

  (1) Ngram Model

  * Ngram_node: Each node represents a word.
 
  * Ngram_edge: Each edge represents a relationship between two words, with weight representing how many times that this relationship appears. i.e. edge "this is" with weight 10 represents the word "this" is followed by word "is" 10 times in training data.

  * Ngram_Graph: A ArrayList that stores all edges and all nodes. It contains methods of adding new node when meets a new word and adding new edge when meets a new relationship in training data.

  (2) Tree:

  The Prefix Tree is a kind of search tree—an ordered tree data structure that is used to store a dynamic set or associative array where the keys are usually strings. We implenments the trie as a dictionary to check spelling mistake, because of its high-efficiency which takes O(k) lookup time for k-length words. There are three elements in the trie: the character stored in the node, child nodes, count of the number of child nodes and end flag. 

**Algorithm:**

(1) Captial error detection:
  For each sentence:
    If first letter of first word is lower case:
       Output first word
       
      
(2) Mis-spelling error detection:
    Two methods in the trie are used to check the word spelling mistakes. we use insert function build the trie as a dictionary, then use the search function to search whether a word is in the trie :   
  * Insert function: Used to insert words form dictionary we crawl online. Every character of input key is inserted as an individual Trie node. The children is an array of pointers (or references) to next level trie nodes. The key character acts as an index into the array children. If the input key is new or an extension of existing key, we need to construct non-existing nodes of the key, and mark end of word for last node. If the input key is prefix of existing key in Trie, we simply mark the last node of key as end of word. The key length determines Trie depth. 
  
  
  * Search function: Used to search whether a word exists in the trie. we compare the characters and move down. The search can terminate due to end of string or lack of key in trie. In the former case, if the isEndofWord field of last node is true, then the key exists in trie. In the second case, the search terminates without examining all the characters of key, since the key is not present in trie.

(3) Unusual phrases detection:
Bigram model:
 We computed the probability of a phrase in two words by using the conditional probability of preceding word P(wn|wn-1). 
 For all pharses showed in training data, we store all phrases relationships in graph. P(w_n|w_(n-1))=number of edge "w_n w_(n-1)"/number of word w_n. 
 The phrase "w_n w_(n-1)" is unusual if P(w_n|w_(n-1)) < e where e is a constant threshold for detecting unusual phrases.
 Unusal phrases more than 2 words:
 If there exist a strange phrase with more than 2 words such as "of of ship", the program will detect "of of" and "of ship" as two unusual phrases, and combine them together as "of of ship".
 

##### 3. Command Line User Interface
 Exported a jar file which is executable in terminal.
 

##### 4. Reading data from typing and exist txt file.
 Two modes are available, user can choose to type in english text or upload a exist file.
 

##### 5. UI
 We implemented Swing library which can provide a graphical user interface (GUI) for our project. Our GUI is shown blew:
 
 Three buttons:
 
 * Read data: Read a text file, show the text on the inputwords area, check the language errors automatically and show the errors one the outputwords text area.
 * Check: After write something in the inputwords area, click on the check button, the language errors will show onth outputwords text area.
 * Exit: Close the application.
  
 Text Area:
 
 * Inputwords Area: Show the text read from a text file or input by yourself.
 * Outputwords Area: Show the errors.
 

##### 6. Android client
  Because of the number of people in our team, we foucs on the Java application and just design simple Android Application for only words checking. In the Android applicaiton, the main datastructure is Trie which we use in the Java application as well. It can read text file on the moblie or input by yourself,  then check the spelling errors and output wrong words.


##### 7. Data processed and running speed
 Data:
 (1) Used only about 350 MB data from crawler. (1GB and 2GB data were tried, but the training time was too slow and memory errors were occured when reading data before training. So I had to use smaller training set, which fast the running speed and on the other hand, lower the accuracy.)
 (2) Sentences were got rid of punctuation before processing. (Therefore program cannot detect any error with punctuation.
 
 Speed:
 (1) Whole training time is around 2 min.
 (2) Loading trained model in testing cost around 20s.


#### Feature not achieved:

##### 1. Testing
 We simply tested our program by using very limited sentences and check the results by ourselves.
##### 2. Grammar check
##### 3. Ability to check other language

Due to not having enough member in our team and limit time, the features above was fail to achieve. More feature will be added in the future plan.

### Reference:
 Daniel Jurafsky and James H.Martin(2008) Speech and Language Processing 2nd Edition, Chapter 4, Chapter 5, Chapter 6, Chapter 12

## Code:

#### java file:
 WebCrawler.java
 DictionaryCheckApp.java
 FirstLetter_rule.java
 Loadmodel.java
 Maintest.java
 Maintrain.java
 Ngram_edge.java
 Ngram_node.java
 Ngram_Graph.java
 Node.java
 Trie.java
 Edge.java
 node.java
 Simple_ngram.java
#### data:
 data.txt
 phrase.txt
 words.txt
 model_client.txt
 model1.txt
 test.txt

#### library:
 jsoup- 1.10.3.jar

#### executable program:
 LanguageChecker_UI.jar
 LanguageChecker_commandline.jar 

## Work contribution:

Xianglin Zhou: 
  * Build Trie to storage dictionary and check spelling errors.
  * Build GUI for Java applicaiton
  * Build Android Application for only word spelling check
  
Yuankun Li:

## Jira link:




