---
layout: about
title: about
permalink: /
subtitle:   The MultiIndicMT 2024 shared task page. This will be a part of WAT 2024, hosted alongside WMT 2024.
---

### Introduction

In WAT 2018, we introduced the IndicMT task for the first time spanning covering 7 Indic languages. Over the years we have gradually added languages and now in WAT 2024, we are pleased to announce a multilingual Indic MT task spanning all **22 scheduled languages** of India belonging to **4 language families** and written in **12 scripts**. The languages exhibit both genetic as well as contact relatedness ([Kunchukuttan et al. 2020](https://arxiv.org/abs/2003.08925)). Some of these languages are extremely low-resource. This diversity makes this language group ideal for studies in multilingual learning, language relatedness and low-resource MT. For the first time, this task will be hosted jointly along with the WMT 2024 shared tasks.

### Task Description

The task covers English and 22 Indic Languages, namely, Assamese, Bengali, Bodo, Dogri, Konkani, Gujarati, Hindi, Kannada, Kashmiri (Arabic script), Maithili, Malayalam, Marathi, Manipuri (Meitei script), Nepali, Oriya, Punjabi, Sanskrit, Santali, Sindhi (Devanagari script), Tamil, Telugu, Urdu. We will evaluate the submissions on 44 translation directions (English-Indic and Indic-English). We will also evaluate the performance of 5 Indic-Indic pairs: Bengali-Hindi, Tamil-Telugu, Hindi-Malayalam and Sindhi-Punjabi. We encourage the use of multilingualism and transfer-learning by leveraging monolingual data, backtranslation and (potentially) LLMs, to develop high quality systems.

### Corpora

* Evaluation data: 
	* Development set: We provide [FLORES-22 Indic dev set](https://indictrans2-public.objectstore.e2enetworks.net/flores-22_dev.zip) an extended version of FLORES-200 dev set spanning all 22 aforementioned languages.
	* Public Test set: We will evaluate on the [IN22-Gen and IN22-Conv](https://indictrans2-public.objectstore.e2enetworks.net/IN22_testset.zip) test sets. These are English original test sets. As we have always done, these test sets are public but we trust participants to not fine-tune on them for fairness and correctness.
	* Hidden Test set: Additionally, we will evaluate on a hidden test set which is Indic original. This spans 13 of the 22 languages and will be released a week before the end of the shared task deadline. 
* Training data:
	* We recommend using the [BPCC dataset](https://ai4bharat.iitm.ac.in/bpcc/) ([Gala et al., 2023](https://openreview.net/forum?id=vfT4YuzAYA))which spans all 22 languages. Additional details of the dataset are present in the [github repo](https://github.com/AI4Bharat/IndicTrans2). Note that one may pivot via English to obtain Indic-Indic parallel corpora.
	* We additionally recommend the use of monolingual data from [Varta](https://huggingface.co/datasets/rahular/varta), [IndicCorp v2](https://github.com/AI4Bharat/IndicBERT/tree/main#indiccorp-v2) and [Sangraha](https://github.com/AI4Bharat/IndicLLMSuite) corpora.
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

* If you wish to participate then please fill this [form](https://docs.google.com/forms/d/e/1FAIpQLScT_PxHGAoLD5huUJtrKpglut4G-0cY0qa7xJE5_2V-g32gbQ/viewform?usp=sf_link) so that we may send you the hidden test sets when it is time.
* There are two types of submissions: Constrained and Unconstrained.
	* Constrained submission: If you use the data and models mentioned above the your submission will be considered as constrained.
	* Unconstrained submission: Any other data or models are used without confirmation from the organizers will result in unconstrained submissions.
* Please submit your system translations to prajdabre@gmail.com and anoop.kunchukuttan@gmail.com.
	* Participants may submit up to 2 systems, one Primary (ranked) and one Contrastive (unranked, optional).
* When submitting results please submit a single **zip** file with the following name: (Teamname)-(Constrained/Unconstrained)-(Primary/Contrastive).zip.
	* For example if your team name is Garuda and you are making an Unconstrained, Primary submission then the zip file will be: Garuda-Unconstrained-Primary.zip.
	* Under the zip file there should be files for each direction in the format: (srccode)-(tgtcode).txt.
	* The codes should be as per the codes listed [here](https://github.com/AI4Bharat/IndicTrans2?tab=readme-ov-file#indictrans2). Thus if you are submitting Hindi to English and Punjabi to Sindhi (Devanagari script) translations then the file names will be: hin_Deva-eng_Latn.txt and pan_Guru-snd_Deva.txt.

### Evaluation

* We will use the SacreBLEU for evaluation and primarily rely on chrF while BLEU will be the secondary metric.
	* We recommend following this [script](https://github.com/AI4Bharat/IndicTrans2/blob/main/compute_metrics.sh) for evaluation, since we will do the same.
* We will also perform human evaluation of a few language pairs which will be decided soon.
* We will provide rankings per translation direction for both automatic and human evaluation.

### Timeline

* Task and training/dev data announcement - 20th April, 2024
* Test data release - 13 July, 2024
* Run Submission and Abstract submission deadline - 28th July, 2024
* System description/workshop paper submission deadline - TBA, 2024 (follow EMNLP/WMT page)
* Notification of Acceptance - TBA, 2024 (follow EMNLP/WMT page)
* Camera-ready - TBA, 2024 (follow EMNLP/WMT page)
* Workshop Dates - follow EMNLP/WMT main page

### Contact

* Raj Dabre: prajdabre@gmail.com
* Anoop Kunchukuttan: anoop.kunchukuttan@gmail.com
