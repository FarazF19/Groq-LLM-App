# 🧠 LangChain LLM Apps: From Simple Chains to Stateful Chatbots and RAG

This repository is a comprehensive, hands-on walkthrough for building production-grade LLM applications using **LangChain**, **Groq**, **OpenAI**, and **ChromaDB**. It includes everything from a basic LCEL chain to a full-fledged chatbot with memory, and culminates with a Retrieval-Augmented Generation (RAG) pipeline using vector stores and retrievers.

## 📁 Project Structure

This repo is organized into three main notebooks (or modules):

1. **`01_simple_llm_app.ipynb`** - A minimalist LangChain Expression Language (LCEL) pipeline to translate text into another language.
2. **`02_chatbots.ipynb`** - A conversational chatbot that remembers previous user inputs using `RunnableWithMessageHistory`.
3. **`03_vectorretriever.ipynb`** - Introduction to document embeddings, vector stores, retrievers, and a basic RAG implementation using LangChain components.

## 🚀 What You’ll Learn

### 🧱 Core Concepts

- How to make LLM calls via LangChain with OpenAI or Groq (Gemma/LLaMA3).
- Crafting prompts with `ChatPromptTemplate`.
- Chaining components using **LangChain Expression Language (LCEL)**.
- Parsing outputs with `StrOutputParser`.

### 💬 Stateful Chatbots

- Implementing chat history with `RunnableWithMessageHistory`.
- Managing session-based interactions.
- Trimming messages to fit LLM context windows.
- Injecting system-level instructions dynamically.

### 📚 Vector Search + RAG

- Creating semantic search pipelines with HuggingFace Embeddings.
- Using `ChromaDB` to store and retrieve relevant chunks.
- Wrapping retrievers into LCEL-compatible chains.
- Building basic **Retrieval-Augmented Generation (RAG)** systems.

## 🛠️ Tech Stack

- **LangChain** (core + community integrations)
- **Groq** (Gemma 2B / LLaMA 3 via `langchain_groq`)
- **OpenAI GPT-4 / 3.5**
- **ChromaDB** for local vector storage
- **HuggingFace Embeddings** (`all-MiniLM-L6-v2`)
- **LangSmith (optional)** – for tracing/debugging
- **Python 3.10+**

## 📦 Setup Instructions

```bash
# 1. Clone the repository
git clone https://github.com/FarazF19/Langchain-Chatbots_RAG.git
cd Langchain-Chatbots_RAG


# 2. Install dependencies
pip install -r requirements.txt

# 3. Add your API keys
touch .env
# Add your keys
OPENAI_API_KEY=your_openai_key
GROQ_API_KEY=your_groq_key
HF_TOKEN=your_huggingface_token
```

## 🧪 Example Usage

### Simple Translator Chain

```python
chain.invoke({"language": "French", "text": "Hello, how are you?"})
```

### Chatbot with Memory

```python
with_message_history.invoke(
    [HumanMessage(content="What is my name?")],
    config={"configurable": {"session_id": "chat3"}},
)
```

### Retrieval-Augmented Response

```python
rag_chain.invoke("tell me about dogs")
```

## 🧠 Key LangChain Concepts Highlighted

| Feature                      | Description                                               |
| ---------------------------- | --------------------------------------------------------- | ---------------------------------------------------- |
| `ChatPromptTemplate`         | Modular prompt templates for structured messaging         |
| `StrOutputParser`            | Clean extraction of string responses from raw LLM outputs |
| `RunnableWithMessageHistory` | Maintains chat state across multiple LLM calls            |
| `Chroma.from_documents`      | Create vector store from document chunks with embeddings  |
| `as_retriever()`             | Convert vector store into retriever for use in RAG        |
| `LCEL` (`                    | ` operator)                                               | Expressive pipeline chaining of LangChain components |

---

## 📈 Future Enhancements

- Add LangGraph and Crew AI multi-agent support
- LangSmith Tracing & Observability Integration
- RAG Fusion (hybrid search techniques)
- Frontend deployment using LangServe / FastAPI

## 🙌 Credits

- [LangChain](https://github.com/langchain-ai/langchain)
- [Chroma](https://github.com/chroma-core/chroma)
- [Groq](https://console.groq.com/)
- [OpenAI](https://openai.com/)
- [HuggingFace](https://huggingface.co/)
-

## Tutor

[Kirish Naik](https://www.udemy.com/course/complete-generative-ai-course-with-langchain-and-huggingface/learn/lecture/44637937#reviews)

## 👨‍💻 Maintainer

**Muhammad Faraz**  
_AI Full Stack Developer_  
[LinkedIn](https://linkedin.com/in/mfaraz7) •
