# Sign Language Translator System Report

## Table of Contents

1. [Introduction](#1-introduction)
2. [System Overview](#2-system-overview)
3. [Video Processing](#3-video-processing)
4. [Prediction Using Deep Learning](#4-prediction-using-deep-learning)
5. [Feedback Mechanism](#5-feedback-mechanism)
6. [Database Storage for Model Improvement](#6-database-storage-for-model-improvement)
7. [Integration with ChatGPT for Sentence Rewriting](#7-integration-with-chatgpt-for-sentence-rewriting)
8. [Choice of Architecture: Server-Based Approach](#8-choice-of-architecture-server-based-approach)
    - [8.1 Comparison of Approaches](#81-comparison-of-approaches)
    - [8.2 Our Choice: Server-based Approach](#82-our-choice-server-based-approach)
9. [System Specifications](#9-system-specifications)
   - [9.1 System Architecture](#91-system-architecture)
   - [9.2 API Endpoints](#92-api-endpoints)
10. [Conclusion](#10-conclusion)

## 1. Introduction

This report outlines the development and implementation of a Sign Language Translator System using a client-server architecture. The system enables users to capture videos of sign language gestures, which are then processed and evaluated by a machine learning model. The system also incorporates a feedback mechanism and utilizes a database to store videos, predictions, and user feedback, enabling continuous improvement and retraining of the model. Additionally, the integration with ChatGPT provides sentence rewriting capabilities to improve the grammatical and semantic correctness of the model's output.

## 2. System Overview

The Sign Language Translator System consists of two main components: the client application and the server backend. The client application provides a user-friendly interface for capturing sign language gestures through video recording and facilitates communication with the server backend. The server backend is responsible for processing the received videos, performing predictions using a machine learning model, and incorporating sentence rewriting through ChatGPT. The system leverages a database to store videos, predictions, and user feedback, creating a valuable resource for model improvement.

![Architecture](/images/Architecture-1.png)

## 3. Video Processing

The Sign Language Translator System employs video processing techniques to analyze the captured sign language gestures. The server backend receives the recorded videos from the client application and extracts relevant features from the video frames. These features serve as inputs to the deep learning model for further analysis and prediction.

We have implemented the following code for video processing:

```python
model_manager = ModelManager(
    weights="server/model/assets/weights/rgb_imagenet.pt",
    model="server/model/assets/model.pt",
    input_transforms=transforms.Compose([videotransforms.CenterCrop(224)])
)

@method
def evaluate_static(file_name: str) -> Result:
    video_input = ModelUtils.load_rgb_frames_from_video("server/test_videos/"+file_name + ".mp4")
    predictions = model_manager.evaluate(video_input)
    return Success(predictions)
```

The `evaluate_static` method takes a video file name as input and processes the video frames using the `ModelUtils.load_rgb_frames_from_video` function. The processed frames are then passed to the `ModelManager.evaluate` method to obtain the predictions for the sign language gestures.

## 4. Prediction Using Deep Learning

Deep learning plays a crucial role in the Sign Language Translator System for predicting the meaning of sign language gestures. The server backend utilizes a deep learning model that has been trained on a vast dataset of sign language gestures. The extracted features from the video frames are fed into the model, which generates predictions based on its learned representations and hierarchical structures.

```python
import torch
import torch.nn as nn
from torchvision import transforms

class ModelManager:
    def __init__(self, weights, input_transforms, model):
      # Model initialization and loading of weights

    def evaluate(self, video_input):
      # Video evaluation and prediction
```

The `ModelManager` class handles the loading and evaluation of the deep learning model. The `evaluate` method takes the preprocessed video frames as input and produces predictions for the sign language gestures.

## 5. Feedback Mechanism

To enhance the accuracy and performance of the Sign Language Translator System, a feedback mechanism is incorporated. The client application allows users to provide feedback on the accuracy of the model's predictions. This feedback is invaluable in identifying and rectifying any incorrect predictions, enabling continuous improvement of the system over time.

The following code snippet demonstrates the implementation of the feedback feature:

```python
@method
def feedback(id: str, feedback: str) -> Result:
    query = Prediction.objects.filter(id__exact=id)
    if len(query) < 1:
        return Error(2, "found no prediciton with this id")
    instance = query.first()
    instance.actual = feedback
    instance.save()
    return Success(True)
```

The `feedback` method takes an ID and user feedback as input and updates the corresponding prediction instance in the database with the provided feedback.

## 6. Database Storage for Model Improvement

The Sign Language Translator System employs a database to store videos, predictions, and user feedback. This database serves as a central repository for accumulating data that can be utilized for model improvement. By storing videos and their corresponding predictions, the system can analyze and evaluate the performance of the machine learning model. Additionally, user feedback is stored to identify patterns and trends, providing insights for refining the model and enhancing its accuracy.

## 7. Integration with ChatGPT for Sentence Rewriting

The Sign Language Translator System integrates ChatGPT, a powerful language model, for sentence rewriting. After the machine learning model generates a prediction, the output sentence is sent to ChatGPT for revision. ChatGPT utilizes its natural language processing capabilities to rewrite the sentence, ensuring grammatical and semantic correctness. The revised sentence is then returned to the server backend for further processing and delivery to the client application.

## 8. Choice of Architecture: Server-Based Approach

### 8.1. Comparison of Approaches

When considering the architecture for the sign language translator system, we evaluated two main approaches: installing the model on the server and using it as an API (Server-based approach) or installing the model directly on the mobile application (Mobile-based approach). Here's a comparison of these two paths:

#### Server-based Approach

- The model is installed on the server, and the mobile application sends videos to the server for processing and receives the translation results.
- Advantages:
  - Flexibility: Updating the model doesn't require updating the application itself, allowing for easier maintenance and updates.
  - Cross-platform Compatibility: The same model can be used across different platforms (Android, iOS, Web).
  - Data Collection: This approach enables data collection from users, which can be used to improve the model over time.
- Challenges:
  - Requires a good internet connection for sending videos to the server and receiving translation results.
  - Requires a powerful server to handle the incoming video processing requests.

#### Mobile-based Approach

- The model is installed directly on the mobile application.
- Advantages:
  - Practicality: This approach eliminates the need for a powerful server, as the model runs locally on the mobile device.
  - Independence: The application can work offline without relying on an internet connection for processing.
- Challenges:
  - Requires a powerful mobile phone to handle the computational requirements of the model.
  - Updates and maintenance require updating the application itself.

### 8.2. Our Choice: Server-based Approach

After careful consideration, we have chosen the server-based approach for the following reasons:

- Industry Standard: The server-based approach is widely adopted in the industry, offering flexibility, compatibility, and ease of maintenance.
- Scalability: The server-based approach allows for scalable deployment, accommodating multiple clients simultaneously without compromising performance or responsiveness.
- Centralized Processing: By offloading the video processing and prediction tasks to the server backend, the client application can remain lightweight and efficient.
- Data Storage and Analysis: The server's centralized database enables efficient data storage, analysis, and model improvement through user feedback.
- Modularity and Updates: The server backend, hosting the machine learning model, can be updated independently without affecting the client application, allowing for future enhancements and advancements.

The following diagram illustrates the flow of data in the server-based approach:

![Sequence](/images/Sequence-1.png)

## 9. System Specifications

### 9.1 System Architecture

The Sign Language Translator System is built using the following technologies:

- Backend Language: Python
- Backend Framework: Django
- APIs: Django REST Framework, jsonRPC, OpenAI
- Database: SQLlite
- Machine Learning: OpenCV, Torch, TorchVision

The system architecture follows a client-server model, with the client application interacting with the server backend through defined API endpoints.

### 9.2 API Endpoints

The Sign Language Translator System provides the following API endpoints:

- **admin/**: Provides access to the Django admin panel for system administration.
- **worker/**: Exposes the worker API for handling video processing, predictions, and feedback.
- **model/upload**: Allows the client application to upload a video to the server and receive the prediction.

### 9.3 Database Schema

The Sign Language Translator System utilizes a SQLlite database to store videos, predictions, and user feedback. The following diagram illustrates the database schema:

![Database](/images/ERD.png)

## 10. Conclusion

The Sign Language Translator System combines video processing, machine learning, feedback mechanisms, and database storage to create an effective and efficient solution for bridging the gap between sign language gestures and spoken language. The integration with ChatGPT further enhances the grammatical and semantic correctness of the model's output sentences. By adopting a server-based architecture, the system ensures scalability, flexibility, and efficient data collection for continuous improvement. The Sign Language Translator System holds immense potential in facilitating seamless communication for the sign language community, fostering inclusivity and accessibility through the power of technology.
