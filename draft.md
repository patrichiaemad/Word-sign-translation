# Sign Language Translator Backend

## 1. Introduction

This report provides an overview of the development and implementation of a sign language translator system using a client-server architecture. The system aims to bridge the communication gap between sign language and spoken language by enabling users to capture sign language gestures through video recording and translating them into written or spoken language.

## 2. System Overview

The sign language translator system consists of a client application, a server backend, and integration with ChatGPT for sentence rewriting. The client application allows users to record sign language gestures, which are then sent to the server for processing and evaluation. The app also enables users to provide feedback on the accuracy of the model's predictions. The server backend processes the videos, evaluates them using a pre-trained machine learning model, and incorporates ChatGPT for sentence rewriting. Relevant data is stored in a database for analysis and model improvement.

The following diagram illustrates the system architecture:

![Architecture](/images/Architecture-1.png)

## 3. Client Application

The client application provides a user-friendly interface for capturing sign language gestures through video recording. It facilitates communication between the user and the server backend. After capturing a video, the client app sends it to the server for processing and evaluation. The app also enables users to provide feedback on the accuracy of the model's predictions.

## 4. Server Backend

The server backend is responsible for processing the received videos, evaluating them using the pre-trained machine learning model, and storing relevant data in a database. Upon receiving a video from the client, the server extracts the relevant features from the video frames and feeds them into the machine learning model for prediction. The server incorporates ChatGPT for sentence rewriting to ensure grammatical and semantic correctness of the translations. The server saves the video, prediction, and any feedback received from users into a database for further analysis and model improvement.

## 5. Integration with ChatGPT for Sentence Rewriting

To enhance the quality and coherence of the translated sentences, the system integrates ChatGPT, a powerful natural language processing model. ChatGPT is utilized to rewrite the output sentences from the machine learning model, ensuring grammatical correctness and semantic accuracy. This integration adds an additional layer of refinement to the translations, making them more linguistically and contextually appropriate.

## 6. Choice of Architecture: Server-Based Approach

### 6.1. Comparison of Approaches

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

### 6.2. Our Choice: Server-based Approach

After careful consideration, we have chosen the server-based approach for the following reasons:

- Industry Standard: The server-based approach is widely adopted in the industry, offering flexibility, compatibility, and ease of maintenance.
- Scalability: The server-based approach allows for scalable deployment, accommodating multiple clients simultaneously without compromising performance or responsiveness.
- Centralized Processing: By offloading the video processing and prediction tasks to the server backend, the client application can remain lightweight and efficient.
- Data Storage and Analysis: The server's centralized database enables efficient data storage, analysis, and model improvement through user feedback.
- Modularity and Updates: The server backend, hosting the machine learning model, can be updated independently without affecting the client application, allowing for future enhancements and advancements.

The following diagram illustrates the flow of data in the server-based approach:

![Sequence](/images/Sequence-1.png)

## 7. System Specifications

### 7.1. Technologies Used

- Backend:
  - Language: Python
  - Framework: Django
  - API: Django REST Framework, jsonRPC, OpenAI
  - Database: PostgreSQL
  - Machine Learning: OpenCV, Torch, TorchVision

### 7.2. Architecture: Client-Server

The sign language translator system follows a client-server architecture. The client application communicates with the server backend through API endpoints to send videos for translation and receive the results. The server processes the videos, evaluates them using the machine learning model, incorporates ChatGPT for sentence rewriting, and stores relevant data in a database. Here's an overview of the API endpoints:

- `/admin`: Django admin panel
- `/worker`: Worker API
- `/model/upload`: Upload a video to the server and receive the translation result

## 8. Conclusion

The sign language translator system, with its client-server architecture and integration with ChatGPT for sentence rewriting, represents a significant advancement in bridging the communication gap between sign language and spoken language. The system offers scalability, centralized processing, efficient data storage and analysis, and the ability to incorporate user feedback for continuous improvement.

By harnessing the power of technology, machine learning, and natural language processing, the system provides a valuable tool for the sign language community, promoting inclusivity, accessibility, and seamless communication between different language modalities. As technology continues to evolve, the sign language translator system serves as a foundation for future developments and innovations in the field.

We envision a more inclusive and connected world, where communication barriers are overcome, and individuals can express themselves freely, regardless of their preferred mode of communication. Through the sign language translator system, we take a significant step towards achieving this vision, offering a transformative solution that empowers individuals and fosters understanding among diverse communities.
