---
language: turkish
license: mit
---

# 🤗 + 📚 dbmdz Turkish ELECTRA model

In this repository the MDZ Digital Library team (dbmdz) at the Bavarian State
Library open sources a cased ELECTRA base model for Turkish 🎉

# Turkish ELECTRA model

We release a base ELEC**TR**A model for Turkish, that was trained on the same data as *BERTurk*.

> ELECTRA is a new method for self-supervised language representation learning. It can be used to
> pre-train transformer networks using relatively little compute. ELECTRA models are trained to
> distinguish "real" input tokens vs "fake" input tokens generated by another neural network, similar to
> the discriminator of a GAN.

More details about ELECTRA can be found in the [ICLR paper](https://openreview.net/forum?id=r1xMH1BtvB)
or in the [official ELECTRA repository](https://github.com/google-research/electra) on GitHub.

## Stats

The current version of the model is trained on a filtered and sentence
segmented version of the Turkish [OSCAR corpus](https://traces1.inria.fr/oscar/),
a recent Wikipedia dump, various [OPUS corpora](http://opus.nlpl.eu/) and a
special corpus provided by [Kemal Oflazer](http://www.andrew.cmu.edu/user/ko/).

The final training corpus has a size of 35GB and 44,04,976,662 tokens.

Thanks to Google's TensorFlow Research Cloud (TFRC) we could train a cased model
on a TPU v3-8 for 1M steps.

## Model weights

[Transformers](https://github.com/huggingface/transformers)
compatible weights for both PyTorch and TensorFlow are available.

| Model                                            | Downloads
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------
| `dbmdz/electra-base-turkish-cased-discriminator` | [`config.json`](https://cdn.huggingface.co/dbmdz/electra-base-turkish-cased-discriminator/config.json) • [`pytorch_model.bin`](https://cdn.huggingface.co/dbmdz/electra-base-turkish-cased-discriminator/pytorch_model.bin) • [`vocab.txt`](https://cdn.huggingface.co/dbmdz/electra-base-turkish-cased-discriminator/vocab.txt)

## Usage

With Transformers >= 2.8 our ELECTRA base cased model can be loaded like:

```python
from transformers import AutoModelWithLMHead, AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("dbmdz/electra-base-turkish-cased-discriminator")
model = AutoModelWithLMHead.from_pretrained("dbmdz/electra-base-turkish-cased-discriminator")
```

## Results

For results on PoS tagging or NER tasks, please refer to
[this repository](https://github.com/stefan-it/turkish-bert/electra).

# Huggingface model hub

All models are available on the [Huggingface model hub](https://huggingface.co/dbmdz).

# Contact (Bugs, Feedback, Contribution and more)

For questions about our ELECTRA models just open an issue
[here](https://github.com/dbmdz/berts/issues/new) 🤗

# Acknowledgments

Thanks to [Kemal Oflazer](http://www.andrew.cmu.edu/user/ko/) for providing us
additional large corpora for Turkish. Many thanks to Reyyan Yeniterzi for providing
us the Turkish NER dataset for evaluation.

Research supported with Cloud TPUs from Google's TensorFlow Research Cloud (TFRC).
Thanks for providing access to the TFRC ❤️

Thanks to the generous support from the [Hugging Face](https://huggingface.co/) team,
it is possible to download both cased and uncased models from their S3 storage 🤗