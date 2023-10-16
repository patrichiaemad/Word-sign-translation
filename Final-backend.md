# Graduation project Backend

## 1. Comparsion of different architectures

We had the option between 2 paths:

1. Install the model on the server and use it as an API
2. Install the model directly on the mobile application

### Comparison of the 2 paths

- **1st path**: The model is installed on the server and the mobile application sends the videos to the server and receives the result.
  - This path is the most used in the industry because it is more flexible and allows to update the model without having to update the application. However, this path requires a good internet connection and a powerful server to handle the requests.
  - This can allow us to use the same model for different platforms (Android, iOS, Web, ...).
  - This can allow us to collect data from the users and improve the model.

- **2nd path**: The model is installed directly on the mobile application.
  - This path is the most used in the academic field because it is more practical and does not require a powerful server. However, this path requires a powerful mobile phone to handle the model.

### Our choice

We chose the **1st** path because it is the most used in the industry and it is more flexible in term of updates, maintenance and data collection.

## 2. Specifications

### 2.1. Technologies

- **Backend**:
  - **Language**: Python
  - **Framework**: Django
  - **API**: Django REST Framework, jsonRPC, openAI
  - **Database**: PostgreSQL
  - **Machine Learning**: OpenCV, Torch, TorchVision

### 2.2. Architecture [Client-Server]

> Architecture diagram and sequence diagram

![Architecture](/images/Architecture-1.png)
![Sequence](/images/Sequence-1.png)
![ERD](/images/ERD.png)

### 2.3. API

#### 2.3.1. API endpoints

- **admin/**: Django admin panel
- **worker/**: Worker API
- **model/upload**: Upload a video to the server and return the prediction
