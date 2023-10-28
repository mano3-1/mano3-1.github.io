---
layout: page
title: Projects
permalink: /projects/
weight: 1
---

## **Projects - Professional /Internships**

---
### **At Tiger Analytics as ML Engineer**


**Bug Risk Prediction**
<ul>
<li>
Deployed a model to predict out of sprint bugs using Jira Data.
</li>
<li>
The model consumes different features like past bug prevalence in an epic, assignee's past performance, 
word level features of the story description, etc.,. 
</li>
<li>
Used Jenkins to schedule a job that runs the model periodically (everyday in offshore hours) to score stories that are in ready status. The results are written to database from which a Grafana dashboard is created to visualize the results.
</li>
<li>
Along with predictions, shap values are computed to help scrum masters to know which factor is contributing towards bug risk and act accordingly.
</li>
</ul>

---

### **At Decimal Point Analytics as Data Scientist**

**CSV Agent**
<ul>
<li> DevelopedaCSVagentutilizinglargelanguagemodelstofacilitate natural language interaction with
Excel files. </li>
<li>  Designed the agent to understand user queries and generate goals based on their input. The agent
writes code to execute actions corresponding to the defined goals, allowing seamless interaction with CSV data. </li>

<video controls="controls" width="600" height="350">
    <source src="https://drive.google.com/uc?export=download&id=1k42rvMM4aGNHzzlubCV1iJ2yn5ajb3rV" type='video/webm'/>
</video>

</ul>

**Dolat Summarization**
<ul>
<li> Contributed to the fine-tuning of a large language model on consumer GPUs to generate summarizations of earnings calls. </li>
<li> Leveraged advanced techniques, such as LoRA, to optimize the training process for large models on consumer-grade hardware. </li>
<li> Collaborated with a teamtoworkwithstate-of-the-art models like Pythia, MPT, GPT-Neo-X, and T5 Flan, achieving significant progress in the project. </li>
</ul>

**Semantic Datatype Detection**
<ul>
 <li> Designed and developed a high-accuracy transformer model for automated classification of column data types, leveraging a dataset of 800K data points from both online and internal sources. </li>
 <li> Achieved an impressive 94% accuracy on the test set, demonstrating the model’s robustness and effectiveness. In addition, trained a LSTM model with an embedded layer to learn character embeddings, which achieved a solid accuracy of 85%. </li>
 <li> Conducted rigorous experimentation and analysis to optimize model performance and improve
 accuracy. </li>
</ul>

**ESG Classifier**
<ul>
 <li> Worked on a project with the objective of developing a text classifier capable of accurately categorizing text into three distinct genres: environmental, social, and governance. </li>
 <li> Incorporated the GradCam technique to visualize the specific phrases that the BERT model focused on during the classification process, enhancing interpretability and transparency of the final output. </li>
</ul>

**Tiger automation**
<ul>
 <li> Worked on a project to automate the appraisal process by developing a robust data processing pipeline using PySpark. </li>
 <li> Leveraged Snowflake database as the primary data source and performed all calculations and transformations using PySpark's distributed processing capabilities. </li>
</ul>

**PDF2Excel**
<ul>
 <li> Worked on development of a cutting-edge ML pipeline for converting PDF tables to Excel, utilizing OCR and advanced layout detection models. Leveraged DiT (document image transformer) to accurately detect the layout of PDFs and extract tabular data. </li>
</ul>

**AutoML**
<ul>
 <li> Working on an end-to-end pipeline that automates diverse ML processes, including preprocessing, feature selection, model selection, and hyperparameter tuning. </li>
 <li> Developed with a vision to democratize model training, the product aims to empower individuals with non-technical backgrounds, making it effortless and accessible for them to engage in machine learning. </li>
</ul>

---

### **At Decimal Point Analytics as Software Development Intern**

**Blockchain based Chat and Bid Application**
<ul>
<li>Designed and developed a cutting-edge blockchain-based chat and bidding application, leveraging the power of Hedera Hashgraph.</li>
<li>Utilized Hedera Hashgraph's JavaScript API to build a secure and robust application that enabled seamless messaging and bidding transactions.</li>
</ul>

---
### **At SchoolHack as AI/ML Engineer**

**IQL for ChatGPT**
    
<ul>
<li>Used Implicit Q learning to pick up engaging answers from ChatGPT</li>
<li>Automated IQL finetuning pipelines using AWS EC2 and AWS S3 bucket</li>
<li>The IQL is performed periodically just by calling an API and this API is responsible to pull data from S3, finetune it using IQL on an ec2 instance and update the weights</li>
</ul>

