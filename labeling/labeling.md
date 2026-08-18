# Image Labeling

## 1. Overview

After extracting the frames from the animal videos, the next step is to label the images using **Label Studio**.

The purpose of labeling is to identify the animal in each image and mark its location using a bounding box.

---

## 2. Current Process

The current process is:

```text
Animal Video
      |
      v
Extract Frames
      |
      v
Select Images
      |
      v
Upload Images to Label Studio
      |
      v
Draw Bounding Box
      |
      v
Select Animal Class
      |
      v
Save Annotation