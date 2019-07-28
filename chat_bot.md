
# MINI CHATBOT 


IMPORT ALL THE NECESSARY PACKAGES


```python
import numpy as np
import pandas as pd
import webbrowser
import matplotlib.pyplot as plt
from IPython.core.display import HTML
import os
```

LET'S LOOK OVER AVAILABLE THE FILES AND FOLDER


```python
actual_path = "C:/Users/Sultan/Desktop/chatbot/chatbot"
files_and_folders = os.listdir(actual_path)
files_and_folders
```




    ['LICENSE-S08,S09', 'README.v1.2', 'S08', 'S09', 'S10']



There are 3 Folder which we going to use

LET'S LOOK WHAT ARE THE FILES AND FOLDER AVAILABLE IN S08, S09 AND S10 


```python
s08 = os.listdir(actual_path+"\S08")
s09 = os.listdir(actual_path+"\S09")
s10 = os.listdir(actual_path+"\S10")

print(s08)
print(s09)
print(s10)
```

    ['Book1.csv', 'data1', 'question_answer_pairs.txt']
    ['Book2.csv', 'data2', 'question_answer_pairs.txt']
    ['Book3.csv', 'data3', 'question_answer_pairs.txt']
    
Each Folder have 2 files (.csv and .txt) and Data Folder
We are not going to use any .txt file here 
LET'S LOOK AT THE EACH .csv FILE


```python
# Each folders have csv fiile, txt files and respective data folders
# Lets look at the each csv files

book1 = pd.read_csv(actual_path + "\S08\Book1.csv")
book2 = pd.read_csv(actual_path + "\S09\Book2.csv")
book3 = pd.read_csv(actual_path + "\S10\Book3.csv")
```


```python
all_table = [book1.head(), book2.head(), book3.head()]
```

USING IPYTHON PACKAGE WE IMPLEMENT HTML METHOD TO ENABLE HTML TAGS.

USING THOSE TAGS WE IMPLEMENT EACH .csv TABLE OVER HTML TABLE TAG.

EACH .csv HAS BEEN DISPLAYED IN EACH COLUMN OF HTML TABLE.


```python
view_tables = HTML('<table><tr style="background-color:white;">' + 
     ''.join(['<td>' + table._repr_html_() + '</td>' for table in all_table]) +
        '</tr></table>')
view_tables
```




<table><tr style="background-color:white;"><td><div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ArticleTitle</th>
      <th>Question</th>
      <th>Answer</th>
      <th>DifficultyFromQuestioner</th>
      <th>DifficultyFromAnswerer</th>
      <th>ArticleFile</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>yes</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>Yes.</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>yes</td>
      <td>easy</td>
      <td>medium</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>Yes.</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Abraham_Lincoln</td>
      <td>Did his mother die of pneumonia?</td>
      <td>no</td>
      <td>easy</td>
      <td>medium</td>
      <td>data/set3/a4</td>
    </tr>
  </tbody>
</table>
</div></td><td><div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ArticleTitle</th>
      <th>Question</th>
      <th>Answer</th>
      <th>DifficultyFromQuestioner</th>
      <th>DifficultyFromAnswerer</th>
      <th>ArticleFile</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alessandro_Volta</td>
      <td>Was Volta an Italian physicist?</td>
      <td>yes</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alessandro_Volta</td>
      <td>Was Volta an Italian physicist?</td>
      <td>yes</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alessandro_Volta</td>
      <td>Is Volta buried in the city of Pittsburgh?</td>
      <td>no</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Alessandro_Volta</td>
      <td>Is Volta buried in the city of Pittsburgh?</td>
      <td>no</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alessandro_Volta</td>
      <td>Did Volta have a passion for the study of elec...</td>
      <td>yes</td>
      <td>easy</td>
      <td>medium</td>
      <td>data/set4/a10</td>
    </tr>
  </tbody>
</table>
</div></td><td><div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ArticleTitle</th>
      <th>Question</th>
      <th>Answer</th>
      <th>DifficultyFromQuestioner</th>
      <th>DifficultyFromAnswerer</th>
      <th>ArticleFile</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Alessandro_Volta</td>
      <td>Was Alessandro Volta a professor of chemistry?</td>
      <td>Alessandro Volta was not a professor of chemis...</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alessandro_Volta</td>
      <td>Was Alessandro Volta a professor of chemistry?</td>
      <td>No</td>
      <td>easy</td>
      <td>hard</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Alessandro_Volta</td>
      <td>Did Alessandro Volta invent the remotely opera...</td>
      <td>Alessandro Volta did invent the remotely opera...</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Alessandro_Volta</td>
      <td>Did Alessandro Volta invent the remotely opera...</td>
      <td>Yes</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Alessandro_Volta</td>
      <td>Was Alessandro Volta taught in public schools?</td>
      <td>Volta was taught in public schools.</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set4/a10</td>
    </tr>
  </tbody>
