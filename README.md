**Mental Health Chatbot**

**Motivation Behind This Project**

Mental health has become an essential aspect of well-being, with an increasing number of people suffering from mental disorders like depression and anxiety. According to the National Mental Health Survey of 2017, one in seven individuals in India suffered from mental health issues. However, access to mental health services remains limited, especially for the economically weaker sections.

This project aims to bridge this gap by making mental health support more accessible through a chatbot. The chatbot can assist individuals by providing preliminary guidance, information, and mental health resources. Additionally, it can complement clinicians by offering support beyond clinical hours, making mental health services more effective and efficient.

**Classification of Chatbots**

Chatbots can be categorized based on different attributes. My research focuses on the design approaches used to build chatbots, namely:

1. **Rule-Based Chatbots**

A rule-based chatbot follows a set of predefined rules and uses pattern matching techniques to select appropriate responses. These chatbots do not generate new responses; instead, they choose from a predefined set of answers based on user input.

2.**Retrieval-Based Chatbots**

Retrieval-based chatbots utilize Machine Learning models to select the best response from a set of predefined answers. Similar to rule-based chatbots, they do not generate new responses but rely on heuristic evaluation for response selection.

3. **Generative-Based Chatbots**

Unlike rule-based and retrieval-based models, generative chatbots create new responses from scratch. They use NLP techniques and sequence-to-sequence models (Seq2Seq) to generate human-like responses. These chatbots do not rely on predefined responses and can dynamically generate meaningful replies based on user inputs.

Overview of the Models Trained

The dataset used for training the chatbot was derived from publicly available mental health FAQs. It contains frequently asked questions related to mental health, along with corresponding answers.

For retrieval-based chatbots, the dataset was manually converted from CSV to JSON format. To keep training efficient, a subset of the dataset was used.

This repository contains three different chatbot models:

1. **Rule-Based Chatbot**

Used TF-IDF (Term Frequency-Inverse Document Frequency) for text vectorization.

NLTK tokenizer was applied for preprocessing.

Cosine similarity was used to compare input queries with predefined responses and select the best match.

2. **Retrieval-Based Chatbot**

Several Machine Learning and Deep Learning models were tested, including:

Basic Recurrent Network

Memory-Based LSTM

Context-Aware Bi-LSTM

Adaptive GRU Model

Pattern-Matching CNN

JSON format was used for data storage to support hierarchical data representation.

CNN-based models performed the best, using a three-layer architecture (CNN + Embedding Layer + Fully Connected Layer).

3.**Generative-Based Chatbot**

NLP techniques were applied to enable the chatbot to mimic human conversations.

Used a Seq2Seq (sequence-to-sequence) encoder-decoder model trained on a CSV dataset.

The LSTM-based model was implemented for response generation.

The model predicts words dynamically, ensuring context-based responses.

**Why JSON for Retrieval-Based Models and CSV for Generative Models?**

During this project, I encountered a challenge in selecting the appropriate data format. Here’s a comparison:

**JSON (Used for Retrieval-Based Chatbots)**

Supports hierarchical data storage, making it easier to map user queries to predefined responses.

Provides context-aware data organization by associating queries with response tags.

Efficiently structures responses for faster lookup and retrieval.

**CSV (Used for Generative-Based Chatbots)**

Contains only two columns: input text and output text, making it simpler for training sequence-based models.

Easier to update by adding or removing rows compared to hierarchical JSON files.

Does not require predefined response tags, as the chatbot learns from input-output text pairs.

**Future Goals**

The current generative chatbot model uses an **LSTM-based encoder-decoder architecture**, which has some limitations in capturing long-term dependencies in responses. To improve performance, I aim to:

Implement Attention Mechanism to enhance the chatbot’s ability to retain relevant context in conversations.

Explore Transformer-based architectures such as **GPT or BERT** to improve the chatbot’s response generation.

Expand the dataset to cover a broader range of mental health topics, improving the chatbot's response accuracy and usefulness.

How to Use This Repository

1. Clone the repository:
_git clone https://github.com/aranjan3/Mental_Health_Chatbot.git_
2. Navigate to the project directory:
_cd Mental_Health_Chatbot_
3. Install dependencies:
pip install -r requirements.txt
