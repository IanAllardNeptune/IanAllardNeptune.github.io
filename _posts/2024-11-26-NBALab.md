---
layout: post
title: NBA Data Correlations From 1996-Present
subtitle: An analysis of different NBA statistics and their correlations.
cover-img: assets/img/lab3nbaphoto.webp
thumbnail-img: assets/img/lab3nbaphoto.webp
share-img: assets/img/lab3nbaphoto.webp
tags: [NBA, Statistics]
author: Ian Allard-Neptune
---




# Intro

I went into this project seeking out a fairly clean dataset with something I'm interested in. I ended up finding this (relatively) clean  [Dataset](https://www.mdpi.com/2075-4426/14/9/958) on the NBA. It shows some of the most important NBA stats for each player in pts, reb, ast, etc. from the 1996-1997 season to the 2022-2023 season.

### The Authors

There are only two authors cited for the paper who voice some concerns. The first, Masab A. Mansoor, a "Medical Student at Edward Via College of Osteopathic Medicine," has written multiple papers on various subjects relating to his practice in medicine. I noted how he is credited to 12 papers, 11 of which were made in 2024. 

![Kashif H. Ansari SciProfile:](/assets/img/AuthorMetaAnalysis.png)

The next author, Kashif H. Ansari, has been an oncologist for over 20 years and received his medical degree from DOW University of Health Sciences. He has only made one paper. Immediately, several red flags are present from just the information about the authors. They cite no one else for this paper, which seems unrealistic as it is a comprehensive study of artificial intelligence, which an oncologist and a medical student need to be more qualified for. 

### Content

#### Beginning:

A general issue this paper has is that the exact goal it is trying to achieve is unclear. The basic premise is testing current AI's capabilities to detect mental health crises, but the way the data is analyzed and the conclusions are all over the place. If I had to diagnose a **Null Hypothesis:** There is no correlation between people’s social media presence and their potential to have a mental health crisis. Making the **Alternate Hypothesis:** There is a correlation between people’s social media presence and their potential to have a mental health crisis. However, as I stated, the conclusions the paper eventually makes are not directly correlated to these hypotheses.

The paper clearly describes the need for better research in this field, as the potential of having a functioning AI to aid with mental health could save thousands of lives. This field is in its "infancy" and needs much more improvement before it becomes practical for real-life use. Another aspect of the mental health / AI field they touch on is the ethics behind gathering people's social media posts. They introduce the point very briefly that taking public posts may be unethical but never address it again until the end of the paper when they explain that "Patient consent was waived due to all data being publicly available." This is quite hand-wavy as it acknowledges the potential issues but hypocritically uses public information in the study. I would have appreciated a more fleshed-out segment dedicated to privacy, which I think will likely be the future make or break of AI in this field. 


#### The Method of the Study

The AI network created was a multimodal deep learning model that "[integrates] natural language processing and temporal analysis techniques." The model was trained on a data set of 996,452 social media posts across different social media in different languages. The method by which this paper intends to evaluate the AI's performance is by comparing its results with professional psychiatric assessments. There were three phases, including "data collection, model development, and validation".

###### Data Collection, Model Development, and Validation.


They went through a stringent process of only collecting public data, which then went through depersonalization phases to ensure the practice was ethical. The initial collection of data from various social media sites was accessible as most have built-in APIs to sift through posts on their platform.

The model architecture was relatively straightforward and largely used preexisting networks for different stages, such as BERT (Bidirectional Encoder Representations from Transformers), a well-known NLP model developed by Google specialized for AI analysis of text, and established AI architectures such as the LSTM (Long Short-Term Memory networks), which specializes in sequence data. The general theme behind their model was that it largely meshed together from different pre-trained models. They used common splitting of data into training (60%), validation (20%), and test (20%). But, an interesting note from this section was how they completed the training and validation steps. 

![Model Architecture:](/assets/img/metaAnalysisArchitechture.png)


They did not give specifics on how many GPUs were used in the training, but they did specify that exactly three board-certified psychiatrists "manually annotated a subset of the data (100,000 posts)!" A simple prompt from ChatGPT came up with the response that the payment for three psychiatrists costs a range of $83,350 to $250,050! Notably, the researchers state at the end of the paper that the research received no external funding! Another unexplained point in this study.

![ChatGPT Psyciatrist Analysis:](/assets/img/realmetaanalysisdata.png)


#### The results

They deemed their model successful, with an 89.3% agreement rate with the expert psychiatrists. The model performed the best for English but had a generally good score across all of the tested languages. Interestingly, the model performed best with Twitter's platform, likely because it is largely text-based. The categories of crisis that the model performed best in were suicidal ideation and depressive episodes. 

The most crucial error analysis they give is the extrapolation of their false positives and negatives. Sarcasm and irony were the leading causes behind false positives, followed by hyperbolic temporary reactions to various non-serious events. For false negatives, despite an entire branch of their model dedicated to noticing the changing frequency of an individual's posts, the most common false negatives were sourced by a gradual decline in someone's mental health.


### Conclusion

Overall, the content of this paper was exciting and proved that there is a lot of potential for AI in this field in the future. They sufficiently proved 89.3% accuracy with an almost seven-day faster response than a psychiatrist, which most certainly could save lives in the future. Personally, I could totally see a much more developed model that was built uniquely for this purpose and not just a cumulation of pre-trained models that could function as a warning system in the future. Just like the model came to its conclusion and then was verified by an expert psychiatrist, maybe there would be a system in which if the model could predict with high confidence that someone will experience a mental health episode, then a psychiatrist can verify and possibly intervene.

Positive parts aside, I had some serious issues with this paper. Specifically, the paper needs more information that would make it genuinely verifiable. A glaring example would be how only two authors are cited for this paper, and neither of them has the qualifications one would expect for a research topic such as this. Additionally, no conflicts of interest were cited, and no outside funding existed. The one convincing piece of information the study gives is that an Ethics Committee approved it. While this committee may have verified them, there needs to be an explanation of the process by which someone can achieve that acceptance.

Additionally, assuming the paper is ethical, it does not make the findings accurate or truthful. Logistically, taking everything into account one of two realities must be true: the paper is incorrectly credited or fake. Even the best case of the paper, being that it incorrectly cites the number of authors and the funding, hurts its credibility greatly, and other questions arise about what ulterior motives these individuals may have.













