---
author-meta:
- Tiago Lubiana
bibliography:
- content/manual-references.json
date-meta: '2020-09-14'
header-includes: "<!--\nManubot generated metadata rendered from header-includes-template.html.\nSuggest improvements at https://github.com/manubot/manubot/blob/master/manubot/process/header-includes-template.html\n-->\n<meta name=\"dc.format\" content=\"text/html\" />\n<meta name=\"dc.title\" content=\"ANN: A platform to annotate text with Wikidata IDs\" />\n<meta name=\"citation_title\" content=\"ANN: A platform to annotate text with Wikidata IDs\" />\n<meta property=\"og:title\" content=\"ANN: A platform to annotate text with Wikidata IDs\" />\n<meta property=\"twitter:title\" content=\"ANN: A platform to annotate text with Wikidata IDs\" />\n<meta name=\"dc.date\" content=\"2020-09-14\" />\n<meta name=\"citation_publication_date\" content=\"2020-09-14\" />\n<meta name=\"dc.language\" content=\"en-US\" />\n<meta name=\"citation_language\" content=\"en-US\" />\n<meta name=\"dc.relation.ispartof\" content=\"Manubot\" />\n<meta name=\"dc.publisher\" content=\"Manubot\" />\n<meta name=\"citation_journal_title\" content=\"Manubot\" />\n<meta name=\"citation_technical_report_institution\" content=\"Manubot\" />\n<meta name=\"citation_author\" content=\"Tiago Lubiana\" />\n<meta name=\"citation_author_institution\" content=\"Computational Systems Biology Laboratory, University of S\xE3o Paulo\" />\n<meta name=\"citation_author_orcid\" content=\"0000-0003-2473-2313\" />\n<meta name=\"twitter:creator\" content=\"@johndoe\" />\n<link rel=\"canonical\" href=\"https://lubianat.github.io/ann_sprint/\" />\n<meta property=\"og:url\" content=\"https://lubianat.github.io/ann_sprint/\" />\n<meta property=\"twitter:url\" content=\"https://lubianat.github.io/ann_sprint/\" />\n<meta name=\"citation_fulltext_html_url\" content=\"https://lubianat.github.io/ann_sprint/\" />\n<meta name=\"citation_pdf_url\" content=\"https://lubianat.github.io/ann_sprint/manuscript.pdf\" />\n<link rel=\"alternate\" type=\"application/pdf\" href=\"https://lubianat.github.io/ann_sprint/manuscript.pdf\" />\n<link rel=\"alternate\" type=\"text/html\" href=\"https://lubianat.github.io/ann_sprint/v/c0f258a96151e4f8ff79e79438818ca5d884b469/\" />\n<meta name=\"manubot_html_url_versioned\" content=\"https://lubianat.github.io/ann_sprint/v/c0f258a96151e4f8ff79e79438818ca5d884b469/\" />\n<meta name=\"manubot_pdf_url_versioned\" content=\"https://lubianat.github.io/ann_sprint/v/c0f258a96151e4f8ff79e79438818ca5d884b469/manuscript.pdf\" />\n<meta property=\"og:type\" content=\"article\" />\n<meta property=\"twitter:card\" content=\"summary_large_image\" />\n<link rel=\"icon\" type=\"image/png\" sizes=\"192x192\" href=\"https://manubot.org/favicon-192x192.png\" />\n<link rel=\"mask-icon\" href=\"https://manubot.org/safari-pinned-tab.svg\" color=\"#ad1457\" />\n<meta name=\"theme-color\" content=\"#ad1457\" />\n<!-- end Manubot generated metadata -->"
keywords:
- wikidata
- Europe PMC
- annotation
lang: en-US
manubot-clear-requests-cache: false
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
title: 'ANN: A platform to annotate text with Wikidata IDs'
...






