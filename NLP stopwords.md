```python
import nltk
from nltk.corpus import stopwords
```


```python
print(stopwords.words('english'))
```

    ['i', 'me', 'my', 'myself', 'we', 'our', 'ours', 'ourselves', 'you', "you're", "you've", "you'll", "you'd", 'your', 'yours', 'yourself', 'yourselves', 'he', 'him', 'his', 'himself', 'she', "she's", 'her', 'hers', 'herself', 'it', "it's", 'its', 'itself', 'they', 'them', 'their', 'theirs', 'themselves', 'what', 'which', 'who', 'whom', 'this', 'that', "that'll", 'these', 'those', 'am', 'is', 'are', 'was', 'were', 'be', 'been', 'being', 'have', 'has', 'had', 'having', 'do', 'does', 'did', 'doing', 'a', 'an', 'the', 'and', 'but', 'if', 'or', 'because', 'as', 'until', 'while', 'of', 'at', 'by', 'for', 'with', 'about', 'against', 'between', 'into', 'through', 'during', 'before', 'after', 'above', 'below', 'to', 'from', 'up', 'down', 'in', 'out', 'on', 'off', 'over', 'under', 'again', 'further', 'then', 'once', 'here', 'there', 'when', 'where', 'why', 'how', 'all', 'any', 'both', 'each', 'few', 'more', 'most', 'other', 'some', 'such', 'no', 'nor', 'not', 'only', 'own', 'same', 'so', 'than', 'too', 'very', 's', 't', 'can', 'will', 'just', 'don', "don't", 'should', "should've", 'now', 'd', 'll', 'm', 'o', 're', 've', 'y', 'ain', 'aren', "aren't", 'couldn', "couldn't", 'didn', "didn't", 'doesn', "doesn't", 'hadn', "hadn't", 'hasn', "hasn't", 'haven', "haven't", 'isn', "isn't", 'ma', 'mightn', "mightn't", 'mustn', "mustn't", 'needn', "needn't", 'shan', "shan't", 'shouldn', "shouldn't", 'wasn', "wasn't", 'weren', "weren't", 'won', "won't", 'wouldn', "wouldn't"]
    


```python
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
```


```python
ex="""This is a sentence showing the example of stop words"""
stop_words=set(stopwords.words('english'))
word_tokens=word_tokenize(ex)
filtered_sentence=[w for w in word_tokens if not w in stop_words]
filtered_sentence=[]
for w in word_tokens:
    if w not in stop_words:
        filtered_sentence.append(w)
        
print(word_tokens) 
print(filtered_sentence)
```

    ['This', 'is', 'a', 'sentence', 'showing', 'the', 'example', 'of', 'stop', 'words']
    ['This', 'sentence', 'showing', 'example', 'stop', 'words']
    

Removing stop words from a file


```python
import io
from nltk.corpus import stopwords 
from nltk.tokenize import word_tokenize 
```


```python
stop_words=set(stopwords.words('english'))
```


```python
file=open("stopwords.txt")
```


```python
line=file.read()
words=line.split()
for r in words:
    if not r in stop_words:
        appendFile=open("filteredtext.txt",'a')
        appendFile.write(" "+r)
        appendFile.close()
```


```python

```
