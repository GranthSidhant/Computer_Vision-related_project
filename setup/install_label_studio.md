Yes — this one has the same problem. The `\n`, broken URL, and single backticks around code blocks are not valid raw Markdown formatting for what you want.

Copy the following exactly as-is into:

`setup/install_label_studio.md`

Markdown

# Label Studio Installation and Setup

## Purpose

This document contains the commands used to create a dedicated Anaconda environment, install Label Studio, and start the Label Studio application.

Label Studio is being used in this project to **label/annotate animal images** before preparing the dataset for YOLO object detection training.

---

## Reference Tutorial

The installation and setup steps were learned by following the relevant part of the following tutorial:

**YouTube:** [YOLO Object Detection Tutorial]([https://www.youtube.com/watch?v=r0RspiLG260](https://www.youtube.com/watch?v=r0RspiLG260))

The tutorial was used as a reference for downloading and setting up the required software and for understanding the Label Studio workflow.

> The commands below document the setup used for this project. They are maintained separately so that the environment can be recreated later if needed.

---

## Requirements

Before installing Label Studio, make sure the following are available:

- Anaconda or Miniconda

- Anaconda Prompt

- Internet connection

- Windows operating system

---

## Installation

Open **Anaconda Prompt** and run the following commands one at a time.

### 1. Create a Conda Environment

```bash

conda create -n label-studio-env python=3.10 -y

This creates a new Conda environment named `label-studio-env` using Python 3.10.

The environment keeps the Label Studio installation separate from the system Python installation.

### 2. Activate the Environment

Bash

conda activate label-studio-env

This activates the `label-studio-env` environment.

The remaining installation commands should be executed after activating this environment.

### 3. Install Label Studio

Bash

pip install label-studio

This installs Label Studio and its required Python dependencies inside the `label-studio-env` environment.

### 4. Start Label Studio

Bash

label-studio start

This starts the Label Studio application locally.

After starting, Label Studio should provide a local web address that can be opened in a browser.

### Complete Command Sequence

For convenience, the complete setup sequence is:

Bash

conda create -n label-studio-env python=3.10 -y

conda activate label-studio-env

pip install label-studio

label-studio start

Run each command in Anaconda Prompt.

### Environment Information

| Item                | Value            |
| ------------------- | ---------------- |
| Environment Manager | Anaconda / Conda |
| Environment Name    | label-studio-env |
| Python Version      | 3.10             |
| Annotation Tool     | Label Studio     |
| Installation Method | pip              |
| Terminal            | Anaconda Prompt  |
| Operating System    | Windows          |

### Usage in This Project

Label Studio is used to annotate the video frames extracted from animal videos.

The overall workflow is:

Animal Video

|

v

Python Frame Extraction

|

v

Extracted Images

|

v

Label Studio

|

v

Draw Bounding Boxes Around Animals

|

v

Export Labeled Dataset

|

v

Prepare Dataset for YOLO

|

v

YOLO Model Training

The initial labeling work focuses on wild cat species such as:

* Jaguar

* Cheetah

* Leopard

* Tiger

These animals are being selected because some of them can have visually similar characteristics, making them useful classes for testing object detection and classification performance.

### Starting Label Studio Again

If Label Studio has been closed, there is no need to reinstall it.

Open Anaconda Prompt and activate the environment:

Bash

conda activate label-studio-env

Then start Label Studio:

Bash

label-studio start

### Checking the Environment

To verify that the correct Conda environment is active, run:

Bash

conda env list

The active environment will be marked with `*`.

Example:

# conda environments:

#

base C:\Users\Username\anaconda3

label-studio-env * C:\Users\Username\anaconda3\envs\label-studio-env

### Notes

* The Conda environment should be activated before running Label Studio.

* The environment name used for this project is `label-studio-env`.

* Python 3.10 is used for this Label Studio environment.

* Label Studio is installed using `pip`.

* The environment setup is documented so that the project environment can be recreated later.

* The actual dataset and labeling process are documented separately.

### Related Documentation

* `docs/01-project-overview.md` — Overall project description and goals

* `docs/02-software-and-setup.md` — Software and environment setup

* `docs/03-dataset.md` — Dataset organization and statistics

* `docs/04-data-collection.md` — Video collection and I-frame extraction

* `setup/install_label_studio.md` — Label Studio installation commands

### Source

The initial Label Studio setup was learned by following the relevant part of this tutorial:

YouTube: YOLO Object Detection Tutorial

The tutorial is used as a learning and reference resource. This repository documents the actual setup and workflow used in this project.

### One structural change I'd make

Since you now have **installation instructions for individual tools**, I think your repository should evolve slightly:

```text

wild-animal-detection/

│

├── README.md

│

├── docs/

│ ├── 01-project-overview.md

│ ├── 02-software-and-setup.md

│ ├── 03-dataset.md

│ └── 04-data-collection.md

│

├── setup/

│ └── install_label_studio.md

│

├── src/

│ └── data/

│ └── extract_i_frames.py

│

├── dataset/

├── experiments/

└── results/

This gives us a nice separation:

`docs/` = explains the project and methodology

`setup/` = commands needed to install/configure things

`src/` = actual project code

`dataset/` = project data

`experiments/` = experiments and tests

`results/` = model/results/output

That's a structure I'd be comfortable keeping as the project grows.
