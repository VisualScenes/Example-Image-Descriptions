# Understanding Visual Scenes

This repository provides supplementary material for our work on representations for the semantics of image scenes by explicitly encoding the objects detected in them and their spatial relations. We represent image content via well-known tree representations, namely constituents and dependencies. 

The representations are amenable to standard NLP tools developed for tree-based structures. We use syntax-based SMT and tree kernel methods in order to build models for image description generation and image-based retrieval. 

## Supplementary material for the image description generation models
### Examples
of generated descriptions by our tree-based SMT models and comparison models can be found in 
 [examples_html.pdf] (https://github.com/VisualScenes/Example-Image-Descriptions/blob/master/examples_html.pdf) 
 
 All example images are part of the MS COCO dataset [1]. 
  
  
### Parameter settings used for training the SMT models
We used moses' [2] default settings for syntax-based / phrase-based MT if not stated otherwise. 

The core features of our syntax-based models are a language model, the translation model, word and phrase penalties, and unknown word penalty. 
- We trained a 6-gram language model with modified Kneser-Ney smoothing using KenLM [3].
- For the creation of the rule table, we set MaxNonTerm to 10 for rule extraction (the maximum number of non-terminals on the 
right hand side of a rule), and used Good-Turing smoothing for rule scoring. 
- We tuned the parameters for translation quality as measured by IBM BLEU [4] using Minimum Error Rate Training [5].

---
[1] Xinlei Chen, Hao Fang, Tsung-Yi Lin, Ramakrishna Vedantam, Saurabh Gupta, Piotr Dollar, C. Lawrence Zitnick. 2015. Microsoft COCO Captions: Data Collection and Evaluation Server. arXiv preprint arXiv:1504.00325. [MSCOCO] (http://mscoco.org/)

[2] Philipp Koehn, Hieu Hoang, Alexandra Birch, Chris Callison-Burch, Marcello Federico, Nicola Bertoldi, Brooke Cowan, Wade Shen, Christine Moran, Richard Zens, Chris Dyer, Ond?rej Bojar, Alexandra Constantin, and Evan Herbst. 2007. Moses: Open Source Toolkit for Statistical Machine Translation. ACL Interactive Poster and Demonstration Sessions, Prague, Czech Republic.

[3] Kenneth Heafield, Ivan Pouzyrevsky, Jonathan H. Clark, and Philipp Koehn. 2013. ACL, Sofia, Bulgaria.

[4] Kishore Papineni, Salim Roukos, Todd Ward, and Wei-Jing Zhu. 2002. BLEU: A Method for Automatic Evaluation of Machine Translation. ACL, Philadelphia, Pennsylvania. 

[5] Franz Josef Och. 2003. Minimum Error Rate Training in Statistical Machine Translation. ACL, Sapporo, Japan. 





