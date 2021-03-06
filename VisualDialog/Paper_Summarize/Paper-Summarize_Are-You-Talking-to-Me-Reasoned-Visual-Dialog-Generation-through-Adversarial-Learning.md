## Are You Talking to Me? Reasoned Visual Dialog Generation through Adversarial Learning

### Indexing
- [Introduction](#Introduction)
- [Approach](#Approach)
- [Experiments](#Experiments)
- [Conclusion](#Conclusion)
- [Thoughs](#Thoughts)
- [Reference](#Reference)


---
### Introduction
- Human-like vs. Machine-like responses in a visual dialog

<img src="https://github.com/qiuyue1993/Notes/blob/master/VisualDialog/images/Paper-Summarize_Reasoned-Visual-Dialog-through-GAN_overview.png" width="400" hegiht="400" align=center/> 


- We present a novel approach that combines **Reinforcement Learning** and **Generative Adversarial Networks (GANs)** to generate more **human-like responses** to questions. 
We particularly frame the task as a reinforcement learning problem that we jointly train two sub-modules:
- a **sequence generative model** to produce response sentences on the basis of the image content and the dialog history
- a **discriminator** that leverages previous generator’s memories to distinguish between the humangenerated dialogs and the machine-generated ones. 
-  Finally, as with most sequence generation problems, the quality of the response can only be assessed over the whole sequence. We follow apply Monte Carlo search to **calculate the intermediate rewards**. 

#### Dialog generation in NLP
- The dialog generation is typically viewed as a **sequence-to-sequence (Seq2Seq)** problem, or formulated as a **statistical machine translation problem**.
- Inspired by the success of the Seq2Seq model in the machine translation, end-to-end dialog generation models have been built using an **encoder-decoder**. **Reinforcement learning (RL)** has also been applied to train dialog systems.

---
### Approach
- Proposed adversarial learning framework

<img src="https://github.com/qiuyue1993/Notes/blob/master/VisualDialog/images/Paper-Summarize_Reasoned-Visual-Dialog-through-GAN_proposed-model.png" width="600" hegiht="300" align=center/> 

Proposed model is composed of two components:
-  A sequential co-attention generator that accepts as input image, question and dialog tuples, and uses the co-attention encoder to jointly reason over them.
-  A discriminator tasked with labelling whether each answer has been generated by a human or the generative model by considering the attention weights. 
The output from the discriminator is used as a reward to push the generator to generate responses that are indistinguishable from those a human might generate.

---
### Experiments
- Evaluation Metrics: MR; Recall@k; MRR
-  Results on VisDial v0.9

<img src="https://github.com/qiuyue1993/Notes/blob/master/VisualDialog/images/Paper-Summarize_Reasoned-Visual-Dialog-through-GAN_experiments-results.png" width="600" hegiht="300" align=center/> 

---
### Conclusion
-  In this paper, we have proposed an adversarial learning based approach to encourage the generator to generate more human-like dialogs. 
-  Technically, by combining a **sequential co-attention generative model** that can jointly reason the image, dialog history and question, and a **discriminator** that can dynamically access to the attention memories, with an **intermediate reward**, our ﬁnal proposed model achieves the state-of-art on VisDial dataset. 
---
### Thoughts

---
### Reference
- [Are You Talking to Me? Reasoned Visual Dialog Generation through Adversarial Learning](http://openaccess.thecvf.com/content_cvpr_2018/papers/Wu_Are_You_Talking_CVPR_2018_paper.pdf)


---