<small><em>
This manuscript
([permalink](https://lubianat.github.io/ann_sprint/v/c0f258a96151e4f8ff79e79438818ca5d884b469/))
was automatically generated
from [lubianat/ann_sprint@c0f258a](https://github.com/lubianat/ann_sprint/tree/c0f258a96151e4f8ff79e79438818ca5d884b469)
on September 14, 2020.
</em></small>

## Authors



+ **Tiago Lubiana**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-2473-2313](https://orcid.org/0000-0003-2473-2313)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [lubianat](https://github.com/lubianat)
    · ![Twitter icon](images/twitter.svg){.inline_icon}
    [johndoe](https://twitter.com/johndoe)<br>
  <small>
     Computational Systems Biology Laboratory, University of São Paulo
  </small>



## Abstract {.page_break_before}




# Individual contributions 

All contributors participated in the discussions about the platform design, the directions of the project and on the draft of this manuscript.    

Additionally: 

- I.H.G.P , A.D.R, D.F, T.L, G.N.V and D.A. contributed to the manual annotation of scientific articles. 

- S.W. and A.G worked on the analysis of Natural Language Processing software and on the integration of sci spaCy to Wikidata. 

- D.A. made connections with Europe PMC and designed the frond-end mockup. 

- A.D.R. organized the survey of the researchers’ views 

- G.N.V , D.F and A.D.R.  discussed and wrote the community aspects on benefits of annotation and research incentives. 

- B.A.P designed the logo.

- T.L, D.W, I.H.G.P worked on extracting patterns from manual annotations 

- T.L proposed the initial idea, and oversaw the project. 


# Introduction

Most scientific findings are communicated via scientific papers. In these papers knowledge is encoded in language, which makes it difficult for computers to search for facts. Additionally, millions of articles are produced every year, which makes it virtually impossible to keep track of current biomedical knowledge without the aid of computational tools. 

Annotation - linking words in scientific texts with external identifiers - is a ground step to automatically process biomedical knowledge. The annotation of biomedical articles is part of the work of biocurators, professionals dedicated to parse and make knowledge available on databases. These annotations, usually based on ontologies (sets of organized concepts)  already power core platforms used by the research community, such as ZFIN and UniProt. (Note that the meaning of "annotation" used here is different from sharing written notes about ideas on the text such as proposed by hypothes.is).

Even though  biomedical databases are extremely valuable, they are limited to specific subsets of human knowledge. It would be a colossal challenge to annotate text if we needed to look for the right ontology for each kind of concept. 


Wikidata is a possible solution for this challenge. It is knowledge base that contains more than 80 million varied concepts: “p53, “malaria”, “Douglas Adams”, “Brazil” and much more.  Moreover, anyone can contribute with new concepts (and relations between them) to Wikidata, which makes it flexible enough to accommodate the vast amount of concepts used in research articles.


During the 2-day hackathon eLife Sprint 2020, we hot-started a project for annotating concepts in scientific articles to Wikidata, envisioning integration with Europe PMC’s Annotation API. We brainstormed both technical and practical aspects of developing a tool to gather crowd-annotations of scientific concepts. Inspired by other scientific games (like Mark2cure, eterna and foldit), we designed a gamified interface for crowdsourcing scientific annotations. Additionally, we studied Natural Language Processing approaches for extracting scientific entities, and assembled a series of perspectives on how to implement such an annotation tool in the current research environment.  

This document contains reports on the different branches of the project, coupled to thoughts of the participants on how to achieve the overarching goal of annotating all scientific text. 
Given the short time for the event, some parts of the report are not completely structured. Nevertheless, we believe that they can be useful for accessing the development of the project. 

### Community biocuration  projects

We note that this is not the first shot at organizing biomedical information by harnessing the power of the crowd. Some notable examples:

* PomBase (a base of information related to Schizosaccharomyces pombe) has a wonderful system for annotation articles to a set of OBO ontologies: https://github.com/pombase/canto [@doi:10.1093/database/baaa028]
* [UniProt has a community curation branch, which is under active development](http://insideuniprot.blogspot.com/2019/07/)
* Mark2Cure was a project with goals really similar to the Annotate Them All project, with some [very nice publications](https://mark2cure.org/blog/thank-you-campaign-pause/)  and a [GitHub page](https://github.com/SuLab/mark2cure/issues) [@doi:10.1093/bioinformatics/btz678]
* Cochrane has a crowd-annotation platform targeted at clinical trials: [Cochrane Crowd](https://crowd.cochrane.org/)


"Annotate them all" can be useful for these (and similar) projects, by providing coarse, community annotations for the dedicated, expert curator teams of bases such as UniProt and PomBase. 


# Tasks

Tasks developed at the hackathon
At the hackathon we worked on the following tasks:

- Deploy a pilot survey of the researchers’ views on annotating of scientific texts
- Develop code for selecting candidate concepts for annotations (using the NLP package scispacy) 
Review works related to annotation of texts and how they relate to the project. 
- Analyse the incentive structure and how to engage researchers in the annotation of scientific texts
- Manually annotate a sample of biomedical publications to Wikidata IDs and compare them to currently annotated pieces of text on Europe PMC
- Extract patterns related to the availability of annotated concepts in Wikidata.
- Design a logo and a name for the project
- Design an user interface and prepare a mockup “front-end”. 


# Why is annotation important?
Two main contributions of annotations are to clarify the meaning of texts  and enable programmatically processing.

## Clarify scientific prose

- *__Disambiguation of concepts and abbreviations__*: Words can have different meanings in different contexts. With annotations, selected words in a scientific article or abstract are linked to a concept in a knowledge base (e.g. Wikidata) and can be clearly disambiguated. Ultimately, this helps readers better understand the content of scientific articles.
- *__Science communication__*: through an enriched layer, annotations help convey complex information to the general public. It is possible to implement a “hover” function (similar to that in Wikipedia), where the user could hover above a word and you see the definition of a concept.
Programmatically process articles 
Semantic enrichment: annotations enrich a scientific article with an additional layer of machine-readable information, providing more in-depth information about a concept or linking it to other sources of information.

The semantic enrichment layer unleashes the biomedical knowledge constrained in biomedical articles to the world of the semantic web. The connections of concepts, then, can impact a number of different aspects of research: 

## Programmatically process articles 
- *__Semantic enrichment__*: annotations enrich a scientific article with an additional layer of machine-readable information, providing more in-depth information about a concept or linking it to other sources of information.

The semantic enrichment layer unleashes the biomedical knowledge constrained in biomedical articles to the world of the semantic web. The connections of concepts, then, can impact a number of different aspects of research: 


- *__Integration of different sources of information__*: annotations can help us find information related to any given concept, regardless of its source. From the perspective of the researcher, this can improve  the visibility of their work, making it reachable for the ones interested in the area.  
- *__Improvement of document classification: annotation can help automated document classification, making it easier to search these documents.
- *__Search for complex questions__*: Text annotated with Wikidata IDs (semantically enriched) are readable by computers. This enables better discovery mechanisms (and not just left as words). Moreover, Wikidata is a knowledge graph, and concepts are linked to each other. That makes if possible to leverage the collective knowledge embedded in the graph to make powerful queries, such as: “Which articles produced by alumni of my university mention drugs that block NMDA receptors?” , “Which cell lines are used for research that deals with respiratory viruses”?. 
- *__Improve openness of research__*: annotations in a paper that link to an open knowledge base increase the openness of an article in accordance to the FAIR principles of Findability, Accessibility, Interoperability and Reusability. Our work focus on annotations compatible with the EuropePMC API (which uses the W3C standard and encodes annotations in a RDF-compatible format), therefore making annotations quickly available via the API itself and wrappers, such as the R package europe PMC.



# Related softwares for annotation

The task of connecting mentions in scientific texts to identifiers in databases has been researched in both the biomedical and the natural language processing communities. There have been many approaches to automate this task. This is different from our human-in-the-loop approach. Nevertheless different components can help us to select candidates that we present to the annotators.

Of note, there have also been previous approaches for annotating documents using Wikipedia [@doi:10.1109/WIIAT.2008.56]

## Overview
-   Open Tapioka
    -   Recognizes entities and links them to Wikidata, but only for person, location organization
    -   Could be retrained with a subset of Wikidata that would contain only biomedical entities
-   Sci Spacy
    -   Entity detection and linking to UMLS ID
    -   Linked WikiText-2 Project
    -   Does Entity identification, Annotation with Wikidata entries.
    -   The project utilizes Stanford CoreNLP  
-   Doccano
    -   Does Entity identification, Sentiment analysis.
-   BERN
    -   Uses contextualized word embeddings, which might have higher accuracy than sci Spacy
    -   Does Entity Identification, Entity typing

### Open Tapioka

- [github repo](https://github.com/wetneb/opentapioca)
- [online demo](https://opentapioca.org/#)
- [paper](https://arxiv.org/pdf/1904.09131.pdf)
- [documentation](https://opentapioca.readthedocs.io/en/latest/)

#### System description 
Input is a sentence. Output is the sentence, with all persons, locations and organizations linked to their respective Wikidata identifier. The system is trained solely on Wikidata. The authors use occurrence statistics of concepts in Wikidata and in text to compute the likelihood of a certain word in the text linking to a certain Wikidata item (e.g. “Barack Obama” linking to “Q76”). To take context into account independently computed local features are propagated along a Markov chain. The authors claim that this system is lightweight and easy to retrain, and therefore easily adapts to the frequent changes of Wikidata. They say that restricting their system to only people, organizations and locations enabled them to do well without using any other data but Wikidata, while other approaches do rely on additional text from Wikipedia.

#### How feasible is this system for our project
Using only Wikidata to train the system is a good asset, because this might keep training times low. The authors are right in claiming that their system is lightweight: It does not use word embeddings or extensive language models but derives the necessary information about word similarities from Wikidata itself. The author states that this approach worked for relatively common entities, so it is unclear whether we can adapt it to less common biological entities. Testing the system on the cited website gave reasonably good results for less common names of people and cities, but was prone to misinterpret words that were not people, organization or locations as such (e.g. in the sentence “Banks are often closed.” the words “Banks” and “closed” were linked to locations). The documentation seems generally very good. 

#### Questions/Answers:

- How does the system pick out only people, locations and organizations? This is done before training, by using only entities of those categories in the training data set. (see documentation [here](https://opentapioca.readthedocs.io/en/latest/indexing.html))
- How easily can this be changed in the code? If we had a dump of Wikidata containing only biological entities we could use it to train on as described, no changes to the code itself needed! 

### Sci Spacy

- [github link](https://allenai.github.io/scispacy/)
- [online demo](https://scispacy.apps.allenai.org/)
- [paper](https://arxiv.org/pdf/1902.07669.pdf)

### System  description
The input is a sentence. The output is a sentence with the biomedical entities in that sentence annotated with canonical names, concept IDs and TUI(s). 

#### How feasible is this system for our project: 
This looks nearly perfect for candidate generation.

#### Questions:

- Are the IDs provided there in any way meaningful for linking them to Wikidata? Yes! (See section below) 

### Doccano

- [code base](https://github.com/doccano/doccano)
- [demo](http://doccano.herokuapp.com/)

Comments:
-   Entity identification; Sentiment analysis.

### Linked WikiText-2 Project

- [codebase](https://github.com/rloganiv/kglm-data)
- [demo](https://rloganiv.github.io/linked-wikitext-2/#/explore)
- [backbone](https://stanfordnlp.github.io/CoreNLP/corenlp-server.html)

Entity identification; Annotation with Wikidata entries; the project utilizes Stanford CoreNLP  



### BERN

- [code base](https://github.com/dmis-lab/bern)
- [demo](https://bern.korea.ac.kr/)

Uses contextualized word embeddings, which might have higher accuracy than sci Spacy
Does Entity Identification, Entity typing


## Applicability of the sciSpacy tool

The input for the software backend are abstracts of scientific articles that are loaded from Europe PMC using the Europe PMC API. We then use sci Spacy to detect entities in the abstract. Sci Spacy annotates those entities with their ID in the Unified Medical Language System (UMLS).  

Notably, 26 thousand items in Wikidata have an UMLS ID, which allows to link the items that were detected by sciSpacy to be connected to Wikidata. We pinpoint a couple challenges: 

The pre-trained scispacy models are unable to identify the entity if it has conjunctions and prepositions in it. To improve the entity detection performance the model needs to be retrained using manually curated scientific word lists.
Sci spacy does not use contextualized word embeddings, which impacts the precision of retrieved entities (the model employed in sci Spacy is derived from this reference[@doi:10.18653/v1/N16-1030]).  

Other approaches use  contextualized word embeddings for detecting and normalizing biomedical entities (such as  https://bern.korea.ac.kr/).  They could be used in the project in  addition to scispacy.

Besides UMLS IDs, sciSpacy also can match concepts a number of MeSH IDs, which can also be linked to Wikidata items. 

We wrote code in a Google Colab notebook to concatenate the Europe PMC API with sciSpacy and Wikidata. After retrieving the abstract of an article via its PMID, the function extracts relevant concepts via sciSpacy and match the ones with PMIDs to Wikidata. 
The output of the pipeline is depicted in the Figure @arup and the code is available in the [project github repository]https://github.com/lubianat/ann)

![ Concatenation of the Europe PMC API to Wikidata and sciSpacy
](images/arup.png){#fig:arup}

# Software Frontend

A mockup of the frontend is available in Figure @fig:front  and the rules used for the user interface design are shown in Figure @fig:miro. The main idea is to make annotations made with ANN fun for annotators. Users will be able to search for a publication by PMID or title. ANN boxes will be filled in with title and abstract. Annotations  will work in a task manner where annotators will be asked to annotate a type of entity or sentence and be rewarded with ANN badge points.

When selecting a text for annotation, a window will popup and users will be able to select terms from Wikidata. The annotations will be saved in a format that is compatible with Europe PMC annotations submission system, which would add Wikidata annotations to the Europe PMC SciLite annotations features. Users would be able to login with an ORCID account and ANN would allow them to claim their annotations work to their ORCID account.

![ Mockup prototype of the frontend of ANN
](images/front.png){#fig:front}

![ [Miro](https://miro.com/app/dashboard/) board for brainstorming of the functionalities of the user interface. 
](images/front.png){#fig:miro}



# Manual annotations: case report

We manually annotated a sample of biomedical publications (some of which from eLife) to extract information from their abstracts as a prototype for the platform. These annotations were made mostly by people from a research-lab background, which were presented to Wikidata during this project. In that sense, they mimic what a researcher could annotate when using the ANN platform. 

The annotations and notes are available in the attached table: [Manual Annotations Spreadsheet](https://docs.google.com/spreadsheets/d/1jmqW9GV04rxFwPiyidGOLN0NUzN-OWfzCkqB7RdwJbY/edit#gid=543386109). 

The following observations were made:


Annotation of PMID 19268344 [@pubmed:19268344]

“Ankyrin G” was not found on  Wikidata, but only "ankyrin". The [ankirin](https://www.wikidata.org/wiki/Q414971) item on Wikidata refers to a [protein family](https://www.wikidata.org/wiki/Q84467700), and not to the  protein itself. Later, we noticed that “Ankyrin G” was actually present on Wikidata ([here](https://www.wikidata.org/w/index.php?title=Q21981188) or [here](https://www.wikidata.org/wiki/Q21131080)), but at the moment the exact term “Ankyrin G” was not listed as one alias. 

- A1 - Concepts might be present on Wikidata, but not with the exact wording they appear in scientific texts.

- A2 - The abstract of the text does not mention if the study is dealing with humans or mouse cells! Digging into the text, it mentions that "Dissociated hippocampal neurons were prepared from embryonic E18 rats.” The actual annotation would be [this](https://www.wikidata.org/wiki/Q28558025), but this was impossible to tell given the abstract! Annotation would solve this, and the authors would be the best to disambiguate. 

Given A3, There are some things that should always be annotated, such as the species. Which kind of things should be always annotated? How should they be required? Things such as the species of the organisms used in the study, and the techniques used to assess the question. Maybe if journals require a semantic abstract, a structured abstract with semantically enriched knowledge, some of this problems would be bypassed. 

The concept of “[hippocampal neurons](https://www.wikidata.org/wiki/Q98842773)” was not identified separately on Wikidata, just the concepts for “[hippocampus](https://www.wikidata.org/wiki/Q48360)” and “[neuron](https://www.wikidata.org/wiki/Q43054)”. Notably, even these two concepts are represented in an species-independent way. The ideal annotations would be precise for the taxon of interest. 

- A3 - Compound concepts might be split on Wikidata on its building parts. However, as per the view of the annotator, “hippocampal neuron” can be understood as an individual concept. This illustrates an  open challenge of annotation: do we annotate the parts, or do we annotate the complete concept? 


AIS, the acronym for “Axon Initial Segment” did not have a string-match on Wikidata. Notably, the concept is [present on Wikidata](https://www.wikidata.org/wiki/Q14862704) , but not the wording of the acronym, making this an instance of the problem A1 (lack of exact name). 

- A4 - The AIS acronym is present on Wikidata but for many different things (like the Australian Institute of Sport and in situ pulmonary adenocarcinoma).  Acronyms are tricky, and might need disambiguation before matching to the database. Some NLP programs like spacy have acronym disambiguation modules. 
Adding a concept to Wikidata in the perspective of a new user

# Adding a concept to Wikidata in the perspective of a new user

The concept of  “[hippocampal neurons](https://www.wikidata.org/wiki/Q98842773)”   was created on Wikidata by a new editor. However, the creation of an item in an ontology is a challenging task. The terms used are not common for the biological research workflow. These are the perceptions of one of the team members, when creating an Wikidata item for the first time: 

_

- LABEL: main annotation for the concept. This is what would be used from SpaCY,
- DESCRIPTION: what the annotation refers to. As simple as possible. Simple words, it can reference other concepts.
- ALSO KNOWN AS/ alias : other concepts that mean the same thing (I wonder whether this could be “counted” as one, if referencing throughout an abstract). For example, when writing an abstract you use “different words” for the same thing to avoid repetition, would this be understood as one same concept if they are linked ?
(in multiple languages): All this can be done in multiple languages: 
- When adding statements:
    - you can specify if the concept is a subcategory of a different concept: SUBCLASS OF
    - you can specify if the concept is an example of a different concept:  INSTANCE OF 
    - You can also specify if the concept is PART OF: I take this to be as part of a bigger system, not necessarily immediate subclass. But this can be tricky to distinguish I think.
    - You can add an IMAGE to better describe it."_

This is the first report (as of our knowledge) of a biology researcher perspective when faced with the task of adding a new item to Wikidata. 

Given the complexity of ontological modelling, the report shows that the task is feasible. Adding a concept without training in semantic technology makes Wikidata a powerful tool, as the barrier of contribution is much lower than the one for current ontologies. The entries can be, then, adjusted later by the community, if necessary. 

Annotation of PMID 31254741 [@pubmed:31254741]

This article is related to drosophila research. Drosophila genes have frequently funny names, which might be mistaken for other entities. For the gene [frizzled](https://www.wikidata.org/wiki/Q29715259), the system worked nicely. We could find the Wikidata entry by typing "frizzled" but the official name is "fz".  The [protein](https://www.wikidata.org/wiki/Q29812172) is also present, and the researchers would have to choose if they are talking about the gene or its product. 

The Van Gogh protein, on the other hand,  does not show up on Wikidata, just the [dutch post-impressionist painter](https://www.wikidata.org/wiki/Q5582). For this case, the protein is not on Wikidata, but the [protein-coding gene](https://www.wikidata.org/wiki/Q29723017) is, but it gets “buried” amidst the references to the painter.  
 

- B1 - Many entities may have the same name, even when dealing with full words (and not acronyms). This ambiguity cannot be solved by looking at the word, and it might be solvable (at least partially) by looking at the context. 

- B2 - A biologically similar entity might be present, but in a slightly different way (for example, gene entry when talking about a protein). This is a more general case of problem A2, of disambiguation of gene names for different species. 

Annotation of PMID 31909712 [@pubmed:31909712]

For this article, PCP (planar cell polarity) was not found on Wikidata, just other references for the same acronym (instance of case A4). In this case, even searching for the full concept does not lead to a hit. 

- C1- The concept of interest may be completely missing. 

Of note, many scientific articles catalogued on Wikidata mention “planar cell polarity” in their titles, which might be confusing for annotation. This is a good indication that it would be useful to create the concept on Wikidata, at the very least to link to the article items via the [main subject property](https://www.wikidata.org/wiki/Q70782961).

- C2 - The concept itself is not present, but there are scientific articles with the concept in the title. 

For [N-cadherin](https://www.wikidata.org/wiki/Q21981240), the label on wikidata was “cadherin 2”, but “N-cadherin was listed as an alias. This is not a problem, but it seems to be a possible source of confusion, so it is worth mentioning it. 

- C3 - The main label on Wikidata is not the one used on the article, but the name used by the article is present as an alias. 

## Conclusion of manual annotations

The case study of manual annotations is useful to find patterns of problems in database matching. Notably, we had time only to analyse 3 of the many manual annotations made during the eLifeSprint 2020. In that way, the spreadsheet of manual annotations represent a rich resource for further exploration of the details related to annotation of biological concepts to Wikidata. 



# Community Engagement
## How can we motivate researchers to annotate content?

- _Award a stamp/reward/badge for annotations_: here, it is important to acknowledge the challenge that incentivising a behaviour is difficult if it is not yet rewarded more systematically within the research ecosystem (e.g. for example via grants). Assigning a DOI or a badge
- _Start small_: annotate smaller components of the research article such as the title or the abstract
- _Gamification_: make it fun! See an example from a previous eLife Sprint, [appstract](https://appstract.pub/). 
- _Embed annotations in the publishing process_: make use of existing “check points” in the publishing system to encourage researchers to annotate their research articles/abstracts (e.g. publishers could ask researchers to annotate their abstract when they submit their paper, similar to assigning keywords). We reached out to members of the eLife community for feedback on this 

## Citable annotations? 

We discussed further the idea of how to acknowledge the work of curators in a specific channel of the hackathon called “product clinic”, created to help projects to identify core value propositions, audience, user stories and more. Here is a partial summarized transcript of the thread we had to discuss citable annotations. Note: the conversations were adapted by T.L. for clarity and anonymity, in good faith to preserve the conversation, but respecting the privacy of people involved:  

- Team member A: 

At #team-annotate we are working on possible incentives for researchers to annotate their articles. One of the options we discussed is the possibility of giving an identifier (like. a DOI) to these kind of contributions and even make them citable. Do you know if it is possible to do so for this kind of work/contribution?

- eLife Sprint staff A: 
I don’t believe there are any restrictions that would prevent using a DOI. According to the DOI.org faq, a DOI can be assigned to “any entity — physical, digital or abstract — that you wish to identify, primarily for sharing with an interested user community or managing as intellectual property.”

A DOI in and of itself is not generally perceived as such unless linked to a higher level incentive such as, say, recognition of the content the DOI represents for the purposes of funding or career progression

- Team member A: 
After discussing it with the team members, we thought that maybe a badge/stamp system instead would be better - it may also be more "visual" than a DOI. But it's good to know we can consider DOIs too. 


- eLife Sprint staff B: 

If annotations, as a web standard, already have URIs, would mean that adding a DOI is duplicative. Nevertheless, DOIs are only really valuable as scholarly currency if some funder or tenure committee recognizes the thing the DOI is attached to. Badges seem like a good way to go. 
This seems like a good resource: [Annotation Is Now a Web Standard](https://web.hypothes.is/blog/annotation-is-now-a-web-standard/)

- eLife Sprint  staff A:
For what it’s worth, eLife funded much of the work that went into [Hypothes.is](hypothes.is) becoming a publisher-friendly option for scholarly annotation ([eLife enhances open annotation with Hypothesis to promote scientific discussion online](https://elifesciences.org/for-the-press/81d42f7d/elife-enhances-open-annotation-with-hypothesis-to-promote-scientific-discussion-online)).
As to whether that makes Hypothesis itself an actual web standard, that’s up to the definition of what a web standard is.  I think it’s fair to say that it is a solution based on principles and practices that have been approved by the W3C consortium.

Once the technical barriers to annotation on academic content were overcome however, there remain other issues that impact the usage of open annotations on academic research. They range from the lack of incentives, to reticence by researchers to publicly critique a peer’s (especially a senior peer’s) work, to fear of controversy.
Public annotations pertaining to academic papers therefore remain, at least in our experience, sadly underused.

- eLife Sprint  staff B:
The w3c has recognized the Recommendations of the Annotation Working Group. Their [architecture model](https://www.w3.org/annotation/) leads me to believe that the goal is that annotations will be anchored to URIs. 

-eLife Sprint  staff A:
You can already use the share icon on any hypothesis annotation to share it via a unique URI: https://hyp.is/-cFm4AajEeiHGMe1j9pq5g/elifesciences.org/for-the-press/81d42f7d/elife-enhances-open-annotation-with-hypothesis-to-promote-scientific-discussion-online
 

- eLife Sprint  staff A:
First thing that came to mind regarding abstract keywords is reviewer/editor matching, Daniel Ecer is the brain behind eLife’s PeerScout project, which focuses on abstract keyword extraction to help make reviewer/editor matching easier ([see this this talk](https://www.youtube.com/watch?v=htkCDiGbpt8))
So, it is perhaps in publishers’ favour to get researchers to annotate their abstracts, but what does researchers gain from annotating correctly? Moreover, what is correctly? 
 
Ultimately the reviewer/editor has the power to decide whether or not to review, so whatever they think is correct, is currently considered “correct”. In a future where we open up peer review to all researchers, it would be beneficial to annotate your abstracts to get the appropriate reviewers to review your paper.
 
Also pointing out another open-source effort to annotate figures - http://smartfigures.net/
 







# Final Remarks 

This report is a documentation of our collective efforts to hotstart the ANN project. We hope that the efforts we collectively made during the sprint will allow the project to start its journey until becoming a reality. 

The project is going to be continuously improved at github.com/lubianat/ann, where future tasks have been organized as issues. Everyone is welcome to join us and help empowering open biomedical knowledge with collaborative semantic enrichment.

# Acknowledgements

This world would not have been possible without the effort of the eLife Innovation team and the organizers of the eLife Innovation Sprint 2020, specially Emmy Tsang. All the participants of the eLife Sprint contributed to this as a community. We would like to thank Giulliano Maciocci, Micah Vandergrift and Dasapta Irawan for the discussion and insights. We would also like to thank João Vitor Cavalcante, which contributed with code to the repository, solving issues raised at the Sprint. 


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>
