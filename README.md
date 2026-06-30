# Brain-Tumor-Detection
CNN-based Brain Tumor Detection from MRI scans, classifying images as glioma, meningioma, pituitary tumor, or normal. Trained on 21,672 MRI images (150×150px, normalized) using an 8-layer convolutional architecture with dropout and softmax output — a fast, non-invasive AI aid for tumor screening.

<u>Introduction</u>

Brain tumors are one of the most serious and life-threatening diseases. Traditional methods of brain tumor detection, such as MRI scans and biopsies, can be invasive, time-consuming, and expensive. Artificial Intelligence (AI) offers a promising alternative for brain tumor detection.

AI-Based Brain Tumor Detection

AI-based brain tumor detection involves using machine learning algorithms to analyze medical images, such as MRI scans, to identify and classify brain tumors.  Once trained, AI algorithms can be used to detect brain tumors in new patients. AI algorithms can also be used to track the progression of brain tumors over time, helping doctors to monitor treatment and make informed decisions.


IMAGE ACQUISITION

1.	We have a dataset of brain MRI images that is structured into two main subfolders:
2.	Tumor Images Subfolder:
a.	This subfolder contains images of patients diagnosed with brain tumors. It is further divided into three subcategories based on the type of tumor:
i.	Glioma Tumor: A collection of MRI images showing glioma tumors.
ii.	Pituitary Tumor: Images showing pituitary tumors.
iii.	Meningioma Tumor: Images showing meningioma tumors.
3.	Normal Images Subfolder:
a.	This subfolder contains MRI images of patients with no tumors.
 


Dataset Splitting:
The dataset is split into two parts:
Training Set (80%): The majority of the data is used to train the Convolutional Neural Network (CNN) model. This ensures that the model learns to identify patterns and features in the images that distinguish between the different categories.
Testing Set (20%): A smaller portion of the data is set aside to evaluate the model’s performance. This set is used to test the model after training to see how well it generalizes to new, unseen data.





The brain tumor dataset
Dataset comprises:
●	Normal Images: 3,066 brain MRI images of patients without tumors.
●	Tumor Images: 18,606 brain MRI images, divided into three categories:
○	Glioma Tumor: 6,307 images
○	Meningioma Tumor: 6,391 images
○	Pituitary Tumor: 5,908 images
This results in a total of 21,672 images, which are used for training and testing a Convolutional Neural Network (CNN) model.






Data preprocessing

In the data preprocessing phase, several steps are performed to prepare the brain MRI images for input into a deep learning model. Here's a more detailed explanation:
1. Resizing:
Process: Each image in the dataset is resized to 150 x 150 pixels.
Reason: Deep learning models, especially Convolutional Neural Networks (CNNs), require a consistent input size. Resizing the images to a smaller, uniform size reduces the computational load, allowing the model to train more efficiently and quickly. Smaller images also help in reducing the complexity of the model, which can be beneficial when working with large datasets.
2. Normalization:
Process: After resizing, the pixel values of the images are normalized. This typically involves scaling the pixel values to a range between 0 and 1 or adjusting them to have a mean of 0 and a standard deviation of 1.
Reason: Normalization is crucial for deep learning models because it helps in stabilizing the learning process. By ensuring that the pixel values are within a specific range, the model's gradient descent algorithm can converge more quickly, leading to faster and more stable learning. Normalized data also helps prevent issues related to vanishing or exploding gradients.
3. Shuffling:
Process: The images are randomly shuffled before being fed into the model.
Reason: Shuffling is an important step in ensuring that the model learns effectively from the data. If the images were fed into the model in a sequential order (e.g., all glioma images followed by all meningioma images), the model might not generalize well and could develop a bias towards the most recent category of images it has seen. Shuffling ensures that each batch of data the model sees contains a random mix of different types of images, which improves the model's ability to learn distinguishing features across all categories.
   



PROPOSED CNN ARCHITECTURE

Convolutional Neural Networks (CNNs) are specialized deep learning models designed for processing and classifying images. They use convolutional layers to detect local patterns, such as edges and textures, through the application of filters that produce feature maps. To capture complex patterns, CNNs incorporate activation functions like ReLU, which introduce non-linearity. Pooling layers reduce the spatial dimensions of feature maps, decreasing computational load and enhancing generalization by making the network more invariant to small translations. Fully connected layers then combine the extracted features to make final classifications or predictions. The output layer, often using a softmax function, provides the classification result by converting raw scores into probabilities. CNNs are highly effective due to their ability to automatically learn relevant features from images, reducing the need for manual feature engineering, and capturing hierarchical patterns. They are widely used in applications such as object detection, face recognition, and medical image analysis. Advanced techniques like transfer learning, which leverages pre-trained models for new tasks, and data augmentation, which enhances the training dataset, further improve CNN performance.

Architecture of the Proposed CNN Model

The proposed CNN model is structured to efficiently handle image classification tasks through a two-stage process: feature extraction and classification. It starts with 8 convolutional layers, each utilizing a 3×3 filter to detect essential features like edges and textures from the input image. These convolutional layers are followed by max pooling layers that reduce the spatial dimensions of the feature maps while preserving critical features. This reduction not only decreases the computational load 
   

   
but also helps in mitigating overfitting and noise. After feature extraction, the ReLU (Rectified Linear Unit) activation function is applied to introduce non-linearity into the model, which enhances its ability to learn complex patterns and accelerates training by avoiding vanishing gradient issues. To further combat overfitting, a dropout layer randomly deactivates a portion of neurons during training, encouraging the network to generalize better. In the classification stage, the model features 3 fully connected (dense) layers, which integrate the extracted features to make predictions. The final classification is performed using the softmax activation function, which converts the output scores into probabilities for each class, ensuring a clear and accurate classification of the image into one of the n categories.

