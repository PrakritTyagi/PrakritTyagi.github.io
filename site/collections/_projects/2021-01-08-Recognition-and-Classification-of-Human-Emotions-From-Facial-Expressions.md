---
date: 2021-01-08 06:20:35 +0300
title: Recognition and Classification of Human Emotions From Facial Expressions
subtitle: AI and Human Emotions
image: '/images/Emotions/cover_facial_recog.png'
---

## Motivation

Facial emotion recognition (FER) is a key field with applications in healthcare, human interactions, and human-machine interactions. It plays a vital role in predicting psychological states during social interactions. Machines that recognize emotions from facial expressions have great potential for improving user and customer satisfaction by understanding mental states. Although emotion recognition from speech is also important, facial expressions are often the first indicators of emotion, especially when verbal cues are absent. With communication being largely visual (55%), vision-based FER techniques are essential for identifying emotions.

## Proposed Algorithm and Model Implementation

This project introduces a facial expression classification algorithm that utilizes a shallow neural network architecture to recognize and categorize human emotions. The system leverages images from the AffectNet dataset to classify eight primary emotions: neutral, happiness, sadness, surprise, fear, disgust, anger, and contempt. The whole dataset is batchlized to prevent memory overshoot. At each iteration of batches, the model is trained through forward-pass and backpropagation via Mean Cross Entropy loss function. Labels are predicted on a given image with argmax. After training the model on AffectNet, the algorithm is implemented in real-time for emotion classification, in conjunction with the OpenCV facial detection algorithm. We also compare the performance of this algorithm with both a baseline neural network and a pre-trained ResNet18 model.

![CNN Model](/images/Emotions/model.png){: width="900" height="675"}
<!-- markdownlint-disable-next-line MD033 -->
<p style="text-align: center; font-size: 0.7em; color: gray; margin-top: 0; margin-bottom: 40px;">Baseline CNN with 5 Convolutional layer & Fully Connected Layer.</p>

## Dataset

In this work, we used a benchmark dataset: [Affectnet](http://mohammadmahoor.com/affectnet/) to train our convolutional neural network.

![MAPF results](/images/Emotions/num_classes_train.png){: width="400"}

## Live Demo

The video below demonstrates the real-time emotion recognition system in action.

<!-- <iframe width="560" height="315" src="https://www.youtube.com/embed/1X2e3e3JN5M" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> -->

![MAPF video](/images/Emotions/live_demo.gif){: width="800"}

## References

Read Full Report [Here](/files//24787_Final_Report_Human_Emotion_Classification.pdf) !!!
