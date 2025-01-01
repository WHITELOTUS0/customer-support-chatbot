# customer-support-chatbot

## Overview

This project demonstrates how to build a customer support question-answering chatbot using GPT-3 and Deep Lake. The chatbot retrieves relevant information from a set of articles and generates responses to user queries. The workflow involves scraping content from online articles, splitting them into chunks, computing their embeddings, and storing them in Deep Lake. The chatbot then uses these embeddings to find the most relevant chunks and generates answers using GPT-3.

## Instructions

1. **Set up Environment Variables:**
   - Set the `OPENAI_API_KEY` and `ACTIVELOOP_TOKEN` environment variables with your API keys and tokens.

2. **Install Required Libraries:**
   - Install the necessary Python libraries using pip:
     ```bash
     %pip install unstructured selenium
     %pip install langchain==0.0.208 deeplake==3.9.27 openai==0.27.8 tiktoken
     ```

3. **Load and Split Documents:**
   - Use the SeleniumURLLoader to load documents from the provided URLs.
   - Split the documents into smaller chunks using the `CharacterTextSplitter`.

4. **Compute Embeddings and Store in Deep Lake:**
   - Compute the embeddings using `OpenAIEmbeddings`.
   - Store the embeddings in a Deep Lake vector store on the cloud.

5. **Retrieve Relevant Chunks:**
   - Use the `similarity_search` method of the Deep Lake vector store to retrieve the most similar chunks to a given query.

6. **Generate Responses:**
   - Craft a prompt for GPT-3 using the retrieved chunks and the user's query.
   - Use the GPT-3 model with a temperature of 0 to generate a response.

Refer to the `customer_support_chatbot.ipynb` notebook for detailed code and examples.