</table>
</div></td></tr></table>



Since the data path are similar on each table, it's necessary to differentiate before merging all tables

let's Rename the data folders of respective csv files


```python
data_1 = os.rename(actual_path + "\S08\data", actual_path + "\S08\data1")
data_2 = os.rename(actual_path + "\S09\data", actual_path + "\S09\data2")
data_3 = os.rename(actual_path + "\S10\data", actual_path + "\S10\data3")
```


    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    <ipython-input-40-fa80a06af835> in <module>
    ----> 1 data_1 = os.rename(actual_path + "\S08\data", actual_path + "\S08\data1")
          2 data_2 = os.rename(actual_path + "\S09\data", actual_path + "\S09\data2")
          3 data_3 = os.rename(actual_path + "\S10\data", actual_path + "\S10\data3")
    

    FileNotFoundError: [WinError 2] The system cannot find the file specified: 'C:/Users/Sultan/Desktop/chatbot/chatbot\\S08\\data' -> 'C:/Users/Sultan/Desktop/chatbot/chatbot\\S08\\data1'



```python
print(s08)
print(s09)
print(s10)
```


```python
# Now the folder name has been changed 
# it's also necessary to change the path in each csv file on the Articlefile feature
book1['ArticleFile'] = book1['ArticleFile'].map(lambda x : "S08/data1" + str(x)[4:])
book2['ArticleFile'] = book2['ArticleFile'].map(lambda x : "S09/data2" + str(x)[4:])
book3['ArticleFile'] = book3['ArticleFile'].map(lambda x : "S10/data3" + str(x)[4:])
```


```python
all_table = [book1.head(), book2.head(), book3.head()]
view_tables = HTML('<table><tr style="background-color:white;">' + 
     ''.join(['<td>' + table._repr_html_() + '</td>' for table in all_table]) +
        '</tr></table>')
view_tables
```


```python
print(book1.shape)
print(book2.shape)
print(book3.shape)
```


```python
merged = book1.append(book2).append(book3)
merged.to_csv(actual_path + "\wiki_dataset.csv")
```


```python
# lets read the   merged dataset
dset = pd.read_csv(actual_path + "\wiki_dataset.csv")
dset.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>ArticleTitle</th>
      <th>Question</th>
      <th>Answer</th>
      <th>DifficultyFromQuestioner</th>
      <th>DifficultyFromAnswerer</th>
      <th>ArticleFile</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>yes</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>Yes.</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>yes</td>
      <td>easy</td>
      <td>medium</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>Yes.</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Abraham_Lincoln</td>
      <td>Did his mother die of pneumonia?</td>
      <td>no</td>
      <td>easy</td>
      <td>medium</td>
      <td>data/set3/a4</td>
    </tr>
  </tbody>
</table>
</div>




```python
# let's remove the first column
dset = dset.drop(columns="Unnamed: 0")
dset.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ArticleTitle</th>
      <th>Question</th>
      <th>Answer</th>
      <th>DifficultyFromQuestioner</th>
      <th>DifficultyFromAnswerer</th>
      <th>ArticleFile</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>yes</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>Yes.</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>yes</td>
      <td>easy</td>
      <td>medium</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>Yes.</td>
      <td>easy</td>
      <td>easy</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Abraham_Lincoln</td>
      <td>Did his mother die of pneumonia?</td>
      <td>no</td>
      <td>easy</td>
      <td>medium</td>
      <td>data/set3/a4</td>
    </tr>
  </tbody>
</table>
</div>




```python
# The DifficultyFromQuestioner and DifficultyFromAnswerer is not needed
dset = dset.drop(columns="DifficultyFromQuestioner")
dset = dset.drop(columns="DifficultyFromAnswerer")
dset.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ArticleTitle</th>
      <th>Question</th>
      <th>Answer</th>
      <th>ArticleFile</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>yes</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Abraham_Lincoln</td>
      <td>Was Abraham Lincoln the sixteenth President of...</td>
      <td>Yes.</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>yes</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Abraham_Lincoln</td>
      <td>Did Lincoln sign the National Banking Act of 1...</td>
      <td>Yes.</td>
      <td>data/set3/a4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Abraham_Lincoln</td>
      <td>Did his mother die of pneumonia?</td>
      <td>no</td>
      <td>data/set3/a4</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Sort the table according to the article title
dset = dset.sort_values("ArticleTitle", axis = 0, ascending = True) 
dset.head()
```


```python
dset['ArticleTitle'].describe()
```


```python
titles = list(dset['ArticleTitle'].unique())
title_dict = {}
all_title = list(dset['ArticleTitle'])
all_question = list(dset['Question'])
all_answer = list(dset['Answer'])
all_content = list(dset['ArticleFile'])
for title in titles:
     title_dict[title] = all_title.count(title)
title_dict # key : Title , value : No. of QuestionsQuestion     
```


