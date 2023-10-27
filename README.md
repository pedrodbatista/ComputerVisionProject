## Project - Image Captioning
This project focuses on developing a program for generating captions for images. To achieve this, Convolutional Neural Networks (CNNs) are employed to extract image features. Several architectures from Keras, including VGG16, ResNetV2, EfficientNetB2, ImageNet, and InceptionResNetV2, are utilized for feature extraction. The article delves deeper into the performance of each architecture.

## Dataset

The dataset used is the Flickr8k dataset, which consists of images, each paired with five captions. This variability in captions allows the model not to focus on a single, exact description, offering flexibility in learning.

## Model
__Image Feature Extraction with VGG16:__ The model begins with the extraction of image features using the VGG16 architecture, a convolutional neural network (CNN) pretrained on a large dataset called ImageNet. VGG16 has layers that perform convolutions and pooling to extract image features. These layers produce a vector representation (a vector of numbers) that captures the main characteristics of the images.

__Caption Text Processing:__ Image captions are processed on the left side of the model. The caption text is fed into the model, with a maximum input size determined based on caption data. This text is passed through processing layers that reduce its dimensionality and convert it into a vector of size 256. This is done using natural language processing techniques and recurrent neural networks (RNNs), such as Long Short Term Memory (LSTM). These RNNs are effective at understanding word sequences and capturing semantic relationships between them.

__Image Feature Processing:__ On the right side of the model, the features extracted by VGG16 are processed. The number of inputs depends on the feature extraction model used (in the example, VGG16 has 4096 inputs). Similar to text processing, these values are reduced to a vector of size 256.

__Integration of Text and Images:__ The processed information from the left (text) and right (image features) sides is then integrated in the model. This information is summed and processed together to generate an output. This output is a vector whose size is equal to the size of the caption vocabulary. This step is essential for relating image features to caption generation.

__Prediction Weight Generation:__ The model's output is used to predict words in the captions. Each element of the output vector is associated with a word in the vocabulary. The model uses these elements to assign weights to words that best describe the image.



## Initial Results

We initiated training with a baseline VGG16 model, which showed promising results. After 20 epochs of training, we observed a substantial reduction in the categorical cross-entropy loss. However, there was room for improvement as the generated captions did not yet closely align with the images.

To evaluate the quality of captions, we used BLEU (Bilingual Evaluation Understudy), a metric that measures the semantic cohesiveness between the generated and reference captions. For the VGG16 model (20 epochs), we achieved a BLEU-1 score of 0.54 and a BLEU-2 score of 0.32.

## Conclusion
We learned that the choice of CNN architecture can significantly impact performance. VGG16 and ResNet50 performed well in our experiments. The complexity of image captioning remains a challenging research area with much room for further exploration.

Please refer to the full article for more detailed information and insights.


###
- src: Código desenvolvido em python (.ipynb)
- artigo: Documento com a descrição geral do projeto e as bases teóricas do conteúdo de visão computacional e redes neurais
