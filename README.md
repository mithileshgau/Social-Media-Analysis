# TopicBubbler: Visual Analytics for Hierarchical Social Media Exploration

TopicBubbler is an interactive visual analytics system designed for the cross-level, fine-grained exploration of large-scale social media datasets. By leveraging hierarchical topic modeling and advanced NLP pipelines, it enables users to navigate complex conversational landscapes and extract actionable insights through intuitive, multi-coordinated views.

## 🚀 Key Features

*   **Hierarchical Structure Exploration**: A radial tree visualization representing a "Dual-LDA" hierarchy, allowing users to drill down from broad categories to granular sub-topics.
*   **Temporal Trend Analysis**: Interactive timelines that visualize the evolution of topics and keywords over time.
*   **Keyword Salience & Correlation**: Integrated bubble plots and correlation matrices to identify significant terms and their semantic relationships.
*   **Narrative Construction**: An event evolution view that allows users to select keywords and construct narrative timelines of social media discourse.
*   **Document Contextualization**: Direct access to original social media documents for qualitative validation of quantitative patterns.

---

## 🧠 Technical Architecture

TopicBubbler employs a robust backend designed for efficient text processing and analytical depth.

### 1. NLP Preprocessing Pipeline
The system transforms raw social media data through a rigorous multi-stage pipeline:
*   **Sanitization**: Removal of hyperlinks, specialized symbols, user tags, and hashtags using optimized regular expressions.
*   **Tokenization & Stop-word Removal**: Text is broken into unigrams, with common conversational noise filtered out using NLTK's standardized corpora.
*   **Stemming**: Implementation of the Porter Stemmer to reduce words to their base forms (e.g., "shopping" and "shopped" to "shop").
*   **Dictionary Filtering**: Verification against a validated dictionary to ensure keyword relevance and reduce noise.

### 2. Hierarchical Topic Modeling (Dual-LDA)
At the core of TopicBubbler is a **Dual-LDA** (Latent Dirichlet Allocation) approach:
*   **Level 1 (Global Topics)**: Documents are classified into 10 high-level themes (e.g., Global Economy, Health Measures).
*   **Level 2 (Granular Sub-topics)**: Each global topic is further partitioned into 3 distinct sub-topics, facilitating a hierarchical "parent-child" relationship for deeper exploration.

### 3. Keyword Salience with TextRank
To identify the most "essential" words within a topic, the system implements a **TextRank** algorithm. By constructing word-co-occurrence graphs and applying the PageRank algorithm, TopicBubbler calculates a salience score for every keyword, ensuring that visualization components highlight terms with the highest informational density.

---

## 🛠️ Technology Stack

*   **Frontend**: HTML5, CSS3, JavaScript (D3.js for visual analytics).
*   **Backend**: FastAPI (Python) for high-performance asynchronous data processing.
*   **Analytics**: Gensim (LDA modeling), NLTK (Text processing), NetworkX (Graph-based keyword ranking).
*   **Data**: Pandas & PyArrow (Efficient parquet-to-CSV processing).

## 📊 Visualization Components

### Hierarchical Structure View
Displays the visual hierarchy of topics in a radial tree format.
![Hierarchical Structure View](images/hierarchical_view.png)

### Fine-grained Exploration View
Facilitates correlation analysis through interactive bubble plots.
![Fine-grained Exploration View](images/fine_grained_view.png)

### Temporal Evolution View
Provides insights into temporal trends across different hierarchical levels.
![Temporal View](images/temporal_view.png)

---

## 📈 Dataset
The project currently utilizes a dataset of **44,955 coronavirus-related tweets** sourced from Hugging Face, spanning July 2020 to December 2020, processed for optimal visual exploration.

