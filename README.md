# SentencePiece: Turning Text into Tidy Tokens for Our Translator 🧱➡️🔢

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ooCqCJgCI4_hB7PLFksnWRanZt2QUH0l#scrollTo=IVBODnmRpAOV)

Welcome to our tutorial on using **SentencePiece** to create a powerful, language-agnostic tokenizer! Learn how to transform raw English and Spanish text into organized, numerical tokens – an essential first step for building high-quality Neural Machine Translation models. 🗣️🔁

This repository contains a tutorial notebook (`.ipynb`) that guides you through the process of training your own SentencePiece tokenizer from scratch. We cover everything from preparing your text data to training the model and testing its capabilities.

## Why This Tutorial? 🤔

* **Practical Focus:** Get hands-on experience with a widely-used tokenization tool in NLP.
* **Clear Steps:** Follow a simple, step-by-step guide to train your own tokenizer for English-Spanish.
* **NMT Foundation:** Understand a crucial preprocessing step required for many translation and language generation tasks.
* **Beginner-Friendly:** Suitable for those new to tokenization or SentencePiece, with clear explanations.

## Tutorial Outline ("Our Tokenizing Adventure") 📚

1.  **Setting the Stage:**
    * Introduction to why tokenization is needed for NLP models.
    * What SentencePiece is and its key advantages (subword units, language-agnostic).
2.  **Getting Your Tools Ready:**
    * Installing the `sentencepiece` library.
    * Downloading and preparing the English-Spanish dataset (`spa-eng.zip`).
3.  **Training Your Custom Tokenizer:**
    * Preparing a combined text file from English and Spanish sentences for SentencePiece training.
    * Using `SentencePieceTrainer` to train your model, understanding key parameters like `vocab_size`, `model_type` (Unigram vs. BPE), `character_coverage`, and special token IDs (`<pad>`, `<s>`, `</s>`, `<unk>`).
4.  **Testing Your New Tokenizer:**
    * Loading your trained SentencePiece model (`.model` file).
    * Encoding text into subword pieces and numerical IDs.
    * Decoding IDs back into human-readable text to verify.
    * Understanding the role of the `.vocab` file.

## Key SentencePiece Concepts/Functions Covered ✨

* Subword Tokenization (Unigram & BPE)
* `sentencepiece.SentencePieceTrainer.train()`: Training a new tokenizer.
    * `input`: Specifying training data.
    * `model_prefix`: Naming your output model files.
    * `vocab_size`: Setting the desired vocabulary size.
    * `character_coverage`: Ensuring representation of characters.
    * `model_type`: Choosing between `unigram` or `bpe`.
    * Defining `pad_id`, `bos_id`, `eos_id`, `unk_id`.
* `sentencepiece.SentencePieceProcessor()`: Loading a trained model.
    * `load()`: (Implicitly called or can use `model_file=` in constructor).
    * `encode_as_pieces()`: Converting text to subword strings.
    * `encode_as_ids()`: Converting text to numerical IDs.
    * `decode_pieces()`: Converting subword strings back to text.
    * `decode_ids()`: Converting numerical IDs back to text.
    * Accessing special token IDs (`bos_id()`, `eos_id()`, etc.) and vocabulary size (`get_piece_size()`).
* Understanding the `.model` and `.vocab` output files.
* Text Normalization (default NFKC, `nmt_nfkc_cf`).

Dive into the notebook and start turning your text into tidy tokens!
