pyrouge
=======

A Python interface to the ROUGE package.

Right now, only the basic functionality is in place. You can score one summary at a time with respect to multiple reference summaries. Summaries are represented as lists of sentences, where each sentence is a list of words.
Down the road, the plan is to reimplement (parts of) ROUGE in pure Python.
The motivation is that the ROUGE package, while standard in evaluation of extractive summaries,
can be a challenge to obtain and install, and also does not fit well in a Python workflow.

Contributions and suggestions are very welcome.

## Usage example

```
from pyrouge import Rouge155
from pprint import pprint

ref_texts = {'A': ["Poor nations pressurise developed countries into granting trade subsidies .".split()],
             'B': ["Developed countries should be pressurized .".split(), "Business exemptions to poor nations .".split()],
             'C': ["World 's poor decide to urge developed nations for business concessions .".split()]}
summary_text = ["Poor nations demand trade subsidies from developed nations .".split()]


rouge = Rouge155(n_words=100, average="sentence")
score = rouge.score_summary(summary_text, ref_texts)
pprint(score)
```

The output will be this:

```
{'rouge_1_f_score': 0.45833,
 'rouge_1_f_score_cb': 0.45833,
 'rouge_1_f_score_ce': 0.45833,
 'rouge_1_precision': 0.45833,
 'rouge_1_precision_cb': 0.45833,
 'rouge_1_precision_ce': 0.45833,
 'rouge_1_recall': 0.36667,
 'rouge_1_recall_cb': 0.36667,
 'rouge_1_recall_ce': 0.36667,
 'rouge_2_f_score': 0.19048,
 'rouge_2_f_score_cb': 0.19048,
 'rouge_2_f_score_ce': 0.19048,
 'rouge_2_precision': 0.19048,
 'rouge_2_precision_cb': 0.19048,
 'rouge_2_precision_ce': 0.19048,
 'rouge_2_recall': 0.14815,
 'rouge_2_recall_cb': 0.14815,
 'rouge_2_recall_ce': 0.14815,
 'rouge_3_f_score': 0.0,
 'rouge_3_f_score_cb': 0.0,
 'rouge_3_f_score_ce': 0.0,
 'rouge_3_precision': 0.0,
 'rouge_3_precision_cb': 0.0,
 'rouge_3_precision_ce': 0.0,
 'rouge_3_recall': 0.0,
 'rouge_3_recall_cb': 0.0,
 'rouge_3_recall_ce': 0.0,
 'rouge_4_f_score': 0.0,
 'rouge_4_f_score_cb': 0.0,
 'rouge_4_f_score_ce': 0.0,
 'rouge_4_precision': 0.0,
 'rouge_4_precision_cb': 0.0,
 'rouge_4_precision_ce': 0.0,
 'rouge_4_recall': 0.0,
 'rouge_4_recall_cb': 0.0,
 'rouge_4_recall_ce': 0.0,
 'rouge_su4_f_score': 0.15625,
 'rouge_su4_f_score_cb': 0.15625,
 'rouge_su4_f_score_ce': 0.15625,
 'rouge_su4_precision': 0.15625,
 'rouge_su4_precision_cb': 0.15625,
 'rouge_su4_precision_ce': 0.15625,
 'rouge_su4_recall': 0.11364,
 'rouge_su4_recall_cb': 0.11364,
 'rouge_su4_recall_ce': 0.11364}
```
## Run tests

The unit tests can be run be issuing ``nosetests´´ from the root directory of the package.