```python
# Remove '\\n:1' which is unnecessary
del title_dict['\\n']
titles.remove('\\n')
```


```python
def chooseTheTopic():
    print("TOPICS TO SEARCH"+"\n----------------\n")
    for index, top in enumerate(titles):
        print(index+1 , top, end = '     ')     
    print("\n___________________________________________________________________________________________________________")    

def displayContent(content):
    f= open("C:/Users/Sultan/Desktop/chatbot/chatbot/" + content + ".txt", "r",  encoding="utf8")
# #     content = f.read()
    #global inp
    #f = open("C:/Users/Sultan/Desktop/chatbot/chatbot/"+ content +".txt", "r")
    inp = f.read()[:500]+"......."
    ##   print("fdfDfdgdgvg")
    print(inp)
    
def displayUrl(content):
    print("FOR MORE INFORMATION Visit the link->")
    print("Do you wnat to vist Y/N")
    q = input().strip()
    if q=='y' or q=='Y':
        webbrowser.open_new_tab("C:/Users/Sultan/Desktop/chatbot/chatbot/" + content + ".htm")
    else:
        print("Thanks!!")
    
def chooseTheNumber():
    global question
    global answer
    global content
    
    topicNumber = int(input())
    
    question = [all_question[index] for index, top in enumerate(all_title) if top == titles[topicNumber-1]]
    answer = [all_answer[index] for index, top in enumerate(all_title) if top == titles[topicNumber-1]]
    content = [all_content[index] for index, top in enumerate(all_title) if top == titles[topicNumber-1]]
    
    
    print("content======", content)

    print("You have chosen the topic: ", titles[topicNumber-1])
    print("___________________________________________________________________________________________________________")
    
def askQuestion(ques):
    print("\n___________________________________________________________________________________________________________")
    print("Answers are")
    for i, q in enumerate(question):
        if ques == q: 
            index = i
            print("->", answer[i])
            break 
    print("\n___________________________________________________________________________________________________________")
        
    
print("s")
```

    s
    


```python
def main():
    chooseTheTopic()
    chooseTheNumber()
    print("Ask question")
    q = input().strip()
    index = askQuestion(q)
    displayContent(content[0])
    displayUrl(content[0])
if __name__ == "__main__":
    main()
```

    TOPICS TO SEARCH
    ----------------
    
    1 Abraham_Lincoln     2 Alessandro_Volta     3 Amedeo_Avogadro     4 Anders_Celsius     5 Ant     6 Antwerp     7 Arabic_language     8 Bee     9 Beijing     10 Berlin     11 Blaise_Pascal     12 Butterfly     13 Calvin_Coolidge     14 Canada     15 Cello     16 Charles-Augustin_de_Coulomb     17 Chinese_language     18 Copenhagen     19 Cougar     20 Cymbal     21 Dhaka     22 Dragonfly     23 Drum     24 Eel     25 Egypt     26 English_language     27 Finland     28 Finnish_language     29 Flute     30 Fox     31 French_language     32 Gerald_Ford     33 German_language     34 Ghana     35 Giant_Panda     36 Giraffe     37 Gray_Wolf     38 Grover_Cleveland     39 Guitar     40 Henri_Becquerel     41 Indonesia     42 Isaac_Newton     43 Italian_language     44 Jackson_Pollock     45 Jakarta     46 James_Monroe     47 James_Watt     48 Japanese_language     49 John_Adams     50 Koala     51 Korean_language     52 Kuala_Lumpur     53 Leonardo_da_Vinci     54 Liechtenstein     55 Lima     56 Lobster     57 London     58 Lyre     59 Malay_language     60 Melbourne     61 Michael_Faraday     62 Michelangelo     63 Millard_Fillmore     64 Montreal     65 Nairobi     66 Nassau     67 Nikola_Tesla     68 Norman_Rockwell     69 Octopus     70 Ottawa     71 Otter     72 Pablo_Picasso     73 Piano     74 Pierre-Auguste_Renoir     75 Portuguese_language     76 Qatar     77 Romania     78 Saint_Petersburg     79 San_Francisco     80 Santiago     81 Singapore     82 Spanish_language     83 Swahili_language     84 Swan     85 Swedish_language     86 Taipei     87 Theodore_Roosevelt     88 Tiger     89 Trumpet     90 Turkish_language     91 Turtle     92 Ulysses_S._Grant     93 Uruguay     94 Vietnamese_language     95 Vincent_van_Gogh     96 Violin     97 Woodrow_Wilson     98 Xylophone     99 Zebra     100 beetle     101 duck     102 elephant     103 kangaroo     104 leopard     105 otter     106 penguin     107 polar_bear     108 turtle     
    ___________________________________________________________________________________________________________
    


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
