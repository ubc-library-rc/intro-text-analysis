---
layout: default
title: NLTK
parent: Tools and Methods
nav_order: 2
---
# NLTK Overview

NLTK is a set of tools that, similar to Voyant, let you quickly accomplish some of the core tasks in text mining, preparation, and analysis. It is free and open source and a component of Python. The core benefits of using a tool like NLTK is the high level of flexibility with how you interact with the corpus of text that you are analyzing. While the learning curve is higher, NLTK has many openly available tutorials for beginners. Learning Python, the language NLTK is working within, is also an easily transferrable skill.

## Exploring text with NLTK

NLTK comes with a default corpus of several books from [Project Gutenberg](https://www.gutenberg.org/). You can explore it by calling on "nltk.corpus.gutenberg". This is what we will be using throughout this session.

### POS (Part of Speech) Tagging

Input
{: .label .label-green}
~~~ Python
s = "Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world. "
words = nltk.tokenize.word_tokenize(s)
nltk.pos_tag(words)
~~~

Output
{: .label .label-yellow}
~~~
[('Call', 'VB'),
 ('me', 'PRP'),
 ('Ishmael', 'NNP'),
 ('.', '.'),
 ('Some', 'DT'),
 ('years', 'NNS'),
 ('ago—never', 'RB'),
 ('mind', 'VB'),
 ('how', 'WRB'),
 ('long', 'JJ'),
 ('precisely—having', 'JJ'),
 ('little', 'JJ'),
 ('or', 'CC'),
 ('no', 'DT'),
 ('money', 'NN'),
 ('in', 'IN'),
 ('my', 'PRP$'),
 ('purse', 'NN'),
 (',', ','),
 ('and', 'CC'),
 ('nothing', 'NN'),
 ('particular', 'JJ'),
 ('to', 'TO'),
 ('interest', 'NN'),
 ('me', 'PRP'),
 ('on', 'IN'),
 ('shore', 'NN'),
 (',', ','),
 ('I', 'PRP'),
 ('thought', 'VBD'),
 ('I', 'PRP'),
 ('would', 'MD'),
 ('sail', 'VB'),
 ('about', 'IN'),
 ('a', 'DT'),
 ('little', 'JJ'),
 ('and', 'CC'),
 ('see', 'VB'),
 ('the', 'DT'),
 ('watery', 'JJ'),
 ('part', 'NN'),
 ('of', 'IN'),
 ('the', 'DT'),
 ('world', 'NN'),
 ('.', '.')]
~~~

### Tokenization
Tokenization is the process of segementing text into parts such as words or sentences to aid in lexical analysis. NLTK supports tokenization for English, Spanish and most European languages.

#### Sentence Tokenization
Input
{: .label .label-green}
~~~ Python
from nltk.tokenize import sent_tokenize
text="Call me Ishmael. Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world. It is a way I have of driving off the spleen and regulating the circulation. Whenever I find myself growing grim about the mouth; whenever it is a damp, drizzly November in my soul; whenever I find myself involuntarily pausing before coffin warehouses, and bringing up the rear of every funeral I meet; and especially whenever my hypos get such an upper hand of me, that it requires a strong moral principle to prevent me from deliberately stepping into the street, and methodically knocking people’s hats off—then, I account it high time to get to sea as soon as I can. This is my substitute for pistol and ball. With a philosophical flourish Cato throws himself upon his sword; I quietly take to the ship. There is nothing surprising in this. If they but knew it, almost all men in their degree, some time or other, cherish very nearly the same feelings towards the ocean with me."
tokenized_text=sent_tokenize(text)
print(tokenized_text)
~~~

Output
{: .label .label-yellow}
~~~
['Call me Ishmael.', 'Some years ago—never mind how long precisely—having little or no money in my purse, and nothing particular to interest me on shore, I thought I would sail about a little and see the watery part of the world.', 'It is a way I have of driving off the spleen and regulating the circulation.', 'Whenever I find myself growing grim about the mouth; whenever it is a damp, drizzly November in my soul; whenever I find myself involuntarily pausing before coffin warehouses, and bringing up the rear of every funeral I meet; and especially whenever my hypos get such an upper hand of me, that it requires a strong moral principle to prevent me from deliberately stepping into the street, and methodically knocking people’s hats off—then, I account it high time to get to sea as soon as I can.', 'This is my substitute for pistol and ball.', 'With a philosophical flourish Cato throws himself upon his sword; I quietly take to the ship.', 'There is nothing surprising in this.', 'If they but knew it, almost all men in their degree, some time or other, cherish very nearly the same feelings towards the ocean with me.']
~~~

### Word Tokenization
Input
{: .label .label-green}
~~~ Python
from nltk.tokenize import word_tokenize
tokenized_word=word_tokenize(text)
print(tokenized_word)
~~~

Output
{: .label .label-yellow}
~~~
['Call', 'me', 'Ishmael', '.', 'Some', 'years', 'ago—never', 'mind', 'how', 'long', 'precisely—having', 'little', 'or', 'no', 'money', 'in', 'my', 'purse', ',', 'and', 'nothing', 'particular', 'to', 'interest', 'me', 'on', 'shore', ',', 'I', 'thought', 'I', 'would', 'sail', 'about', 'a', 'little', 'and', 'see', 'the', 'watery', 'part', 'of', 'the', 'world', '.', 'It', 'is', 'a', 'way', 'I', 'have', 'of', 'driving', 'off', 'the', 'spleen', 'and', 'regulating', 'the', 'circulation', '.', 'Whenever', 'I', 'find', 'myself', 'growing', 'grim', 'about', 'the', 'mouth', ';', 'whenever', 'it', 'is', 'a', 'damp', ',', 'drizzly', 'November', 'in', 'my', 'soul', ';', 'whenever', 'I', 'find', 'myself', 'involuntarily', 'pausing', 'before', 'coffin', 'warehouses', ',', 'and', 'bringing', 'up', 'the', 'rear', 'of', 'every', 'funeral', 'I', 'meet', ';', 'and', 'especially', 'whenever', 'my', 'hypos', 'get', 'such', 'an', 'upper', 'hand', 'of', 'me', ',', 'that', 'it', 'requires', 'a', 'strong', 'moral', 'principle', 'to', 'prevent', 'me', 'from', 'deliberately', 'stepping', 'into', 'the', 'street', ',', 'and', 'methodically', 'knocking', 'people', '’', 's', 'hats', 'off—then', ',', 'I', 'account', 'it', 'high', 'time', 'to', 'get', 'to', 'sea', 'as', 'soon', 'as', 'I', 'can', '.', 'This', 'is', 'my', 'substitute', 'for', 'pistol', 'and', 'ball', '.', 'With', 'a', 'philosophical', 'flourish', 'Cato', 'throws', 'himself', 'upon', 'his', 'sword', ';', 'I', 'quietly', 'take', 'to', 'the', 'ship', '.', 'There', 'is', 'nothing', 'surprising', 'in', 'this', '.', 'If', 'they', 'but', 'knew', 'it', ',', 'almost', 'all', 'men', 'in', 'their', 'degree', ',', 'some', 'time', 'or', 'other', ',', 'cherish', 'very', 'nearly', 'the', 'same', 'feelings', 'towards', 'the', 'ocean', 'with', 'me', '.']
~~~

### Frequency distribution
Building on what we've already done, NLTK allows us to see what the frequency distribution of our tokenized text is.

Input
{: .label .label-green}
~~~ Python
from nltk.probability import FreqDist
import matplotlib.pyplot as plt
fdist = FreqDist(tokenized_word)
fdist.plot(10,cumulative=False)
plt.show()
~~~

Output
{: .label .label-yellow}
![Frequency Plot]({{site.baseurl}}/content/frequency-plot.png)

## Next Steps: Sentiment analysis
There is a lot more that you can do with NLTK that we will not cover in this session.

- lexicon based SA
- machine learning based SA
