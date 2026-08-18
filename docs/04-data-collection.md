# Data Collection and I-Frame Extraction

## 1. Purpose

The first step in creating the dataset is to collect useful images of wild animals.

For this project, animal videos are used as a source of images. Instead of manually taking screenshots from videos, **FFmpeg** is used to automatically extract I-frames from the videos.

An I-frame is a video frame that can be decoded independently and contains a complete image. Extracting I-frames provides a convenient way to obtain representative frames from a video without saving every single frame.

The extracted images will later be reviewed and selected for labeling in **Label Studio**.

---

## 2. Data Collection Workflow

The current workflow is:

```text
Animal Videos
      |
      v
FFmpeg
      |
      v
Extract I-Frames
      |
      v
Review / Select Images
      |
      v
Label Studio
      |
      v
Draw Bounding Boxes
      |
      v
Export Labeled Dataset
      |
      v
YOLO Dataset