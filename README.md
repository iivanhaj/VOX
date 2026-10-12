# Vox: Multilingual Collaboration Model

**Vox** is a collaboration tool designed to automate meeting summarization and enable efficient information retrieval. Built by team Vox for the Samsung PRISM Gen AI Hackathon (2024), it brings speech, summarization, translation and LLM-based retrieval together in one meeting assistant.

## Key Features

- **Wake Word Activation**  
  Vox listens on the microphone and starts when it hears its wake word, using the **MIT/ast-finetuned-speech-commands-v2** audio classifier.

- **Live Transcription with Speaker Labels**  
  Speech is transcribed with **OpenAI Whisper**, and **pyannote** speaker diarization (combined through **speechbox**) labels who said what, with timestamps.

- **Automated Meeting Summarization**  
  The labelled transcript is summarized into meeting minutes with the **ankitkhowal/minutes-of-meeting** model, helping teams focus on key insights for better decision-making.

- **Multilingual Translation**  
  Transcripts are translated with **facebook/nllb-200-distilled-600M** (English to German in the notebook; NLLB-200 covers 200 languages).

- **Task Scheduling**  
  A spoken request such as "set up a Meet reminder at 10:00" is turned into a Google Calendar event structure (JSON) by **Falcon-7B-instruct**.

- **Interactive Chat Interface**  
  Powered by **meta-llama/Llama-2-7b-chat-hf**, the chat interface answers questions such as "What tasks are left?" using the team's **Notion** task data.

- **Optimized Vector Storage**  
  With **Llama Index** and **sentence-transformers/all-mpnet-base-v2** embeddings, Vox indexes the Notion data for fast and accurate retrieval.

## Tech Stack

- **Hugging Face Transformers**
- **Whisper**, **pyannote.audio**, **speechbox**
- **NLLB-200**
- **Llama-2-7b-chat**, **Falcon-7B-instruct**
- **Llama Index**
- **Langchain**
- **Notion**

## How to Run

Everything lives in one notebook, `Vox_3&5_Gen_AI_Hackathon.ipynb`.

1. Open it in Google Colab using the badge at the top of the notebook.
2. Use a GPU runtime (Llama-2-7b is loaded in 8-bit).
3. Add a Hugging Face token as a Colab secret named `HF_TOKEN`. Your account needs access to `meta-llama/Llama-2-7b-chat-hf` and `pyannote/speaker-diarization`.
4. For the task chat, put your Notion export in Google Drive at `MyDrive/Notion_DB`.
5. Run the cells in order. The first cell installs the dependencies.

## Architecture

### Voice Module
Wake word detection (AST speech-commands), then live transcription with Whisper.

### Transcription and Summarization Module
Whisper and pyannote diarization produce a speaker-labelled transcript, which is summarized into minutes of the meeting.

### Translation Module
NLLB-200 (distilled 600M) translates the transcript into another language.

### Scheduling Module
Falcon-7B-instruct turns a natural-language request into a Google Calendar event structure.

### Chat Module
The chat interface, powered by meta-llama/Llama-2-7b-chat-hf, answers questions over the team's Notion data.

### Data Storage and Retrieval
Llama Index with all-mpnet-base-v2 embeddings is used for embedding-based data retrieval, ensuring fast and accurate results.

## Future Enhancements

- Multilingual support for the chat interface.
- Integration with platforms like Slack and Microsoft Teams.
- Advanced natural language understanding for more personalized insights.

## License

This project is licensed under the MIT License.
