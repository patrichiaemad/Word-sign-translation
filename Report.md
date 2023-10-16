# Project Report

## Table of Contents

1. [Introduction](#1introduction)
2. [Problem Statement](#2problem-statement)
    1. [Challenges](#21challenges)
    2. [Approaches](#22approaches)
    3. [Metrics](#23metrics)
3. [Dataset](#3dataset)
    1. [Dataset Analysis](#31data-analysis)
    2. [Dataset Description](#32data-description)
    3. [Dataset Problem](#33dataset-problems)
    4. [Dataset Conclusion](#34conclusion)
4. [Deep Learning Approaches](#4deep-learning-approaches)
    1. [I3D](#i3d-model)
    2. [TGCN](#tgcn-model)
5. [Results](#5results)
    1. [I3D](#51i3d-model)
    2. [Results](#52results)
    3. [Graphs](#53graphs)
6. [Future Work](#6future-work)
7. [Acknowledgements](#7acknowledgements)

## 1.Introduction

**Word Sign Language (WSL)** is a problem in computer vision and natural language processing that involves recognizing and translating sign language words into text. Sign languages are visual-spatial languages that use hand gestures, facial expressions, and body language to communicate. They are used by deaf and hard-of-hearing communities around the world and are different from spoken languages.

The **WSL problem** involves developing algorithms that can accurately recognize and interpret sign language gestures in real-time, and translate them into text or speech for communication with hearing individuals. This is a challenging task due to the complexity and variability of sign language gestures, as well as the lack of large-scale datasets for training machine learning models.

**WSL** is important for several reasons:

- **Improved communication**: WSL technology can enable better communication between deaf and hard-of-hearing individuals and hearing individuals by providing a real-time translation of sign language into text or speech.

- **Accessibility**: WSL technology can make information and services more accessible to deaf and hard-of-hearing individuals by allowing them to communicate more easily with others.

- **Inclusion**: WSL technology can promote inclusion and equal opportunities for deaf and hard-of-hearing individuals by reducing barriers to communication and access to information.

- **Education**: WSL technology can be used to develop educational materials and tools for teaching sign language, which can help to preserve and promote the use of sign languages.

- **Research**: WSL technology can be used to study and understand sign languages, which can help to improve our understanding of human language and communication.

Overall, **WSL** is a crucial technology in order to bridge the communication gap between hearing and non-hearing individuals and make the world more inclusive and accessible for everyone.

## 2.Problem Statement

The **WSL problem** involves developing algorithms that can accurately recognize and interpret sign language gestures in real-time, and translate them into text or speech for communication with hearing individuals.

### 2.1.Challenges

1. One of the most important challenges in the **WSL problem** is the lack of large-scale datasets for training machine learning models. This is because sign language is a visual-spatial language that is difficult to record and annotate. This makes it difficult to collect large amounts of data for training machine learning models.

2. Another challenge in the **WSL problem** is the complexity and variability of sign language gestures. This is because sign language is a visual-spatial language that uses hand gestures, facial expressions, and body language to communicate. This makes it difficult to accurately recognize and interpret sign language gestures in real-time.

3. A third challenge in the **WSL problem** is the lack of standardization in sign language. This is because sign languages are used by deaf and hard-of-hearing communities around the world, and they are not standardized. This makes it difficult to develop algorithms that can accurately recognize and interpret sign language gestures in real-time.

### 2.2.Approaches

1. One approach to the **WSL problem** is to use deep learning models to recognize and interpret sign language gestures in real-time. This is because deep learning models can learn complex patterns in large amounts of data, and they can be trained to recognize and interpret sign language gestures in real-time.

2. Another approach to the **WSL problem** is to use computer vision and natural language processing techniques to recognize and interpret sign language gestures in real-time. This is because computer vision and natural language processing techniques can be used to recognize and interpret sign language gestures in real-time.

3. A third approach to the **WSL problem** is to use machine learning models to recognize and interpret sign language gestures in real-time. This is because machine learning models can be trained to recognize and interpret sign language gestures in real-time.

**Table of comparison between the 3 approaches:**

|Approach|Pros|Cons|
|:-|:-|:-|
|Deep Learning Models|Can learn complex patterns in large amounts of data|Lack of large-scale datasets for training machine learning models|
|Computer Vision and Natural Language Processing Techniques|Can be used to recognize and interpret sign language gestures in real-time|Lack of standardization in sign language|
|Machine Learning Models|Can be trained to recognize and interpret sign language gestures in real-time|Complexity and variability of sign language gestures|

### 2.3.Metrics

1. One metric to evaluate the performance of algorithms in the **WSL problem** is accuracy. This is because accuracy is a measure of how well an algorithm performs on a dataset. It is calculated by dividing the number of correct predictions by the total number of predictions.
    - $accuracy = \frac{correctPredictions}{totalPredictions}$

2. Another metric to evaluate the performance of algorithms in the **WSL problem** is precision. This is because precision is a measure of how well an algorithm performs on a dataset. It is calculated by dividing the number of true positives by the total number of true positives and false positives.
    - $precision = \frac{truePositives}{truePositives + falsePositives}$

3. A third metric to evaluate the performance of algorithms in the **WSL problem** is recall. This is because recall is a measure of how well an algorithm performs on a dataset. It is calculated by dividing the number of true positives by the total number of true positives and false negatives.
    - $recall = \frac{truePositives}{truePositives + falseNegatives}$

4. A fourth metric to evaluate the performance of algorithms in the **WSL problem** is loss. This is because loss is a measure of how well an algorithm performs on a dataset. It is calculated by subtracting the predicted value from the actual value, squaring the result, and then averaging the results.
    - $loss = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y_i})^2$

**Table of comparison between the 3 metrics:**

|Metric|Pros|Cons|
|:-|:-|:-|
|Accuracy|Easy to understand and interpret. Good for overall performance evaluation.|Does not take into account false positives and false negatives|
|Precision|Good for problems where false positives are more costly than false negatives. Provides a measure of how many relevant items are selected.|Doesn't take into account false negatives .Doesn't work well when the dataset is imbalanced.|
|Recall|Good for problems where false negatives are more costly than false positives. Provides a measure of how many relevant items are missed.|Doesn't take into account false positives. Doesn't work well when the dataset is imbalanced.|
|Loss|Provides a direct measure of model's performance. Can be used as a stopping criterion for training.|Can be hard to interpret. Depends on the choice of loss function.|

### 2.4.Conclusion

- We choose the deep learning approach as it would be the most suitable way for us to solve this problem.

- And decided to report our resuls on accuracy.

## 3.Dataset

The **WLASL** dataset is a large-scale dataset for training machine learning models to recognize and interpret sign language gestures in real-time. It contains 21,095 videos of sign language gestures, and it is divided into 2,000 classes. Each video is annotated with the corresponding sign language word.

The **WLASL** dataset is important for several reasons:

1. It is the largest dataset for training machine learning models to recognize and interpret sign language gestures in real-time.
2. It is annotated with sign language words.
3. It is divided into 2,000 classes.

### 3.1.Data analysis

1. The **WLASL** dataset contains 21,095 videos of sign language gestures.
2. The **WLASL** dataset is divided into 2,000 classes.
3. Each video in the **WLASL** dataset is annotated with the corresponding sign language word.

### 3.2.Data Description

- `gloss`: *str*, data file is structured/categorised based on sign gloss, or namely, labels.
- `bbox`: *[int]*, bounding box detected using YOLOv3 of (xmin, ymin, xmax, ymax) convention. Following OpenCV convention, (0, 0) is the up-left corner.
- `fps`: *int*, frame rate (=25) used to decode the video as in the paper.
- `frame_start`: *int*, the starting frame of the gloss in the video (decoding
with FPS=25), *indexed from 1*.
- `frame_end`: *int*, the ending frame of the gloss in the video (decoding with FPS=25). -1 indicates the gloss ends at the last frame of the video.
- `instance_id`: *int*, id of the instance in the same class/gloss.
- `signer_id`: *int*, id of the signer.
- `source`: *str*, a string identifier for the source site.
- `split`: *str*, indicates sample belongs to which subset.
- `url`: *str*, used for video downloading.
- `variation_id`: *int*, id for dialect (indexed from 0).
- `video_id`: *str*, a unique video identifier.

### 3.3.Dataset problems

After downloading the dataset we found that.

1. Alot of the videos was missing from the dataset.
2. The dataset was nnbalanced.
    > Each gloss doesn't have the same number of videos

|Gloss|Expected|Actual|
|:-| :-| :-|
|100|2038|1013|
|300|5118|2661|
|1000|13174|7238|
|2000|21095|11992|

> Totla number of missing videos = 9103

### 3.4.Conclusion

1. The unbalanced data increased.
2. Fewer videos in each gloss.

**Solution approach:**

1. Making data augmentation to increase the dataset by:
    - Random crops
    - Random rotaion
2. Making a new subset of the dataset with the same number of videos.
    - To balance the dataset
    - Eliminate any kind of bias in our model

**The new subset used:**

- Number of gloss = 48
- Number of videos/gloss = 10
- Splitting ratio used 8:1:1

|Gloss|
|:-|
appointment
argue
bad
balance
because
bird
black
blanket
cheat
convince
cry
daughter
delicious
doctor
fat
fish
full
give
good
government
graduate
hot
interest
language
like
many
move
orange
order
perspective
ready
sandwich
secretary
silly
snow
son
speech
study
sweet
tell
theory
toast
wait
white
work
write
year
yesterday

## 4.Deep learning Approaches

### I3D Model

- I3D is a type of deep learning model that is specifically designed for processing video data.
- I3D is based on the idea of "inflating" the weights of a 2D convolutional neural network (CNN) trained on image data so that the CNN can be used to process video data directly.
- I3D is particularly well-suited for tasks that involve recognizing and understanding complex spatial-temporal patterns in video data, such as action recognition, object recognition, and video classification.
- To train an I3D model, the input data must be a sequence of video frames.
  - The model learns to recognize patterns and dependencies in the data by applying 3D convolutional operations to the video frames.
  - I3D is able to capture both spatial and temporal features in the data, making it well-suited for tasks that involve recognizing patterns and dependencies over time.
- I3D has been applied to a variety of tasks in different domains, including action recognition, object recognition, and video classification.
  - In action recognition, I3D can be used to recognize and classify different types of human or animal actions in video data.
  - In object recognition, I3D can be used to recognize and classify different objects in video data, such as cars, pedestrians, or buildings.
  - In video classification, I3D can be used to classify video data into different categories, such as sports, news, or entertainment.

Overall, I3D is a powerful tool for processing video data and recognizing complex spatial-temporal patterns in the data. It has the potential to improve the performance of a wide range of applications in different domains, including action recognition, object recognition, and video classification.

### TGCN Model

> Temporal Graph Convolutional Network

- TGCN is a type of deep learning model that is specifically designed for processing data with both temporal and graph structures.
  - TGCN combines the strengths of Graph Convolutional Networks (GCN) with the ability to model temporal dependencies.
  - TGCN is well-suited for tasks such as predicting future events in a dynamic network.
- TGCN can be trained on datasets that include both temporal and graph data, such as sequences of events in a social network or financial market.
  - The model learns to recognize patterns and dependencies in the data that are not easily captured by traditional machine-learning models.
  - TGCN can be used to make predictions or recommendations based on these patterns.
- To train a TGCN model, the input data must be structured as a sequence of graph snapshots.
  - Each snapshot represents the state of the graph at a specific time point.
  - The TGCN model applies convolutional and temporal operations to the graph snapshots and uses an RNN or TCN to model the temporal dependencies between the snapshots.
- TGCN has been applied to a variety of tasks, including recommendation systems, fraud detection, and natural language processing.
  - In recommendation systems, TGCN can be used to recommend items to users based on their past interactions with other users and items in the system.
    - For example, TGCN can learn to recognize patterns in users' interactions with the system (e.g., which items they have viewed, purchased, or rated), and can use these patterns to make recommendations to other users based on their past behavior.
  - In fraud detection, TGCN can be used to identify patterns of fraudulent activity in financial transactions or social networks.
    - TGCN can learn to recognize patterns of transactions that are characteristic of money laundering or other types of fraud and can be used to flag transactions that are likely to be fraudulent.
  - In natural language processing, TGCN can be used to analyze the structure and dynamics of language use in social media or other online platforms.
    - TGCN can learn to recognize patterns in language use that are not easily captured by traditional machine learning models and can be used to classify text or make predictions about future language use.

Overall, TGCN is a powerful tool for processing data with temporal and graph structures and has the potential to improve the performance of a wide range of applications. By learning to recognize patterns and dependencies in the data that are not easily captured by traditional machine learning models, TGCN can provide insights and predictions that are valuable for a variety of tasks and domains.

|  | TGCN | I3D |
| :-| :-| :-|
| Data type | Temporal graph data | Video data |
| Architecture | Graph convolutional network + RNN or TCN | Inflated 3D CNN |
| Key Characteristics | Model patterns and dependencies in temporal and graph data | Model spatial-temporal patterns in video data |
| Applications | Recommendation systems, fraud detection, and natural language processing. | Action recognition, object recognition, and video classification. |

## 5.Results

### 5.1.I3D Model

After training the model with the following parameters:

- Batch size = 3
- Epochs = 50
- Learning rate = 0.0001
- Update per stage = 1
- Optimizer = Adam
- Loss function = Cross entropy

### 5.2.Results

We got the following results:

|  | Train | Validation |
| :-| :-| :-|
| Accuracy | 1.0 | 0.625 |
| Loss | 0.002 | 0.0552 |

### 5.3.Graphs

![Graphs](/images/graph.jpeg)

## 6.Future Work

- We will try to collect more data to increase the dataset.
- We will build an application that will help the deaf people to communicate with the hearing people.

## 7.Acknowledgements

- We would like to thank our professor Dr. Noha El-Korany for her support and guidance.
