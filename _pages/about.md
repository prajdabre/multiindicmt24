---
layout: about
title: about
permalink: /
subtitle: <a href='#'>Affiliations</a>. Address. Contacts. Moto. Etc.

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>555 your office number</p>
    <p>123 your address street</p>
    <p>Your City, State 12345</p>

news: true # includes a list of news items
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
---

## In22 MT Task

### Introduction

In WAT 2018, we introduced the IndicMT task for the first time spanning covering 7 Indic languages. Over the years we have gradually added languages and now in WAT 2024, we are pleased to announce a multilingual Indic MT task spanning all 22 scheduled languages of India. Also, for the first time, this task will be hosted jointly along with the WMT 2024 shared tasks.

### Task Description

The task covers 22 Indic Languages (Assamese, Bengali, Gujarati, Hindi, Kannada, Malayalam, Marathi, Nepali, Oriya, Punjabi, Sindhi (Arabic script), Sinhala, Tamil, Telugu, Santali, Kashmiri (Arabic and Devanagari script), Maithili, Sanskrit and Urdu), Dogri, Bodo, Manipuri and English. We will evaluate the submissions on 44 translation directions (English-Indic and Indic-English). We will also evaluate the performance of 5 Indic-Indic pairs: Bengali-Hindi, Tamil-Telugu, Hindi-Malayalam and Sindhi-Punjabi. We encourage the use of multilingualism and transfer-learning by leveraging monolingual data, backtranslation and (potentially) LLMs, to develop high quality systems.

### Corpora

* Evaluation data: 
	* Development set: We provide [Flores-In22](https://indictrans2-public.objectstore.e2enetworks.net/flores-22_dev.zip) a subset of FLORES-200 spanning all 22 aforementioned languages.
	* Public Test set: We will evaluate on the [In22-Gen and In22-Conv](https://indictrans2-public.objectstore.e2enetworks.net/IN22_testset.zip) test sets. These are English original test sets. As we have always done, these test sets are public but we trust participants to not fine-tune on them for fairness and correctness.
	* Hidden Test set: Additionally, we will evaluate on a hidden test set which is Indic original. This spans 13 of the 22 languages and will be released a week before the end of the shared task deadline. 
* Training data:
	* We recommend using the [BPCC dataset](https://ai4bharat.iitm.ac.in/bpcc/) which spans all 22 languages. Additional details of the dataset are present in the [github repo](https://github.com/AI4Bharat/IndicTrans2). Note that one may pivot via English to obtain Indic-Indic parallel corpora.
	* We additionally recommend the use of monolingual data from [Varta](https://huggingface.co/datasets/rahular/varta), and [IndicCorp v2](https://github.com/AI4Bharat/IndicBERT/tree/main#indiccorp-v2). We are expecting the release of [Sangraha](https://github.com/AI4Bharat/IndicLLMSuite) a dataset much larger than the aofrementioned ones.
* Other data:
	* Please check with the organizers once before using any other data sources.

### Pre-trained models and training toolkits:
* Participants are welcome to leverage the following publicly available models for fine-tuning or synthetic data generation: 
	* IndicTrans2 one-to-many - [large hf](https://huggingface.co/ai4bharat/indictrans2-en-indic-1B), [distilled hf](https://huggingface.co/ai4bharat/indictrans2-en-indic-dist-200M), [large fairseq](https://indictrans2-public.objectstore.e2enetworks.net/it2_preprint_ckpts/en-indic-preprint.zip), [distilled fairseq](https://indictrans2-public.objectstore.e2enetworks.net/it2_distilled_ckpts/en-indic.zip)
	* IndicTrans2 many-to-one - [large](https://huggingface.co/ai4bharat/indictrans2-indic-en-1B), [distilled](https://huggingface.co/ai4bharat/indictrans2-indic-en-dist-200M), [large fairseq](https://indictrans2-public.objectstore.e2enetworks.net/it2_preprint_ckpts/indic-en-preprint.zip), [distilled fairseq](https://indictrans2-public.objectstore.e2enetworks.net/it2_distilled_ckpts/indic-en.zip)
	* IndicTrans2 many-to-many - [large](https://huggingface.co/ai4bharat/indictrans2-indic-indic-1B), [distilled](https://huggingface.co/ai4bharat/indictrans2-indic-indic-dist-320M), [large fairseq](https://indictrans2-public.objectstore.e2enetworks.net/it2_preprint_ckpts/indic-indic.zip), [distilled fairseq](https://indictrans2-public.objectstore.e2enetworks.net/it2_distilled_ckpts/indic-indic.zip)
	* mT5 - You may use models of any size. [hf](https://huggingface.co/docs/transformers/en/model_doc/mt5), [github](https://github.com/google-research/multilingual-t5)
	* IndicBart - [hf unified script](https://huggingface.co/ai4bharat/IndicBART), [hf separate script](https://huggingface.co/ai4bharat/IndicBARTSS), [github](https://github.com/AI4Bharat/indic-bart)
	* VartaT5 - [hf](https://huggingface.co/rahular/varta-t5)
	* BLOOM - [hf](https://huggingface.co/docs/transformers/model_doc/bloom)
	* Gemma - [hf](https://huggingface.co/docs/transformers/en/model_doc/gemma)
	* If you want to use any other LLM, please feel free but let us know in advance.
* For training you are free to use any toolkit you like but we list the following for convenience:
	* HuggingFace scripts/notebooks might be the most convenient
	* Fairseq [v1](https://github.com/facebookresearch/fairseq), [v2](https://github.com/facebookresearch/fairseq2), [lora and distillation fork](https://github.com/VarunGumma/fairseq)
	* [YANMTT](https://github.com/prajdabre/yanmtt)
	* [open-instruct](https://github.com/allenai/open-instruct/tree/main) and its [fork](https://github.com/AI4Bharat/IndicInstruct) for Indic languages if you plan to fine-tune LLMs.

### Submission details

* Constrained submission:
	* If you use the data mentioned above the your submission will be considered as constrained.
* Unconstrained submission:
	* Any other data used without confirmation from the organizers will result in unconstrained submissions.


### Timeline

* Release of training/dev data | 15th March, 2024
* Test data release | 13 July, 2024
* Run Submission and Abstract submission deadline | 28th July, 2024
* System description/workshop paper submission deadline | TBA, 2024 (follow EMNLP/WMT page)
* Notification of Acceptance | TBA, 2024 (follow EMNLP/WMT page)
* Camera-ready | TBA, 2024 (follow EMNLP/WMT page)
* Workshop Dates | follow EMNLP/WMT main page
