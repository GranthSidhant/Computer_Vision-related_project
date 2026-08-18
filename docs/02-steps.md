# Steps

## Step 1 — Extract Frames

Animal videos are collected and frames are extracted from the videos using a Python script with FFmpeg.

The extracted frames are saved as image files.

## Step 2 — Label Images

The extracted images are uploaded to **Label Studio**.

Each image is labeled by drawing a bounding box around the animal and assigning the appropriate class.

Current classes include:

- Jaguar
- Cheetah
- Leopard
- Tiger

## Step 3 — Export Labeled Images

After the images are labeled, the labeled data is exported from Label Studio.

The exported data will be used for the next stage of the project.

---

## Current Progress

Currently, the project is working on **Step 2 — Label Images**.

The immediate task is to continue extracting frames from animal videos and labeling the extracted images in Label Studio.