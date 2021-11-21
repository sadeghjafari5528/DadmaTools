<!-- <h1 align="center">
  <img src="images/dadmatech.jpeg"  width="150"  />
   Dadmatools
</h1> -->


<h2 align="center">Dadmatools: A Python NLP Library for Persian</h2>

<div align="center">
  <a href="https://pypi.org/project/dadmatools/"><img src="https://img.shields.io/pypi/v/dadmatools.svg"></a>
  <!-- <a href="https://travis-ci.com/dadmatech/dadmatools"><img src="https://travis-ci.com/dadmatech/dadmatools.svg?branch=master"></a> -->
  <!-- <a href="https://coveralls.io/github/alexandrainst/danlp?branch=master"><img src="https://coveralls.io/repos/github/alexandrainst/danlp/badge.svg?branch=master"></a> -->
  <a href=""><img src="https://img.shields.io/badge/license-Apache%202-blue.svg"></a>
  <!-- <a href=''><img src='https://readthedocs.org/projects/danlp-alexandra/badge/?version=latest' alt='Documentation Status' /></a> -->
</div>
<div align="center">
  <h5>
      Part of Speech Tagging
    <span> | </span>
      Dependency Parsing
  </h5>
  <h5>
      Constituency Parsing
    <span> | </span>
      Chunking
  </h5>
  <h5>
      Tokenizer
    <span> | </span>
      Lemmatizer
  </h5>
  <h5>
    <!-- <a href="https://github.com/alexandrainst/danlp/tree/master/examples/tutorials">
      Tutorials
    </a> -->
  </h5>
</div>


# **DadmaTools**
Dadmatools is a repository for Natural Language Processing resources for the Persian Language. 
The aim is to make it easier and more applicable to practitioners in the industry to use 
Persian NLP and hence this project is licensed to allow commercial use. 
The project features code examples on how to use the models in popular 
NLP frameworks such as spaCy and Transformers as well as Deep Learning frameworks 
such as PyTorch. 
for more details about how to use this tool read the instruction below. 


## Installation

To get started using DaNLP in your python project simply install the pip package. Note that installing the default pip package 
will not install all NLP libraries because we want you to have the freedom to limit the dependency on what you use. Instead we provide you with an installation option if you want to install all the required dependencies. 

### Install with pip

To get started using DadmaTools simply install the project with pip:

```bash
pip install dadmatools 
```

Note that the default installation of DadmaTools does install other NLP libraries such as SpaCy and supar.

You can check the `requirements.txt` file to see what version the packages has been tested with.

### Install from github
Alternatively you can install the latest version from github using:
```
pip install git+https://github.com/Dadmatech/dadmatools.git
```

## NLP Models

Natural Language Processing is an active area of research and it consists of many different tasks. 
The Dadmatools repository provides an overview of Persian models for some of the most common NLP tasks (and is continuously evolving). 

Here is the list of NLP tasks we currently cover in the repository.
-  Part of speech tagging
-  Dependency parsing
-  Constituency parsing
-  Chunking
-  Lemmatizing
-  Tokenizing

### Use Case

These NLP tasks are defined as pipelines. Therefore, a pipeline list must be created and passed through the model. This will allow the user to choose the only task needed without loading others. 
Each task has its abbreviation as following:
-  ```pos```: Part of speech tagging
-  ```dep```: Dependency parsing
-  ```cons```: Constituency parsing
-  ```chunk```: Chunking
-  ```lem```: Lemmatizing
-  ```tok```: Tokenizing

Note that if no pipeline is passed to the model the tokenizer will be load as default.

```
import dadmatools.pipeline.language as language

# here lemmatizer and pos tagger will be loaded
# as tokenizer is the default tool, it will be loaded as well even without calling
pips = 'lem,pos' 
nlp = language.Pipeline('lem')

# you can see the pipeline with this code
print(nlp.analyze_pipes(pretty=True))

# doc is an SpaCy object
doc = nlp('از قصهٔ کودکیشان که می‌گفت، گاهی حرص می‌خورد!')
```
[```doc```](https://spacy.io/api/doc) object has different extensions. First, there is ```sentences``` in ```doc``` which is the list of the list of [```Token```](https://spacy.io/api/token). Each [```Token```](https://spacy.io/api/token) also has its own extentions. Note that we defined our own extention as well in DadmaTools. If any pipeline related to the that specific extentions is not called, that extention will have no value.
```
sentences = doc._.sentences
for sentence in sentences:
    text = sentence.text
    for token in sentences:
        token_text = token.text
        lemma = token.lemma_
        pos_tag = token.pos_
        dep = token.dep_
        dep_arc = token._.dep_arc
    sent_constituency = sentence._.constituency
    sent_chunks = sentence._.chunks
```
Note that ```_.constituency``` and ```_.chunks``` are the object of [SuPar](https://parser.yzhang.site/en/latest/) class.


## Cite
Will be added in future.
<!-- 
If you want to cite this project, please use the following BibTeX entry: 

```
@inproceedings{
}
``` -->

<!-- Read the paper here.  -->
