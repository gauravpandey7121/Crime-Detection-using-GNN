 Crime Hotspot Detection using Graph Neural Networks (GNN)

A graph-based deep learning project that identifies high-crime districts by learning how nearby and similar regions influence each other. The model uses Graph Attention Networks (GAT) to detect crime hotspots and provide interpretable insights.

 🚀 Project Overview
- Districts are modeled as nodes and connected using spatial and crime similarity.
- Multi-year NCRB district-level crime data is cleaned, merged, and aggregated.
- A k-Nearest Neighbor (k-NN) graph is constructed to map relationships between districts.
- A 2-layer GAT model is trained for binary hotspot classification.
- The system delivers strong accuracy and explainable predictions for crime analytics.

 🧠 Key Features
- Learns crime influence patterns between districts instead of analyzing them in isolation.
- Uses attention scores to highlight the most impactful neighboring regions.
- Designed to scale well with multi-year spatial data.
- Evaluated using accuracy, precision, recall, F1-score, ROC-AUC, and confusion matrix.

 📊 Dataset
- Source: National Crime Records Bureau (NCRB), India
- Contains yearly district crime counts like murder, rape, robbery, theft, and other IPC/State crimes.
- Preprocessing includes:
  - Standardizing district names
  - Handling missing or incorrect values
  - Aggregating data at the district level
  - Labeling hotspots using the 75th percentile crime threshold

 🏗 Graph Construction
1. Numerical crime feature vectors are created for each district  
2. Similarity is measured using cosine or Euclidean distance  
3. Top K similar districts are linked with edges  
4. The graph is converted into PyTorch Geometric edge_index format  

 🤖 Model Architecture
| Layer | Model Type | Heads |
|------|-----------|------|
| 1 | GAT | Multi-Head |
| 2 | GAT | Single-Head |

- Activation: ELU
- Loss Function: Cross-Entropy
- Optimizer: Adam (LR = 0.005)

 ✅ Results Achieved
- Accuracy: 97%  
- ROC-AUC: 0.99+  
- Predictions include attention weights to improve interpretability  

 🛠 Tech Stack
- Python
- PyTorch Geometric
- Pandas, NumPy
- Matplotlib, NetworkX
- Scikit-Learn (Polynomial trend and graph similarity)

 📌 Future Improvements
- Add temporal graph learning to detect emerging hotspots earlier.
- Introduce multi-relational graphs using socio-economic or demographic data.
- Deploy the model into dashboards for easier use by analysts or researchers.

 👨‍💻 Author  
Gaurav Pandey  
GitHub: Linked above  


This project was built as part of academic research and is a step toward applying graph deep learning in real-world policing and public safety analytics.
