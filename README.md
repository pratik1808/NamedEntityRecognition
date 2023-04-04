# NamedEntityRecognition
Named Entity Recognition using Hugging Face Transformer Library

Named entity recognition is the task of extracting information from the sequence of words and sentences and classifying them into predefined categories such as person names, organizations, locations, medical codes, time expressions, quantities, monetary values, percentages, etc.
It is a subtask of information extraction. It can be used in various applications ranging from Classifying content for news providers, Powering Content Recommendations to Entity Detection in Research Papers.

### Dataset Description
The dataset consists of speeches given at the United Nations General Assembly from 1993-2016 scraped from the website and then parsed. There are a total of 70 labeled documents consisting of transcribed speeches which 50 in the training and 20 in the test data. More than 50,000 tokens in the test data were manually tagged for Named Entity Recognition (O - Not a Named Entity; I-PER - Person; I-ORG - Organization; I-LOC - Location; I-MISC - Other Named Entity)

### Model in use: DistilBERT (distilbert-base-uncased)
DistilBERT is a transformers model, smaller and faster than BERT, which was pretrained on the same corpus in a self-supervised fashion.

Using the huggingface model directly to perform named entity recognition does not yeild good results as it is trained on a broader dataset. To make it give accurate results on our dataset, I have finetuned it to suit the UN dataset. Below is the training and test accuracies and results.

<img width="1374" alt="image" src="https://user-images.githubusercontent.com/101216624/229669646-769ea809-a374-4f89-9dbf-603edb5c612f.png">

<img width="1374" alt="image" src="https://user-images.githubusercontent.com/101216624/229669711-c6d2123c-7972-43a0-8a14-28562deb30a3.png">

### Conclusion
Fine-tuned the Hugging Face NER model successfully with UN transcripts data to perform NER on the generated transcripts.
This model can be used in assisting UN speech transcript analysis in order to track the trends of which entities are most discussed during which time of the year to generate insights
Fine tuning can be done using other datasets as well such as sensitive information labels which can be used to censor confidential documents.
