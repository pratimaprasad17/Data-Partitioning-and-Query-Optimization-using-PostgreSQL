# Reranking: Yet Another Performance Boost

## Introduction
This project enhances **information retrieval** by implementing **reranking techniques** to improve the ordering of retrieved documents. The primary goal is to refine traditional search methods (**BM25 & TF-IDF**) using **neural models**, particularly **CrossEncoder**, to improve retrieval precision.

### Problem Statement
Traditional ranking models like **BM25** often retrieve results based on keyword matching but lack deep contextual understanding. This project introduces a **reranking mechanism** that improves search relevance by applying **neural ranking models** to reorder search results based on their semantic relevance to a query.

## Technologies Used
- **Python 3.x**: Core programming language for implementation.
- **Hugging Face Transformers**: Used for **CrossEncoder-based neural reranking**.
- **Elasticsearch**: Indexes and retrieves documents efficiently.
- **BM25 Algorithm**: Initial ranking mechanism for baseline performance.
- **TREC-COVID Dataset**: Used for evaluation of retrieval effectiveness.
- **Pandas & NumPy**: Data processing and analysis.
- **Matplotlib & Seaborn**: Visualization of performance comparisons.

## Project Structure
```
|-- src/
    |-- main/
        |-- Group4-Project2-Code.ipynb  # Jupyter Notebook for implementation
|-- data/
    |-- trec_covid/         # TREC-COVID dataset (Download from https://ir.nist.gov/trec-covid/)
|-- models/
    |-- cross_encoder_model/ # Pretrained reranking model (Download from https://huggingface.co/cross-encoder/ms-marco-MiniLM-L-6-v2)
|-- results/
    |-- evaluation_metrics/ # Performance comparison data
|-- README.md
```

## Installation & Setup
### Prerequisites
Before running the project, ensure you have the following dependencies installed:
```sh
pip install transformers pandas numpy elasticsearch matplotlib seaborn
```

### Setting Up Elasticsearch
Start an Elasticsearch instance:
```sh
docker run -d -p 9200:9200 -e "discovery.type=single-node" elasticsearch:7.10.1
```

### Running the Project
1. **Open the Jupyter Notebook**:
   ```sh
   jupyter notebook Group4-Project2-Code.ipynb
   ```
2. **Run each cell** to execute the reranking pipeline.

## Evaluation & Results
### Metrics Used:
- **nDCG@10**: Measures ranking quality.
- **Judge Rate**: Percentage of judged documents in top results.

| Method | nDCG@10 | Judge Rate |
|--------|--------|------------|
| BM25 | 68.80% | 92.4% |
| Reranking | **75.76%** | **97.4%** |

### Observations:
- **Reranking consistently outperformed BM25**, showing a **10% improvement** in ranking quality.
- **Neural models better capture contextual relevance** compared to keyword-based retrieval.
- **Judge rate improvement** confirms better alignment with human relevance assessments.

## Future Improvements
- **Integrating hybrid models** that combine BM25 and neural approaches for efficiency.
- **Reducing computational overhead** by optimizing the reranking pipeline.
- **Exploring reinforcement learning** to dynamically adjust ranking scores.

## Conclusion
This project successfully demonstrates how **neural reranking** can enhance traditional retrieval systems, **boosting relevance and accuracy** in search results. By integrating **BM25 with CrossEncoders**, we achieve a **highly efficient and effective reranking mechanism** for real-world applications.

## Contribution
Feel free to fork this repository and contribute improvements! Open issues or pull requests if you encounter problems.

## License
MIT License

---
If you have any issues running the project, please raise an issue on the repository.

