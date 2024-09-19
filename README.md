# Vox: Multilingual Collaboration Model

**Vox** is a powerful collaboration tool designed to automate meeting summarization and enable efficient information retrieval. Developed for the Samsung PRISM Hackathon, Vox enhances workplace communication and productivity by integrating cutting-edge AI models.

## Key Features

- **Automated Meeting Summarization**  
  Vox uses the **llama-distilled-600** model to generate concise summaries of meetings, helping teams focus on key insights for better decision-making.

- **Interactive Chat Interface**  
  Powered by **meta-llama/Llama-2-7b-chat-hf**, the chat interface allows seamless collaboration and interaction while retrieving information from **NotionDB**.

- **Optimized Vector Storage**  
  With **Llama Index**, Vox optimizes vector storage and embeddings, ensuring fast and accurate data retrieval from **NotionDB** for an enhanced user experience.

## Tech Stack

- **Langchain**
- **Hugging Face**
- **Llama Index**
- **Transformers**
- **NotionDB**

## Installation

### Prerequisites

- Python 3.8+
- Notion API credentials
- Hugging Face API key
- Access to the Llama-2-7b-chat-hf model

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/vox.git
   cd vox

2. Install the required dependencies:

  ```bash
  pip install -r requirements.txt

3. Set up your environment variables for Hugging Face and Notion API keys:

  ```bash
  export HUGGINGFACE_API_KEY='your-api-key'
  export NOTION_API_KEY='your-api-key'

4. Run the application:

  ```bash
  python app.py

### Usage
Automated Meeting Summarization
Provide meeting transcripts, and Vox will generate concise summaries using the llama-distilled-600 model.

### Interactive Chat Interface
Collaborate with team members through the chat interface, which allows querying of NotionDB for relevant information.

### Efficient Data Retrieval
Vox uses Llama Index to optimize vector storage, enabling fast and accurate retrieval of meeting notes, documents, or other embedded data in NotionDB.

### Architecture
Summarization Module
Leverages llama-distilled-600 for summarizing long meeting transcripts.

### Chat Module
The chat interface, powered by meta-llama/Llama-2-7b-chat-hf, interacts with NotionDB to fetch relevant data during conversations.

### Data Storage and Retrieval
Llama Index is used for embedding-based data retrieval, ensuring fast and accurate results.

### Future Enhancements
Multilingual support for the summarization and chat interface.
Integration with platforms like Slack and Microsoft Teams.
Advanced natural language understanding for more personalized insights.

### License
This project is licensed under the MIT License.
