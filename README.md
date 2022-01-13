# CogCompNLP
[![Build Status](http://morgoth.cs.illinois.edu:5800/app/rest/builds/buildType:(id:CogcompNlp_Build)/statusIcon)](http://morgoth.cs.illinois.edu:5800/)
[![Build status](https://ci.appveyor.com/api/projects/status/f53iv8435rq875ex/branch/master?svg=true)](https://ci.appveyor.com/project/bhargavm/illinois-cogcomp-nlp/branch/master)

This project collects a number of core libraries for Natural Language Processing (NLP) developed 
by [Cognitive Computation Group](https://cogcomp.org).  

## How to use it? 
Depending on the need, please follow one of the following items: 
 - **To annotate raw text** (i.e. no need to open the annotator boxes to retrain them) Follow [pipeline](pipeline/). 
 - **To train and test an NLP annotator** (i.e. you want to open an annotator box), see the list of components below and choose the desired one. We recommend using JDK8, as no other versions are officially supported and tested.
 - **To read a corpus** Follow [the corpus-readers](corpusreaders) module. 
 - **To do feature-extraction** Follow [edison](edison) module. 


## CogComp's main NLP libraries

Each library contains detailed instructions on how to use it. In addition the javadoc of the whole project is available [here](http://cogcomp.org/software/doc/apidocs/). 

| Module | Description |
|----------|------------|
| [nlp-pipeline](pipeline/README.md) | Provides an end-to-end NLP processing application that runs a variety of NLP tools on input text. |
| [core-utilities](core-utilities/README.md) | Provides a set of NLP-friendly data structures and a number of  NLP-related utilities that support writing NLP applications, running experiments, etc. |
| [corpusreaders](corpusreaders/README.md) | Provides classes to read documents from corpora into `core-utilities` data structures. |
| [curator](curator/README.md) | Supports use of [CogComp NLP Curator](http://cogcomp.org/page/software_view/Curator), a tool to run NLP applications as services. |
| [edison](edison/README.md) | Library for feature extraction from `core-utilities` data structures.  | 
| [lemmatizer](lemmatizer/README.md)  |  Uses [WordNet](https://wordnet.princeton.edu/) and simple rules to find the root forms of words in plain text. |
| [tokenizer](tokenizer/README.md) | Identifies sentence and word boundaries in plain text. |
| [transliteration](transliteration/README.md) | Transliterates names between different scripts. | 
| [pos](pos/README.md)  | Identifies the part of speech (e.g. verb + tense, noun + number) of each word in plain text.  |  
| [ner](ner/README.md) | Identifies named entities in plain text according to two different sets of categories.  |
| [md](md/README.md) | Identifies entity mentions in plain text.  |
| [relation-extraction](relation-extraction/README.md) | Identifies entity mentions, then identify relation pairs among the mentions detected.  |
| [quantifier](quantifier/README.md) | Detects mentions of quantities in the text, as well as normalizes it to a standard form. |
| [inference](inference/README.md) |  Suite of unified wrappers to a set optimization libraries, as well as some basic approximate solvers. |
| [depparse](depparse/README.md) | Identifies the dependency parse tree of a sentence. |
| [verbsense](verbsense/README.md) | This system addresses the verb sense disambiguation (VSD) problem for English. |
| [prepsrl](prepsrl/README.md) | Identifies semantic relations expressed by prepositions and develops statistical learning models for predicting the relations. |
| [commasrl](commasrl/README.md) | Extracts relations that commas participate in. |
| [similarity](similarity/README.md) | Compare objects --especially Strings-- and return a score indicating how similar they are. |
| [temporal-normalizer](temporal-normalizer/README.md) | Temporal extractor and normalizer.  |
| [dataless-classifier](dataless-classifier/README.md) | Classifies text into a user-specified label hierarchy from just the textual label descriptions |
| [external-annotators](external/README.md) | Collection useful external annotators.  |


**For additional queries:** Please follow [FAQs](faq.md).

## Using each library programmatically 

To include one of the modules in your Maven project, add the following snippet with the
   `#modulename#` and `#version` entries replaced with the relevant module name and the 
   version listed in this project's pom.xml file. Note that you also add to need the
   `<repository>` element for the CogComp maven repository in the `<repositories>` element.
    
```xml 
    <dependencies>
         ...
        <dependency>
            <groupId>edu.illinois.cs.cogcomp</groupId>
            <artifactId>#modulename#</artifactId>
            <version>#version#</version>
        </dependency>
        ...
    </dependencies>
    ...
    <repositories>
        <repository>
            <id>CogCompSoftware</id>
            <name>CogCompSoftware</name>
            <url>http://cogcomp.org/m2repo/</url>
        </repository>
    </repositories>
```

### Citing 
If you are using the framework, please cite our paper: 
```
@inproceedings{2018_lrec_cogcompnlp,
    author = {Daniel Khashabi, Mark Sammons, Ben Zhou, Tom Redman, Christos Christodoulopoulos, Vivek Srikumar, Nicholas Rizzolo, Lev Ratinov, Guanheng Luo, Quang Do, Chen-Tse Tsai, Subhro Roy, Stephen Mayhew, Zhili Feng, John Wieting, Xiaodong Yu, Yangqiu Song, Shashank Gupta, Shyam Upadhyay, Naveen Arivazhagan, Qiang Ning, Shaoshi Ling, Dan Roth},
    title = {CogCompNLP: Your Swiss Army Knife for NLP},
    booktitle = {11th Language Resources and Evaluation Conference},
    year = {2018},
    url = "http://cogcomp.org/papers/2018_lrec_cogcompnlp.pdf",
}
```
