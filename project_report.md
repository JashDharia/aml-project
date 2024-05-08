# Counteracting Misinformation by AI Using Deepfake Detection Algorithms

## Team
- [Amol Borkar](https://github.com/amolbrkr)
- [Austin Rodrigues](https://github.com/austin-rodrigues)
- [Abhishek Shinde](https://github.com/Abhishek1897)
- [Jash Dharia](https://github.com/JashDharia)

## Introduction
Recent advancements in Generative AI have allowed widespread creation (with tools such as FaceSwap) of Deepfake images and videos that circulate on Social Media. This makes it easy for nefarious agents to use GenAI to impersonate people or cause harm to one's reputation.

Our model can be used as part of a content moderation pipeline to identify if an image uploaded by the user is a deepfake or not. Our primary stakeholders include:

- Social Media Platforms (Content Moderation)
- Law Enforcement

We pursued a conventional deep-learning approach and developed a model from scratch that achieved 84.6% test accuracy.

## Literature Review
In our research, Convolutional Neural Networks (CNNs) emerged as the preferred method for deepfake detection. Various research papers combined CNNs with techniques like attention maps, frequency extractors, etc., for classification. CNNs excel in learning features from images and perform well with limited data.

Considering our primary stakeholders are Social Media Platforms, we aimed for a model with excellent inference speeds for scalable classification of millions of user-generated content uploaded daily. Additionally, the model should provide explanations for classifications.

## Data and Methods
### Data
We primarily worked with image data and utilized publicly available datasets used in deepfake detection research:

- Diverse Fake Face Dataset (msu.edu)
- OpenForensics: In-The-Wild Dataset [V.1.0.0]

Due to limited computing resources, we built a dataset from DFFD, consisting of 10K real images and 6.9K deepfakes.

### Methods
- Preprocessing involved:
  - Face detection using a pre-trained model
  - Center cropping the image around the face to 256x256 resolution
  - Normalization

We experimented with various CNN architectures including AlexNet, LeNet, and ResNet, training them for 40 epochs with a batch size of 75 on 16K images.

### Results
- AlexNet achieved the highest performance with 98% training accuracy and 84.6% test accuracy.
- LeNet followed with a test accuracy of 81%.
- Surprisingly, ResNet with the highest parameter count performed poorly with only 46% accuracy, possibly due to insufficient training data and epochs.

## Discussion
It's crucial for the model to learn deepfake artifacts rather than image features. Models often excel for one technique but fail to generalize to others. While our models serve as an early-stage filter for content moderation, testing on in-the-wild samples from Social Media platforms is necessary.

## Limitations
- Test accuracy reached 84.6%, suggesting room for improvement.
- The model handles only one image size (256x256).
- Generalization ability is uncertain.
- Lack of indication/explanation for why an image is classified as a deepfake.

## Future Work
- Explore augmentation techniques to improve model performance and provide explanations.
- Implement attention maps to highlight forged image parts and enhance model understanding.
- Develop a diverse test set with various deepfake generation techniques for better generalization evaluation.

UI:
![alt text](<WhatsApp Image 2024-05-07 at 23.26.40_5c0f0577.jpg>)

![alt text](<WhatsApp Image 2024-05-07 at 23.26.43_fd24c8c0.jpg>)

![alt text](<WhatsApp Image 2024-05-07 at 23.26.46_3021f3e6.jpg>)

![alt text](<WhatsApp Image 2024-05-07 at 23.26.49_a6e94506.jpg>)