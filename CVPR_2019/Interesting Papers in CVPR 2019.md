# Interesting Papers in CVPR 2019

## Indexing
- [Visual Question Answering (15)](#Visual-Question-Answering)
- [Visual Grounding and Embodied (10)](#Visual-Grounding-and-Embodied)
- [Visual Reasoning (6)](#Visual-Reasoning)
- [Image Captioning (6)](#Image-Captioning)
- [Visual Dialog (5)](#Visual-Dialog)
- [Visual Semantic Embedding (4)](#Visual-Semantic-Embedding)
- [Visual Question Generation (2)](#Visual-Question-Generation)
- [Attention (1)](#Attention)
- [Open Domain (7)](#Open-Domain)
- [Distillation (5)](#Distillation)
- [Interpretability (3)](#Interpretability)
- [3D Vision (3)](#3D-Vision)
- [Reinforcement Learning (1)](#Reinforcement-Learning)
- [References](#References)
---
## Visual Question Answering
### Actively Seeking and Learning From Live Data
#### Abstract
*Intuition*
- **Searching** for the information required at **test time**
- Resulting method **dynamically utilizes data** from an **external source**, such as a large set of questions/answers or images/captions.

*Contributions*
- We propose a new approach to VQA in which the model is trained to **retrieve and utilize information from an external source**, to support its reasoning and answering process.

- We propose an implementation of this approach based on a simple neural network and a **gradient-based adaptation** which is based on the **MAML algorithm**

- Illustration

<img src="https://github.com/qiuyue1993/Notes/blob/master/CVPR_2019/Images/Paper-Summarization_Actively-Seeking-and-Learning-from-Live-DATA_Illustration.png" width="600" hegiht="400" align=center/>

#### Approach
*Steps*
- Learn a set of base weights for a simple VQA model
- **Adapted to a given question** with the information specifically retrieved for this question

*Overall*
- Central idea: learn a VQA model that can **subsequently adapt to each particular given question**, using additional support data relevant to the question

- Overall Framework

<img src="https://github.com/qiuyue1993/Notes/blob/master/CVPR_2019/Images/Paper-Summarization_Actively-Seeking-and-Learning-from-Live-DATA_Overall-Framework.png" width="600" hegiht="400" align=center/>

*Underlying VQA model*
- **Standard VQA model** 
- Encodes the question as a bag-of-words, taking the average of learned word embeddings
- Single-headed, question-guided attention over image locations
- **Hadamard product** to combine the two modalities

*Gradient-based adaptation*
- Based on **MAML**
- For adaptation using support data of the same form as for task of interest
- Use a first-order approximation of the gradient
- **The support set must be simulated to best mimic the conditions in which the model will be evaluated**

*Using non-VQA data as support*
- Challenge: produce beneficial updates the the weights **without access to a loss** on the target VQA model.
- Evaluate the **extracted captions features** with **image-caption hadamard product features**.
- Gradient is projected by **a learned projection**

*Retrieval of relevant support data*
- The **selection of a relevant subset is crucial**
- A **static relevance function** to produce a scalar that reflects the pertinence of a support instance with the input
- A series simple functions (Uniform sampling, common words comparison, Top-5 answers sentence, similarity of image features)

#### Experiments

*Results*
- SOTA on the VQA-CP v2
- Robust to out-of-distribution test data
- Capabilities for leveraging non-VQA data (image captions)


#### Comments
- What is multi-headed attention?
- What is the relationship between main and adaptation loss
- Learned gradient projection is new for me
- How to use the other sources may be a good future work

### MUREL Multimodal Relational Reasoning for Visual Question Answering
#### Abstract

- Illustration

<img src="https://github.com/qiuyue1993/Notes/blob/master/CVPR_2019/Images/Paper-Summarization_MUREL_Illustration.png" width="600" hegiht="400" align=center/>

*Intuition*
- Current **multimodal attention is insufficient** to model complex reasoning features for VQA

*MuRel cell*
- An atomic reasoning primitive representing **interactions between question and image regions** and modeling region relations with **pairwise combinations**
- Can be used **iteratively**

#### Approach

- MuRel Cell

<img src="https://github.com/qiuyue1993/Notes/blob/master/CVPR_2019/Images/Paper-Summarization_MUREL_MuRel-cell.png" width="600" hegiht="400" align=center/>


- Overall Framework

<img src="https://github.com/qiuyue1993/Notes/blob/master/CVPR_2019/Images/Paper-Summarization_MUREL_Overall-Framework.png" width="600" hegiht="400" align=center/>

#### Experiments
*Datasets*
- VQA 2.0
- VQA-CP v2
- TDIUC

*Results*
- Better than bottom-up, mutan, mlb on VQA 2.0
- Pythia and Counter have higher accuracy than MuRel

#### Comments
- The result on VQA-CP v2 is 39%, which is not high
- The attention visualization is not trustful
- **Attention map** in VQA is still not as that trustful

### OK-VQA A Visual Question Answering Benchmark Requiring External Knowledge


### Deep Modular Co-Attention Networks for Visual Question Answering


### Visual Question Answering as Reading Comprehension

### Dynamic Fusion With Intra- and Inter-Modality Attention Flow for Visual Question Answering


### Cycle-Consistency for Robust Visual Question Answering


### GQA: A New Dataset for Real-World Visual Reasoning and Compositional Question Answering


### From Recognition to Cognition: Visual Commonsense Reasoning

### Towards VQA Models That Can Read


### Visual Query Answering by Entity-Attribute Graph Matching and Reasoning


### Transfer Learning via Unsupervised Task Discovery for Visual Question Answering


### Social-IQ: A Question Answering Benchmark for Artificial Social Intelligence


### Answer Them All! Toward Universal Visual Question Answering Models


### Multi-Task Learning of Hierarchical Vision-Language Representation

---
## Visual Grounding and Embodied
### Neural Sequential Phrase Grounding (SeqGROUND)

### Multi-Target Embodied Question Answering

### Reinforced Cross-Modal Matching and Self-Supervised Imitation Learning for Vision-Language Navigation

### Embodied Question Answering in Photorealistic Environments With Point Cloud Perception

### Two Body Problem: Collaborative Visual Task Completion

### The Regretful Agent: Heuristic-Aided Navigation Through Progress Estimation


### Tactical Rewind: Self-Correction via Backtracking in Vision-And-Language Navigation

### Learning to Learn How to Learn: Self-Adaptive Visual Navigation Using Meta-Learning

### Vision-Based Navigation With Language-Based Assistance via Imitation Learning With Indirect Intervention

### TOUCHDOWN: Natural Language Navigation and Spatial Reasoning in Visual Street Environments


---
## Visual Reasoning
### Its Not About the Journey Its About the Destination Following Soft Paths Under Question Guidance for Visual Reasoning


### Scene Graph Generation With External Knowledge and Image Reconstruction


### CLEVR-Ref+: Diagnosing Visual Reasoning With Referring Expressions


### RAVEN: A Dataset for Relational and Analogical Visual REasoNing


### Learning to Compose Dynamic Tree Structures for Visual Contexts

### Video Relationship Reasoning Using Gated Spatio-Temporal Energy Graph

---
## Image Captioning
### Unsupervised Image Captioning

### Context and Attribute Grounded Dense Captioning

### Dense Relational Captioning: Triple-Stream Networks for Relationship-Based Captioning

### Auto-Encoding Scene Graphs for Image Captioning

### Good News, Everyone! Context Driven Entity-Aware Captioning for News Images


### Pointing Novel Objects in Image Captioning

---
## Visual Dialog
### Reasoning Visual Dialogs With Structural and Partial Observations

### Recursive Visual Attention in Visual Dialog


### Audio Visual Scene-Aware Dialog

### Image-Question-Answer Synergistic Network for Visual Dialog

### A Simple Baseline for Audio-Visual Scene-Aware Dialog

---
## Visual Semantic Embedding
### Polysemous Visual-Semantic Embedding for Cross-Modal Retrieval

### Unified Visual-Semantic Embeddings: Bridging Vision and Language With Structured Meaning Representations

### Image Generation From Layout

### Multi-Level Multimodal Common Semantic Space for Image-Phrase Grounding

---
## Visual Question Generation
### Information Maximizing Visual Question Generation


### What's to Know? Uncertainty as a Guide to Asking Goal-Oriented Questions



---
## Attention
### Factor Graph Attention


---
## Open Domain
### Unsupervised Open Domain Recognition by Semantic Discrepancy Minimization


### Large-Scale Long-Tailed Recognition in an Open World

### Universal Domain Adaptation

### Zero-Shot Task Transfer

### Learning Words by Drawing Images


### Neural Task Graphs: Generalizing to Unseen Tasks From a Single Video Demonstration


### Informative Object Annotations: Tell Me Something I Don't Know


---
## Distillation
### Student Becoming the Master: Knowledge Amalgamation for Joint Scene Parsing, Depth Estimation, and More


### Learning Metrics From Teachers: Compact Networks for Image Embedding



### Relational Knowledge Distillation


### Learning Without Memorizing

### Learning Not to Learn: Training Deep Neural Networks With Biased Data


---
## Interpretability
### Interpreting CNNs via Decision Trees


### Interpretable and Fine-Grained Visual Explanations for Convolutional Neural Networks

### Attention Branch Network: Learning of Attention Mechanism for Visual Explanation

---
## 3D Vision
### What Do Single-View 3D Reconstruction Networks Learn?

### DeepVoxels: Learning Persistent 3D Feature Embeddings


### Learning Spatial Common Sense With Geometry-Aware Recurrent Networks

---
## Reinforcement Learning
### Deep Reinforcement Learning of Volume-Guided Progressive View Inpainting for 3D Point Scene Completion From a Single Depth Image



---
## References
### Visual Question Answering
- [Actively Seeking and Learning From Live Data](http://openaccess.thecvf.com/content_CVPR_2019/papers/Teney_Actively_Seeking_and_Learning_From_Live_Data_CVPR_2019_paper.pdf)
- [MUREL: Multimodal Relational Reasoning for Visual Question Answering](http://openaccess.thecvf.com/content_CVPR_2019/papers/Cadene_MUREL_Multimodal_Relational_Reasoning_for_Visual_Question_Answering_CVPR_2019_paper.pdf)
---