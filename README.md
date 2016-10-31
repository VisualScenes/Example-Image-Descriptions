# Understanding Visual Scenes

This repository provides supplementary material for our work on representations for the semantics of image scenes by explicitly encoding the objects detected in them and their spatial relations. We represent image content via well-known tree representations, namely constituents and dependencies. 

The representations are amenable to standard NLP tools developed for tree-based structures. We use syntax-based SMT and tree kernel methods in order to build models for image description generation and image-based retrieval. 

## Supplementary material for the image description generation models
### 1. Examples of System Outputs
<html>
<body>
<p>
Below are example outputs of our tree-based SMT models (Dependency and Constituency) and comparison models. 
We used the <a href="http://mscoco.org/" target="_blank">Microsoft COCO Captions dataset</a> [1] as training and testing data. 
The ranks denote relative ranks (1 is best) and were obtained from human annotators using Amazon&#39;s MT. 
</p>
<table>
  <tr>
    <td>MS COCO 2015 Test Images</td>
    <th colspan="2">
		<img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000143004.jpg">
		</th>
    <th colspan="2">
		<img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000560036.jpg">
		</th>
    <th colspan="2">
		<img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000196058.jpg">
		</th>
  </tr>
  <tr>
	  <th></th>
    <th>Rank</th>
    <th>Output</th>
    <th>Rank</th>
    <th>Output</th>
    <th>Rank</th>
    <th>Output</th>
  </tr>
  <tr>
                <th>Template</th>
                <td>5</td>
                <td>a couch has a couch</td>
                <td>4</td>
                <td>a dog has a frisbee</td>
                <td>5</td>
                <td>a zebra is eating a zebra</td>
            </tr>
            <tr>
                <th>Tuples</th>
                <td>4</td>
                <td>the room has a couch</td>
                <td>3</td>
                <td>a dog holding a frisbee</td>
                <td>3</td>
                <td>two zebras eating grass</td>
            </tr>
            <tr>
                <th>Dependency</th>
                <td>1</td>
                <td>a dog sitting on a couch</td>
                <td>3</td>
                <td>a dog holding a frisbee</td>
                <td>2</td>
                <td>zebras standing in a field</td>
            </tr>
            <tr>
                <th>Constituency</th>
                <td>2</td>
                <td>dog laying on a couch</td>
                <td>2</td>
                <td>a dog catching a frisbee</td>
                <td>1</td>
                <td>zebras are standing in a field</td>
            </tr>
            <tr>
                <th>Human</th>
                <td>3</td>
                <td>a dog is looking at something</td>
                <td>2</td>
                <td>a dog catching a frisbee in its mouth</td>
                <td>4</td>
                <td>a herd of zebra standing in a safari</td>
            </tr>
	    <tr>
<!-- Second block -->
  <tr>
	<td>MS COCO 2015 Test Images</td>
	<th colspan="2">
	<img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000172042.jpg">
	</th>
	<th colspan="2">
	<img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000185312.jpg">
	</th>
	<th colspan="2">
	<img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000096247.jpg">
	</th>    
  </tr>
  <tr>
	  <th></th>
    <th>Rank</th>
    <th>Output</th>
    <th>Rank</th>
    <th>Output</th>
    <th>Rank</th>
    <th>Output</th>
  </tr>
  <tr>
    <th>Template</th>
    <td>2</td>
    <td>a person is above a bed</td>
    <td>2</td>
    <td>an airplane is near a car</td>
    <td>3</td>
    <td>a tv is near a cat</td>
  </tr>
  <tr>
    <th>Tuples</th>
    <td>5</td>
    <td>a man sitting in bed</td>
    <td>5</td>
    <td>a airplane sitting on a street</td>
    <td>4</td>
    <td>a tv sitting on top</td>
  </tr>
  <tr>
    <th>Dependency</th>
    <td>3</td>
    <td>a man sitting on a bed</td>
    <td>3</td>
    <td>a airplane parked next to a car</td>
    <td>2</td>
    <td>a cat sitting next to a tv</td>
  </tr>
  <tr>
    <th>Constituency</th>
    <td>4</td>
    <td>a girl is sitting on a bed</td>
    <td>4</td>
    <td>a airplane parked next to a car</td>
    <td>5</td>
    <td>a cat that is looking at a television</td>
  </tr>
  <tr>
    <th>Human</th>
    <td>1</td>
    <td>a man bounces on the bed</td>
    <td>1</td>
    <td>a large plane with a red tail</td>
    <td>1</td>
    <td>a cat is showing its back to a tv screen</td>
  </tr>
<!-- Third example block -->
  <tr>
    <td>MS COCO 2015 Test Images</td>
    <th colspan="2">
    <img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000078343.jpg">
    </th>
    <th colspan="2">
    <img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000566624.jpg">
    </th>
    <th colspan="2">
    <img width="150px" height="180px" src="https://raw.githubusercontent.com/VisualScenes/Example-Image-Descriptions/master/images/COCO_test2015_000000406163.jpg">
    </th>    
  </tr>
  <tr>
    <th></th>
    <th>Rank</th>
    <th>Output</th>
    <th>Rank</th>
    <th>Output</th>
    <th>Rank</th>
    <th>Output</th>
  </tr>
  <tr>
    <th>Template</th>
    <td>2</td>
    <td>a refrigerator is below a microwave</td>
    <td>1</td>
    <td>a tv is near a laptop</td>
    <td>2</td>
    <td>a tie is near a pizza</td>
  </tr>
  <tr>
    <th>Tuples</th>
    <td>4</td>
    <td>a refrigerator sits in a kitchen</td>
    <td>5</td>
    <td>a tv sitting on top</td>
    <td>3</td>
    <td>a man holding a pizza</td>
  </tr>
  <tr>
    <th>Dependency</th>
    <td>3</td>
    <td>a refrigerator sits in a kitchen</td>
    <td>3</td>
    <td>a tv sitting on a desk</td>
    <td>4</td>
    <td>a man eating pizza</td>
  </tr>
  <tr>
    <th>Constituency</th>
    <td>5</td>
    <td>a kitchen counter</td>
    <td>2</td>
    <td>a laptop on a desk</td>
    <td>4</td>
    <td>a man eating pizza</td>
  </tr>
  <tr>
    <th>Human</th>
    <td>1</td>
    <td>a brown refrigerator sits up against a wall</td>
    <td>4</td>
    <td>a compilation of pictures creating a room</td>
    <td>1</td>
    <td>a calzone or oval pizza with cheese, ham and bacon</td>
  </tr>
</table>
</body>
</html>
  
  
### 2. Parameter settings used for training the SMT models
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





