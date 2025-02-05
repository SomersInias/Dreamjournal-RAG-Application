# Dreamjournal QA RAG Chatbot App

This project is a test and practice showcase project aimed at building an RAG (Retrieval-Augmented Generation) system using ChatGPT, LangChain, and Streamlit. The primary goal is to develop a Dreamjournal QA chatbot that can efficiently process and analyze dream-related queries while providing real-time responses with source references.

## Project Overview

### Features
- **PDF Document Upload and Indexing**: Users can upload dream journals in PDF format, which are indexed for efficient querying.
- **RAG-Based Query Analysis and Response**: Implements a retrieval-augmented generation system to enhance the accuracy and relevance of chatbot responses.
- **Real-Time Result Streaming**: Ensures responses are generated and displayed in real time.
- **Source Document Reference**: The chatbot provides citations from the indexed dream journals to enhance credibility.
- **Word Frequency Analysis Using SpaCy**: Analyzes word occurrences to identify common themes in dream journals.
- **Full Dream Retrieval**: The chatbot can return entire dream entries based on user queries.
- **Counting-Based Query Handling**: Supports queries related to counting occurrences, such as "How many dreams are about... ?"

## **How It Works**

This application provides a user-friendly interface using **Streamlit** to interact with your uploaded dream journal PDFs. It allows you to analyze and query your dream content using AI-powered retrieval-augmented generation (RAG). Here's how it functions:

1. **Upload Your Dream Journal**
   - User upload one or multiple PDF files containing dream journal entries.
   - The application reads and processes the uploaded documents and transfroms it into a **Vector database** using chroma

2. **Processing and Retrieval Setup**
   - The dreamjournal is split into smaller chunks, ensuring that queries return relevant results.
   - A **retriever** is created using an embedding-based vector database to efficiently search for dream-related content.

3. **Ask a Question**
   - Users enter questions related to their dream journal.
   - The **retriever** determines the nature of the question and selects the appropriate function to process it.

4. **Question Classification**
   - The system categorizes the question into one of the following types:
     - **Count Question**: Counts how many dreams contain a specific topic.
     - **Full Dream Question**: Retrieves the complete text of a specific dream.
     - **Analysis Question**: Performs text analysis and visualization on the entire dream journal.
     - **QA Question**: Extracts detailed information based on dream content.

5. **Processing the Query**
   - Based on the classification, the system executes the relevant function:
     - **Count Dreams**: Uses NLP to analyze dream journal entries and count how many of them are related to a specified topic by checking for variations of the topic and handling both positive and negated queries. 
     - **Retrieve Full Dream**: Retrieves the complete dream entry from the database and returns it to the user.
     - **Analyze Dreams**:  Analyzes the dream journal using Spacy to generate word frequency plots, identifying and visualizing the most commonly used words.
     - **QA (Question-Answering)**: Extracts and generates answers based on the user's questions and the dream journal, utilizing a RAG to provide detailed responses about specific dream content.

6. **Display Results**
   - The application displays results in a clear, user-friendly format within the Streamlit app, providing relevant data along with the corresponding page numbers for easy reference. 
  
This workflow ensures an intuitive and effective way to interact with dream journal data, leveraging AI-driven retrieval and analysis.

## Usage
- Run the [Dreamjournal_QA_app](https://github.com/SomersInias/Dreamjournal-RAG-Application/blob/main/Dreamjournal_QA_app.ipynb) in google colab
- Provide API keys for Open AI and ngrok
- Upload a dream journal in PDF format. (Note: The code is currently optimized for a PDF document where each page contains a single dream, with each dream ending with the "/end" marker.)
- Ask questions about your dreams.
