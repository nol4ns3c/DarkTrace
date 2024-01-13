# DarkTrace
From DarkNet forums to structured data format — Machine learning implementation of Threat Intelligence

    This is an open-source project. The aim of the project is to collect and annotate unstructured data that can be found in DarkNet forums. For contributions, please contact me via LinkedIn.

What is CTI?

Cyber threat intelligence refers to the information and insights gathered from various sources to understand and identify potential threats and risks in the digital world. It involves collecting, analyzing, and disseminating information about emerging and existing cyber threats, such as malware, phishing, ransomware, and other types of cyberattacks.

Cyber threat intelligence can be obtained from a variety of sources, including open source intelligence, dark web monitoring, social media analysis, and information sharing among industry peers and government agencies. It requires a range of technical and analytical skills to collect, process, and analyze the data effectively.
What is structured format?

Structured format in cyber threat intelligence refers to the use of a standardized method for organizing and presenting information about cybersecurity threats. This approach allows for easy sharing and comparison of threat data across different organizations and systems, and helps analysts identify patterns and trends that can inform their response.

The security community has become proficient in using indicators of compromise (IoC) feeds for threat intelligence. Automated feeds have simplified the task of extracting and sharing IoCs. However, IoCs like IP addresses, domain names, and file hashes are in the lowest levels of the threat intelligence pyramid; they are relatively easy to access and consume, but they’re also easy for attackers to change to evade detection. IoCs are not enough.

Tactics, techniques, and procedures (TTPs) can enable organizations to extract valuable insights like patterns of attack on an enterprise or industry vertical, or trends of attacker techniques in the overall ecosystem. However, TTPs are at the highest level of the threat intelligence pyramid; this information often comes in the form of unstructured texts like blogs, research papers, and incident response (IR) reports, DarkNet forums (Which we will focus on), and the process of gathering and sharing these high-level indicators has remained largely manual.

Automating the processing of unstructured text for threat intelligence can benefit threat analysts.

Trained on documentation of known threats, our system will take unstructured text as input and extract threat actors, attack techniques, malware families, and relationships.
What is machine learning?

Machine learning is a subfield of artificial intelligence (AI) that involves the development of algorithms and statistical models that enable computers to learn from data without being explicitly programmed.

In a typical machine learning process, a computer system is trained on a dataset of input/output examples, called training data. The system uses statistical techniques to identify patterns in the data and then uses these patterns to make predictions or decisions on new, unseen data.
What is text annotation?

Annotating texts in machine learning refers to the process of manually labeling or marking up text data with specific attributes or metadata, such as named entities, parts of speech, sentiment, or topic categories. This process is also known as text annotation or text tagging.

The purpose of annotating text is to create a labeled dataset that can be used to train and evaluate machine learning models. By providing labeled data, the machine learning algorithms can learn patterns and relationships in the text data and make predictions on new, unlabeled data.

For example, in natural language processing (NLP), text annotation might involve identifying and labeling named entities such as person names, locations, and organizations, or tagging words with their respective part-of-speech labels such as nouns, verbs, adjectives, and adverbs. This labeled data can then be used to train machine learning models that can automatically identify named entities or classify the parts of speech of words in new, unlabeled text data.
What is OIE?

Open Information Extraction (OpenIE) is a technique in natural language processing and machine learning that aims to extract structured and meaningful information from unstructured text. Unlike traditional information extraction methods, which rely on pre-defined templates or schemas, OpenIE does not require any prior knowledge or assumptions about the structure of the information to be extracted.

In OpenIE, the goal is to extract a set of triples (subject, relation, object) from a sentence or a document. For example, from the sentence “Steve Jobs co-founded Apple Inc.”, an OpenIE system would extract the triple (Steve Jobs, co-founded, Apple Inc.). The system is able to identify the subject (“Steve Jobs”), the relation (“co-founded”), and the object (“Apple Inc.”) without any prior knowledge of what these entities are.

OpenIE is typically based on unsupervised machine learning techniques, such as clustering and pattern recognition, and is often combined with techniques from natural language processing, such as part-of-speech tagging and dependency parsing. It can be used for a variety of applications, including knowledge base construction, question answering, and text summarization.
What is NER?

Named Entity Recognition (NER) is a subtask of information extraction in natural language processing that aims to identify and classify named entities in text into predefined categories, such as persons, organizations, locations, dates, and other types of named entities.

The goal of NER is to identify and extract specific pieces of information from text and convert them into structured data that can be easily processed and analyzed by machines. For example, in the sentence “John works at Google in New York”, a NER system would identify “John” as a person, “Google” as an organization, and “New York” as a location.

NER is typically based on supervised machine learning techniques, where a model is trained on annotated data that consists of text and corresponding labeled named entities. The model learns to identify patterns and features in the text that are indicative of a named entity of a particular type.
How to extract useful information with ML?

The pipeline is composed of three main modules; a neural OIE system to extract relation triples from unstructured APT reports and DarkNet forums’ data, a cybersecurity NER model that identifies and classifies each word according to a predefined set of labels.

For Dataset, for now we will use MalwareDB dataset. MalwareDB is an annotated dataset based around Malware Attribute Enumeration and Characterization (MAEC) vocabulary that primarily outlines malware characteristics gathered from 39 APT reports.

After defining our train, test and validation set we can train our model.

This model is not sufficient for extracting valuable information from DarkNet forums because of Dataset. For this we need to annotate new Dataset for DarkNet. This exhausting task need to be manually labeled by human.

Here is example sentence we want to convert to structured format:

And here is our structured format :

This is done by the help of GPT-3 model. We can get more exact result by enhancing our dataset.

