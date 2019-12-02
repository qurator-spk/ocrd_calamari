# ocrd_calamari

> Recognize text using [Calamari OCR](https://github.com/Calamari-OCR/calamari).

[![image](https://circleci.com/gh/OCR-D/ocrd_calamari.svg?style=svg)](https://circleci.com/gh/OCR-D/ocrd_calamari)
[![image](https://img.shields.io/pypi/v/ocrd_calamari.svg)](https://pypi.org/project/ocrd_calamari/)
[![image](https://codecov.io/gh/OCR-D/ocrd_calamari/branch/master/graph/badge.svg)](https://codecov.io/gh/OCR-D/ocrd_calamari)

## Introduction

This offers a OCR-D compliant workspace processor for some of the functionality of Calamari OCR.

This processor only operates on the text line level and so needs a line segmentation (and by extension a binarized 
image) as its input.

## Installation

```
pip install ocrd_calamari
```

## Install models

```
wget https://github.com/Calamari-OCR/calamari_models/archive/master.zip
unzip master.zip
```

## Example Usage

~~~
ocrd-calamari-recognize -p test-parameters.json -m mets.xml -I OCR-D-SEG-LINE -O OCR-D-OCR-CALAMARI
~~~

With `test-parameters.json`:
~~~
{
    "checkpoint": "/path/to/some/trained/models/*.ckpt.json"
}
~~~

TODO
----

* Support Calamari's "extended prediction data" output
* Currently, the processor only supports a prediction using confidence voting of multiple models. While this is
  superior, it makes sense to support single model prediction, too.