**Live Translation from English to other foreign Langugaes**
    
<ul>
<li> Used seamless-m4t model (developed by Meta) to translate ChatGPT/llama's replies into other foreign language, mainly Arabic. </li>
<li> Seamless-m4t requires the label for input language to do the translation. Hence, a separate language detector, xlm-roberta is deployed alongside.</li>
<li>To handle the traffic, the model is deployed on two g4dn xlarge GPUs using AWS sagemaker service. </li>
</ul>

**Llama2 Finetuning**
    
<ul>
<li> As a leading LLM application, School Hack generated a lot of data everyday. </li>
<li>Finetuned Llama2 7b model on a 1M chat datapoints</li>
<li>The training is done on G5.48xlarge instance on AWS. </li>
</ul>

---
---

## **Projects - Academic/Personal**
    
1. Automation of Cleaning cervical data using deep learning techniques:

    Developed a supervised contrastive model to filter outliers in a cervical image dataset resulted in superior performance when compared to human cleaning. These impressive findings were published in the prestigious IEEE Access journal.
        
2. EfficientCenterDet: A novel Self supervision boosted RoI proposal network for cervix type detection [[code]](https://github.com/mano3-1/EfficientCenterDet-for-cervix-type-detection):

    A fully automated self-supervised pipeline has been developed for the detection of cervical cancer. This impressive feat was achieved by leveraging a novel object detector, which drew inspiration from both the efficientdet architecture and centrenet loss. These impressive findings were published in the prestigious International Journal of Imaging Systems and Technology.

        
        
3. Covid-19 detection from CT scans [[code]](https://github.com/mano3-1/Covid-detection-with-CT-scans):
    
    I successfully designed and implemented an advanced EfficientNet architecture that accurately predicts Covid-19 infection through CT scans. To ensure optimal performance, I employed a BCD U-net for efficient segmentation of the region of interest. These findings were communicate to a conference.


        
4. Cassava Leaf disease classification [[code]](https://www.kaggle.com/saimanojakondi/the-cassava/notebook):
        
    I undertook a challenging Kaggle competition by implementing a variety of advanced models, including Vision Transformer, EfficientNets, and ResNets, all trained using Bi-Tempered Loss. To achieve even greater accuracy, I utilized an ensemble of these models in conjunction with Test Time Augmentation (TTA).
        
        
5. Stock Market prediction with tabnet [[code]](https://github.com/mano3-1/Flipr_Hackathon): 
        
    Successfully trained tabnet architecture, (original developed by google AI cloud) for regressing over a complex tabular data. Along with tabnet, I also trained gradient boosted tree algorithms like xgboost, catboost. Also, trained RNN for puts call ratio from historical data. I leveraged self supervised methods to handle missing values and ensure the highest level of model accuracy.   


6. Tweet Sentiment Extraction [[code]](https://github.com/mano3-1/Sentiment-Extraction-from-tweets): 
    Worked on a project to extract key phrases given the sentiment from tweets, utilizing multiple advanced transformers, including XLNet, RoBERTa, and alBERT. To achieve even greater performance, I implemented an ensemble of these models, further enhancing my model's predictive power

7. Human Activity Recognition using 2D pose [[code]](https://github.com/mano3-1/Human-Activity-Recognition):
    For this project, I tackled the challenging task of detecting human activities from video data. To achieve this, I utilized the powerful pose recognition model, Posenet, as a starting point, and built a custom Convlstm head on top of it. This model was then fine-tuned using a data input of 20 frames at a time, allowing for greater accuracy in activity detection.
        
8. Multi task learning for self driving cars:
        
    Developed a single neural network that can perform object detection, segmentation and depth perception using IDD dataset
    

---
---


## Roles, Responsibilities and Interests

### Professional  Level:

**Domain Knowledge:**

- Machine Learning
- Deep Learning
- Artificial Intelligence
- Cloud Computing

**Responsibilities:** 

- Exploration of SOTA Models
- Research Paper reading
- Approaches development for the use case
- Helping  SA's in Architecture Development
- Model Development Research
- Model Development, Training, and Evaluation
- Model Optimisation (Quantization and Pruning)
- Model Deployment
- Integrating model deployments with other cloud components
- Pipeline regular maintenance metadata scripts

### Personal (Passion) level:

**Interests:**

- NLP (LLMs)
- Machine learning - Tradition + Deep Learning
- Reinforcement learning
- Explainable AI