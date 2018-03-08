# Creating Image Recognition Applications

This repository has been created to provide reference materials for Tech(K)NOW workshop and covers topic of "Building AI applications using Microsoft Cognitive Services".

## Overview

Cat or Dog? Picasso or Dali?

In the first part of this hands-on workshop you will learn how to create, train and test and evaluate image classification models using Microsoft Custom Vision Service. You would be able to build your own image classifier using only a handful of labeled images (provided at the workshop, or your own).
After that we will look at how you could use such classification models within your chatbot, web application or an iOS application.

Pre-requisites for the workshop:

- [Required] Microsoft Live ID account (https://account.microsoft.com/account)
- [Optional, Console application] .NET Core SDK, Visual Studio Code IDE
- [Optional, Web application] Node.js environment, Visual Studio Code IDE
- [Optional, iOS application] XCode 9 IDE

There are different approaches how image classifiers can be built and used within your applications, be it a website or a mobile application.

One of the option could be using APIs provided by cloud providers - all major cloud providers (Microsoft, Google, Amazon) provide such services now. In the case of using APIs, at a high level, you'd need to integrate your application with REST APIs provided by a cloud platform of choice, provide an image, call an API and process the results returned to you. Often, it will respond with a imformation about the content of the image provided and will classify it into various categories (i.e. "outdoor", "car", "animal") with corresponding confidence scores.

The main drawback here is that if you actually want to build a classifier that only should classify all the images between, let's say, 2 given categories - "cats" / "dogs", or detect an painter (among 5 or 10) who's likely created a specific artwork, such general purpose APIs will not be useful.

if you were to create such classifier from scratch you're very likely end up using  deep learning neural networks (convolutional neural networks, in particular). A variety of DL frameworks (TensorFlow, CNTK, Keras, and others) can help you to do that, as well as accelerate the process, however that would require a good understanding of the ML / DL fundamentals, as well as Python coding skills to implement those.

When your custom model is trained and tested you can then deploy it to the cloud environment and access and get predictions from your web application. If your application is an iOS app, then you might want to look at CoreML franework introduced by Apple in summer 2017 to bring your trained models into your iOS applications, by running those directly on the device. Similarly, Android devices support models in TensorFlow format that can be run directly on the device for real-time / offline image classification.

Another option could be to use [Microsoft Custom Vision Service](customvision.ai), that can help developers without ML background to start buiding custom classifiers based on custom (= your own) set of images.

The final version of the Custom Vision model can be exposed to your web application as an API endpoint, or can also be exported to the CoreML format for iOS applications, as well as the TensorFlow format to be used in Android devices.

In this workshop we will cover the latter option and demonstrate how you can build an application (console, web, mobile) that can recognise painters' artwork and suggest who might be a painter of the sample image the application has never seen before.

*Note:* Images used in this workshop may be subject to copyright, and they are used for training purposes only.