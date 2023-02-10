# tmdm
Text mining data model with integration of various formats, annotation libraries, bells 
and whistles.

#Summary 
This library is for Text Mining and Data Mining. It contains various tools and algorithms for pre-processing and analyzing text data, such as text pre-processing, feature extraction, and classification.

You can use this library to extract useful information from text data, such as sentiment analysis, topic modeling, and so on. The repository contains a number of example scripts and tutorials that demonstrate how to use the library.



## Setup
### Using pip
```bash
pip install git+https://github.com/schlevik/tmdm
```
### From source
```bash
git clone https://github.com/schlevik/tmdm
cd tmdm
pip install -r requirements.txt
pip install . --editable
```

## Example
```python
from tmdm import tmdm_pipeline, add_coref
from tmdm.allennlp.coref import get_coref_provider
nlp = tmdm_pipeline()
add_coref(nlp, provider=get_coref_provider("https://storage.googleapis.com/allennlp-public-models/coref-spanbert-large-2020.02.27.tar.gz"))
doc = nlp("I like cakes. They taste nice.")
assert len(doc._.corefs) == 2
assert doc[2:3]._.get_coref().coreferent(doc[4])
```

Proper documentation is in preparation.
