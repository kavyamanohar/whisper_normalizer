# whisper_normalizer

<!-- WARNING: THIS FILE WAS AUTOGENERATED! DO NOT EDIT! -->

## Installation of package

``` sh
pip install whisper_normalizer
```

or from github repository

``` sh
pip install git+https://github.com/kurianbenoy/whisper_normalizer.git
```

## Why should we normalize/standardize text?

- In ASR systems it’s important to normalize the text to reduce error in
  metrics like WER, CER etc.
- Text normalization/standardization is process of converting texts in
  different styles into a standardized form, which is a best-effort
  attempt to penalize only when a word error is caused by actually
  mistranscribing a word, and not by formatting or punctuation
  differences.(from [Whisper
  paper](https://cdn.openai.com/papers/whisper.pdf))

## Why use this python package?

This package is a python implementation of the text
standardisation/normalization approach which is being used in OpenAI
whisper text normalizer. If you want to use just text normalization
alone, it’s better to use this instead reimplementing the same thing.
OpenAI approach of text normalization is very helpful and is being used
as normalization step when evaluating competitive models like
[AssemblyAI Conformer-1
model](https://www.assemblyai.com/blog/conformer-1/).

## Models evaluated using Whisper normalization

- Massively Multilingual Speech (MMS) models by Meta
- Conformer 1 by AssemblyAI
- Conformer 2 by AssemblyAI

## How to use

OpenAI open source approach of text normalization/standardization is
mentioned in detail Appendix Section C pp.21 the paper [Robust Speech
Recognition via Large-Scale Weak
Supervision](https://cdn.openai.com/papers/whisper.pdf).

You can use the same thing in this package as follows:

``` python
from whisper_normalizer.basic import BasicTextNormalizer

normalizer = BasicTextNormalizer()
normalizer("I'm a little teapot, short and stout. Tip me over and pour me out!")
```

    'i m a little teapot short and stout tip me over and pour me out '

``` python
from whisper_normalizer.english import EnglishTextNormalizer

english_normalizer = EnglishTextNormalizer()
english_normalizer("I'm a little teapot, short and stout. Tip me over and pour me out!")
```

    'i am a little teapot short and stout tip me over and pour me out'
