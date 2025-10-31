# GRID-IDS
This project focuses on developing a machine learning system for intrusion detection in smart grids using an embedding model combined with a prototype network. The architecture is designed to first implement and evaluate the standalone model for attack classification and then extend it to a federated learning framework to enable privacy-preserving, distributed training across multiple clients.

The core goals are:
- To build an interpretable and efficient classification model using embedding and prototype networks.
- To leverage federated learning for collaborative model training without compromising data privacy.
- To handle heterogeneous and distributed data typical in smart grid environments.

## Dataset
The project uses the Industrial Control System (ICS) Cyber Attack Datasets curated by Uttam Adhikari, Shengyi Pan, Tommy Morris, and collaborators at Oak Ridge National Laboratories (ORNL). These datasets provide measurements related to electric transmission system normal, disturbance, control, and cyber attack behaviors, including synchrophasor data and control panel logs.

Access the datasets here:  
[ICS Cyber Attack Datasets - Tommy Morris](https://sites.google.com/a/uah.edu/tommy-morris-uah/ics-data-sets)

## Architecture
- **Standalone Model:**  
  A classical machine learning pipeline with an embedding model transforming input data into feature space, followed by a prototype network that computes class prototypes for classification based on similarity metrics.

- **Federated Learning Extension:**  
  Multiple clients locally train the embedding + prototype network on their private datasets and share prototype updates with a central server. The server aggregates these prototypes to form global representations and redistributes the aggregated knowledge. This approach ensures data privacy while enhancing detection capabilities across distributed nodes.

- The server optionally integrates with a knowledge database and a large language model (LLM) via API for advanced knowledge synchronization and reasoning support.

![Architecture Diagram](src/data/images/grid_ids.svg)

