# Project Overview

## 1. Introduction

This project is a **computer vision and object detection project** being developed as part of my first semester of the **Master of Computer Applications (MCA)** program.

The main idea is to build a system that can detect wild animals from images or video and, in the future, alert people when a potentially dangerous wild animal is detected.

In simple terms, the goal is to teach a computer to look at an image or video frame and answer:

> **"Is there a wild animal here, and if so, which animal is it?"**

The project will initially focus on wild animals from the cat family that can look similar to each other, such as:

- Jaguar
- Cheetah
- Leopard
- Tiger

These animals are useful for this project because distinguishing between visually similar species can be challenging for a computer vision model.

---

## 2. Problem Statement

Wild animals can sometimes enter areas where humans live or work. Detecting such animals early could help provide people with a warning and potentially improve safety.

The purpose of this project is to explore whether a computer vision model can automatically identify wild animals from images or video.

The long-term goal is to develop a system that can:

1. Receive an image or video stream.
2. Detect whether a wild animal is present.
3. Identify the detected animal.
4. Provide an alert when a relevant animal is detected.

The current work is focused on the first part of this larger system: **creating a good dataset and training an object detection model**.

---

## 3. Project Goal

The primary goal is to train an object detection model capable of detecting and distinguishing selected wild animal species.

The project will use **YOLO (You Only Look Once)** for object detection.

The initial focus is on building a dataset containing images of visually similar wild cat species and using this dataset to train and evaluate the model.

---

## 4. Initial Animal Classes

The initial dataset is focused on the following animal classes:

| Class | Description |
|---|---|
| Jaguar | A large wild cat found mainly in the Americas. |
| Cheetah | A fast-running wild cat known for its speed. |
| Leopard | A large wild cat with a spotted coat and wide geographical distribution. |
| Tiger | A large striped wild cat found mainly in Asia. |

The list of classes may change as the project develops.

Additional species may be added later if they are relevant to the project's objectives and sufficient training data can be collected.

---

## 5. Computer Vision Approach

The project uses **object detection** rather than simple image classification.

Image classification answers a question such as:

> "What animal is in this image?"

Object detection goes one step further. It attempts to answer:

> "What animal is present, and where is it located in the image?"

This is important for the planned application because the system will eventually need to identify animals within video frames and potentially trigger an alert when an animal is detected.

The YOLO model will be trained using labeled images containing bounding boxes around the animals.

---

## 6. Current Data Preparation Workflow

The current project workflow begins with animal videos.

Instead of manually collecting every image, videos are used as a source of training images. A Python script is used to extract I-frames from these videos using **FFmpeg**.

The current workflow is:

```text
Animal Videos
      |
      v
FFmpeg I-Frame Extraction
      |
      v
Extracted I-Frames
      |
      v
Image Selection
      |
      v
Label Studio
      |
      v
Draw Bounding Boxes
      |
      v
Labeled Dataset
      |
      v
YOLO Dataset Format