# RAG-Powered AI Teaching Assistant

An intelligent, context-aware teaching assistant that uses **Retrieval-Augmented Generation (RAG)** to answer student questions based on specific course video content. This system processes raw video lectures, indexes them into a vector database, and provides timestamped answers using a local Large Language Model (LLM).

## Key Features
- **Video-to-Knowledge Pipeline:** Automatically extracts audio, transcribes text, and generates semantic embeddings.
- **Retrieval-Augmented Generation (RAG):** Uses **Cosine Similarity** to find the most relevant lecture segments for any query.
- **Local AI Inference:** Powered by **Ollama (Llama 3.2)** and **OpenAI Whisper** for 100% private, local processing.
- **Timestamped Accuracy:** Directly guides students to the exact video and second where a topic is discussed.

---

## System Architecture
The project follows a modular **ETL (Extract, Transform, Load)** and **RAG** workflow:



1.  **Extraction:** `FFmpeg` extracts high-quality audio from course videos.
2.  **Transcription:** `OpenAI Whisper` converts speech to JSON chunks with precise start/end timestamps.
3.  **Embedding:** Text chunks are converted into 1024-dimensional vectors using the `bge-m3` model via Ollama.
4.  **Vector Store:** Data is stored in a `joblib` serialized dataframe for fast similarity search.
5.  **Query Engine:** When a user asks a question, the system retrieves the Top-K most relevant chunks and passes them as context to the LLM.

---

## 📁 Repository Structure
```text
AI-Assistant-RAG/
├── data/               # Project data (Ignored by Git)
│   ├── videos/         # Raw .mp4 lecture files
│   ├── audios/         # Extracted .mp3 files
│   └── jsons/          # Timestamped transcriptions
├── models/             
│   └── embeddings.joblib # Generated vector database
├── src/                # Source code
│   ├── 01_extraction.py    # Video to Audio processing
│   ├── 02_transcription.py # Whisper AI implementation
│   ├── 03_embedding.py     # Vectorization & Joblib export
│   └── chatbot.py          # RAG query logic & LLM integration
├── .gitignore          # Filters out heavy media files
├── README.md           # Project documentation
└── requirements.txt    # Python dependencies
```
# How to use this RAG AI Teaching assistant on your own data
## Step 1 - Collect your videos
Move all your video files to the videos folder

## Step 2 - Convert to mp3
Convert all the video files to mp3 by ruunning video_to_mp3

## Step 3 - Convert mp3 to json 
Convert all the mp3 files to json by ruunning mp3_to_json

## Step 4 - Convert the json files to Vectors
Use the file preprocess_json to convert the json files to a dataframe with Embeddings and save it as a joblib pickle

## Step 5 - Prompt generation and feeding to LLM

Read the joblib file and load it into the memory. Then create a relevant prompt as per the user query and feed it to the LLM


