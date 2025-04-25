# 🌐 Web Intelligence Workflow (n8n)

This n8n workflow automatically gathers information from the internet to answer a user's query using powerful LLMs and content extraction. It integrates multiple services to perform intelligent web search, content parsing, and summarization.

## 🧠 Workflow Overview

1. **User Input**  
   A question or topic is provided as input via the `Edit Fields` node.

2. **Search the Web**  
   The query is passed to the Serper API to get Google search results (top 7 links).

3. **Scrape Web Content**  
   The URLs are passed to Scrappey API to fetch raw HTML content.

4. **Extract Main Article Text**  
   Langchain Information Extractor removes irrelevant HTML elements (ads, navigation, etc.) and retrieves only the main article content.

5. **Chunk and Merge Content**  
   The extracted content is:
   - Chunked into smaller parts for LLM processing
   - Passed through a Groq LLM to summarize or clean each chunk
   - Merged back into a single text block

6. **Final Answer Generation**  
   The merged content is sent to an LLM Agent (Groq) which answers the original question using the processed information.

---

## 🧩 Technologies Used

- **n8n**: Workflow automation
- **Serper API**: Google search engine alternative
- **Scrappey API**: Web scraping
- **Langchain**: Content extraction & summarization
- **Groq (LLaMA-3)**: High-speed LLM for reasoning and generation

---

## 🚀 How to Use

1. Import this workflow into your n8n instance.
2. Add valid credentials:
   - Groq API (both Free and Paid keys)
   - Serper API key
   - Scrappey API key
3. Modify the input at `Edit Fields` node (`chatInput`) to change the search query.
4. Execute the workflow.

---

## 📝 Example

If you ask:
> "What are the latest advancements in quantum computing?"

The workflow will:
- Search for relevant articles
- Extract their content
- Clean and merge the data
- Answer the question using an LLM based on the articles

---

## ⚙️ Credits

- Developed by Pranav Dhobi
- APIs: [Serper](https://serper.dev), [Scrappey](https://publisher.scrappey.com), [Groq](https://console.groq.com/)


---

