<h1 align="center"><img src="https://readme-typing-svg.demolab.com?font=Chakra+Petch&weight=500&size=29&duration=1&pause=1000&color=000000&background=601EF9&vCenter=true&repeat=false&width=990&lines=AI+Agent+Psychiatrist+for+Mental+Health" alt="Typing SVG" /></h1>

<div align="center">
  <img src="https://github.com/Laoode/AI-Agent-Psychiatrist/blob/main/assets/banner.gif" alt="banner">
</div>

---
# Table of Contents
1. [Overview](#overview)
2. [Background](#background)
3. [Methodology](#methodology)
4. [Data Collection](#data-collection)
    
## Overview
This project aims to develop an artificial intelligence (AI)-based chatbot that supports mental health and suicide prevention, in line with Sustainable Development Goals (SDGs) 3.4.2, which focus on reducing suicide mortality.

## Background
As foundation we are about SDG’s 3.0 which focused on "Healthy and Prosperous Lives". It aims to guarantee health and well-being for all people around the world. One of sub purpose in SDG’s 3.0 is to reduce premature mortality from non-communicable diseases by a third, through prevention and treatment, and improve mental health and well-being. 

Based on WHO data, more than 700,000 people die from suicide every year. In Indonesia, data from POLRI shows that the death rate from suicide in 2023 increased to 1,350 cases, from 826 cases in the previous year. The reasons why someone commits suicide are complex and influenced by various factors, such as biological, genetic, psychological, cultural, and environmental factors. For this reason, we emphasized that efforts related to mental health, especially to prevent suicide, must be the concern of all parties.

Increases in suicide rates are linked to several factors. Mood and affective disorders often coincide with higher suicide rates. Additionally, experiences such as loss, loneliness, and discrimination can increase suicide risk. The media's portrayal of suicide can also impact rates; an increase in suicide stories can lead to a rise in actual suicides. Financial problems and chronic pain are also contributing factors. Therefore, comprehensive prevention strategies should address mental health, social support, and responsible media coverage to mitigate the risk factors associated with suicidal behavior.

Many suicides are unexpected as victims often hide their feelings and do not show any suspicious signs. Loved ones are often unaware that someone is under stress or has even attempted suicide before. The main causes of suicide are generally related to mental health issues, anxiety, depression, and overwhelming life situations. Although most suicidal people want to get help and release their pain, they appear so normal that they are difficult to recognize.

The concern is that people with suicidal thoughts often hide their stress, making it difficult for others to notice and offer support

In the USA have mental health call center (988) for people who are in crisis and may have suicidal thoughts.

<div align="center">
  <img src="https://github.com/Laoode/AI-Agent-Psychiatrist/blob/main/assets/988-contacts-data.webp" alt="988 contacts data">
</div>

Based on data 988 lunch in 2022 and have big impact in USA for someone with anxiety and suicidal ideation. We can see most 988 reached by calls which the people have suicidal, it means they comfort to talking rather text or chats.

Psychiatrists are responsible for patients who meet suicide risk criteria. A psychiatrist can evaluate the patient's psychological and medical condition through interviews or psychiatric medical examinations.

The disadvantage is for area who difficult to meet one on one with the Psychiatrist. For this consideration we introduces AI Agent Psychiatrist for Mental Health. 

AI Agent Psychiatrist  is a revolutionary health-tech platform bringing quality psychotherapy to the general public in the form of online sessions with AI-powered therapists. This way, we provide more efficient, affordable, and accessible mental health care to patients around the world by combining the efficiency of AI and human expertise in psychology.

### The Advantages
#### Availability anytime, anywhere
Unlike human psychotherapists, whose sessions must be scheduled in advance, AI will be accessible anytime by simply logging in.
#### Reduced social stigma
Digital psychotherapists eliminate social stigma by avoiding face-to-face interaction and promoting comfort in discussing deep issues and traumas, for traditional therapy.
#### Lack of bias
AI, unlike traditional therapists, is entirely objective, unbiased, and non-judgmental, despite inherent bias and influence from personal experiences and emotions.
#### Affordability
Unlike human psychotherapists, who need to factor their time into the cost, AI is more affordable as it can help hundreds of thousands of people simultaneously.

## Methodology
We will use LLM as the base model for generated answer based on question and improve the model to act like agent aka Psychiatrist Agent. So how to pick the best model LLM?
In this case we will using model LLM as local model or running with our server not third party cause the healthcare is very risky. So what is the best model to solve tasks about mental health it means healthcare filed?

<div align="center">
  <img src="https://github.com/Laoode/AI-Agent-Psychiatrist/blob/main/assets/evaluating-llm-healthcare.webp" alt="evaluating llm">
</div>

According research Standford Medicine, to pick best LLM model for healthcare can using framework which called  [MedHELM](https://crfm.stanford.edu/helm/medhelm/latest/), HELM standing for holistic evaluation of language models. It's a resource for accurate and reliable evaluations of LLMs, supporting the core principles that power the [RAISE Health](https://med.stanford.edu/raisehealth.html) Initiative.
Shah discussed how MedHELM is best used, how it can help researchers adapt and create their own models, and why it's crucial to evaluate LLMs in the context in which they're used. This interview was edited for clarity and length.

<div align="center">
  <img src="https://github.com/Laoode/AI-Agent-Psychiatrist/blob/main/assets/medhelm.webp" alt="medhelm">
</div>

Based on MedHELM evaluation the best model llm to using for medical or healthcare task is DeepSeek R1 as rank 1 with mean win rate 0.663. So in this case, we will DeepSeek R1 model to fine tuning the model with our data sets about mental health with LORA technique. [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948). With capability of LLM combined with Reinforcement Learning, makes the DeepSeek can outperform to with others model.

### Lora Technique
Think of training a model like learning a new skill. You start with basic knowledge (initializing parameters), practice (forward pass), and compare your results to the target (desired output). Then, you refine your technique (backward pass) and repeat. Eventually, you become proficient (trained model).
Low-Rank Adaptation (LoRA) method is a fine-tuning method introduced by a team of Microsoft researchers in 2021. LORA has extended the idea which is quoted in this [paper](https://arxiv.org/pdf/2012.13255.pdf) to one level further, We will using LLM as base model

## Data Collection
This project utilizes data scraped from Counselchat.com, an expert community platform where licensed clinical counselors respond to user questions. This [dataset](https://huggingface.co/datasets/nbertagnolli/counsel-chat), collected on 20220401, provides a unique view into expert-client interactions, featuring responses from therapists to questions posed by individuals. 
<div align="center">
  <img src="https://github.com/Laoode/AI-Agent-Psychiatrist/blob/main/assets/datasets.png" alt="dataset">
</div>