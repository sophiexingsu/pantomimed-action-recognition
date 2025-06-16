# Pantomimed Action Recognition

**⚠️ CONFIDENTIAL - UNPUBLISHED MANUSCRIPT**  
*This repository contains unpublished research materials. Please do not redistribute without permission.*

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Dash](https://img.shields.io/badge/Dash-Interactive-green.svg)](https://dash.plotly.com)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer_Vision-red.svg)](https://opencv.org)

## 🎯 Project Statement

This research project investigates machine learning approaches for recognizing pantomimed actions performed at desktop environments. We leverage existing video recordings of participants performing everyday activities such as taking out pans or brushing teeth, but without the actual objects present. While the original studies focused on different research questions regarding action performance and quality (detailed documentation available [here](https://wustl.box.com/s/xj2805y9dq8e7ccr7a2ms2vdpxnwg2i8)), our dataset presents a unique opportunity to explore object-free action recognition and its potential for improving generalized machine learning capabilities.

## 🎯 Research Goals

### **Goal 1: Action Quality Assessment**
**Objective:** Develop methods to distinguish between high-quality and low-quality action performances.

**Background:** Our dataset includes recordings where participants demonstrated varying levels of effort and accuracy in performing pantomimed actions. Some participants executed actions with high fidelity to real-world movements, while others showed reduced effort or less accurate representations.

**Research Question:** Can we automatically detect and classify the quality of pantomimed action performance?

**Potential Approach:**
- Post-processing analysis using pose tracking from extracted CSV joint data
- Calculating joint movement patterns, smoothness, and trajectory analysis
- Quantifying movement characteristics that correlate with action quality
- Developing metrics for action fidelity assessment using the dashboard's movement percentage calculations
- Leveraging the existing pose estimation pipeline for automated quality scoring

---

### **Goal 2: Object-Free Action Recognition**
**Objective:** Train or adapt existing machine learning models to recognize actions performed without objects.

**Background:** Traditional action recognition systems often rely on object-action interactions. Our pantomimed action dataset provides an opportunity to explore whether machines can recognize actions based solely on human movement patterns, without visual object cues.

**Research Questions:**
- Can machine learning models accurately recognize pantomimed actions without object context?
- Will training on pantomimed action data improve the generalization capabilities of action recognition systems?
- How do object-free action recognition models compare to traditional object-dependent approaches?

**Potential Approaches:**
- Adapting existing action recognition architectures for object-free scenarios using the comprehensive pose data
- Transfer learning from object-based to pantomimed action datasets 
- Developing new feature extraction methods focused on human movement patterns from joint coordinate data
- Comparative analysis of recognition accuracy with and without object context
- Utilizing the existing video processing pipeline and pose estimation infrastructure
- Training on the diverse action categories available in the dataset (gardening, personal care, movement patterns)

---

### **Goal 3: Enhancing SOTA Action Recognition in the Wild**
**Objective:** Improve current state-of-the-art action recognition systems for real-world deployment by leveraging pantomimed action training data.

**Background:** Recent research suggests that training machine learning models on pantomimed action descriptions can significantly improve state-of-the-art (SOTA) action recognition performance. By learning from spatial-temporal relationships inherent in human movement patterns rather than relying on object and contextual cues, models develop more robust and generalizable action understanding.

**Research Questions:**
- Can pantomimed action training data enhance existing SOTA action recognition models for in-the-wild scenarios?
- How does learning spatial-temporal relationships from pantomimed actions compare to object-context dependent learning?
- What performance improvements can be achieved when SOTA models are augmented with pantomimed action training?

**Potential Approaches:**
- Pre-training SOTA action recognition models on pantomimed action datasets
- Multi-modal training combining pantomimed and object-present action data
- Transfer learning from pantomimed to real-world action recognition scenarios
- Developing hybrid architectures that leverage both spatial-temporal and object-context features
- Benchmarking against current SOTA models on standard action recognition datasets

**Challenges:**
- **Domain Gap:** Bridging the difference between controlled pantomimed actions and chaotic real-world scenarios
- **SOTA Baseline Performance:** Current state-of-the-art models already achieve high accuracy on standard benchmarks, making improvement margins narrow
- **Generalization Complexity:** Ensuring that pantomimed action learning transfers effectively to diverse real-world contexts and object variations
- **Computational Efficiency:** Maintaining real-time performance while incorporating additional training complexity
- **Dataset Bias:** Avoiding overfitting to pantomimed action patterns that may not reflect natural movement variations

## 🔬 Research Significance

This project addresses fundamental questions in computer vision and human-computer interaction:

1. **Theoretical Contribution:** Understanding how human actions can be recognized independently of object interactions
2. **Practical Applications:** Improving action recognition systems for scenarios where objects may be occluded, absent, or varied
3. **SOTA Enhancement:** Advancing current state-of-the-art action recognition through spatial-temporal learning from pantomimed data
4. **Methodological Innovation:** Developing quality assessment metrics for human action performance
5. **Dataset Contribution:** Providing a unique large-scale resource for object-free action recognition research
6. **Real-world Impact:** Enabling more robust action recognition systems for deployment in uncontrolled environments

## 📋 Next Steps

1. **Data Preprocessing:** Implement pose tracking and feature extraction pipelines
2. **Quality Metrics Development:** Design and validate action quality assessment algorithms
3. **Model Development:** Adapt and train action recognition models for pantomimed actions
4. **SOTA Enhancement:** Integrate pantomimed action training with state-of-the-art models
5. **Evaluation Framework:** Establish benchmarks and comparison methodologies against current SOTA
6. **Validation Studies:** Conduct experiments to validate all three research goals
7. **Real-world Testing:** Deploy enhanced models in uncontrolled environments

## 📊 Dataset Description

Our dataset consists of video recordings capturing human performance of everyday activities in pantomimed form, collected as part of experiment `exp168_ActionsInfluenceMemory`. The dataset includes diverse everyday activities performed without physical objects present.

### Dataset Structure and Scale

**Directory Structure:**
```
/data/{study}/
├── performance/           # Original video recordings
├── all_pose_data/        # Extracted pose data (CSV format)
└── all_pose_data_visualization/  # Pose estimation videos
```

**Dataset Statistics (Study 2 Example):**
- **Total files:** 8,784
- **Total directories:** 118  
- **Total size:** 3.2GB
- **Video files:** 8,762 MP4 files
- **Participants:** ~118 unique participant IDs
- **File naming convention:** `{participant_id}_{action_description}.mp4`

### Action Categories

The dataset includes a wide variety of pantomimed everyday activities, such as:
- **Gardening activities:** "puts a short plant in the hole", "smooth the dirt around the tall plant", "take a tall plant out of tray"
- **Kitchen activities:** Taking out pans, Turn on the Stove

### Data Processing Pipeline

The project includes a comprehensive data processing and analysis pipeline:

1. **Video Processing:** Original performance videos stored in participant-specific subdirectories
2. **Pose Estimation:** Automated pose detection generating CSV files with joint coordinates
3. **Pose Visualization:** Generated visualization videos showing pose estimation overlays
4. **Movement Analysis:** Computed movement metrics and quality assessments
5. **Interactive Dashboard:** Real-time visualization and analysis interface

### Technical Infrastructure

- **Analysis Platform:** Dash-based interactive dashboard for data exploration
- **Pose Processing:** Automated joint detection and tracking
- **Data Management:** Structured file organization with participant-based directories
- **Quality Metrics:** Movement percentage calculations and smoothness assessments

**Key Dataset Characteristics:**
- Actions performed without physical objects (pantomimed)
- Desktop/controlled environment recordings
- Multiple participants with varying performance quality
- Participants exerted different levels of effort during task execution
- Comprehensive pose tracking data available for each performance
- Standardized file naming and organization system
- 
## 🚀 Getting Started

### Prerequisites

```bash
python >= 3.8
opencv-python
pandas
numpy
dash
plotly
dash-bootstrap-components
```

### Installation

```bash
git clone https://github.com/yourusername/desktop-pantomimed-action-recognition.git
cd desktop-pantomimed-action-recognition
pip install -r requirements.txt
```

### Running the Dashboard

```bash
python app.py
```

Visit `http://localhost:8050` to access the interactive dashboard.

## 📁 Project Structure

```
desktop-pantomimed-action-recognition/
├── README.md
├── requirements.txt
├── app.py                    # Main dashboard application
├── video_utils.py           # Video processing utilities
├── src/
│   ├── data_processing/     # Data preprocessing scripts
│   ├── models/              # ML model implementations
│   ├── evaluation/          # Evaluation and benchmarking
│   └── visualization/       # Additional visualization tools
├── data/                    # Dataset directory (not included in repo)
├── notebooks/               # Jupyter notebooks for analysis
├── docs/                    # Documentation and research papers
└── results/                 # Experimental results and outputs
```

## 🔧 Technical Implementation

### Current Infrastructure

The project leverages a sophisticated technical stack built around the experimental data:

**Core Components:**
- **Interactive Dashboard:** Dash-based web application for real-time data exploration
- **Video Processing Pipeline:** Automated processing of 8,000+ video files across multiple studies
- **Pose Estimation System:** Computer vision pipeline extracting joint coordinates from video data
- **Data Management:** Structured organization supporting multiple studies and participants

**Analysis Capabilities:**
- Real-time video playback with pose overlay visualization
- Joint position tracking and movement timeline analysis
- Movement quality metrics and percentage calculations
- Cross-participant and cross-action comparison tools
- Automated file processing and batch analysis support

### Data Anonymization and Management

A comprehensive data management system has been implemented:
- **File Reorganization:** Systematic renaming from descriptive filenames to anonymized participant codes
- **Codebook Generation:** Automated mapping between original and anonymized filenames
- **Scalable Processing:** Support for multiple study configurations and participant datasets

## 📚 Documentation

*For detailed information about the original study methodology and findings, please refer to the documentation in `/docs/`*

## 🤝 Contributing

This is an active research project. Please contact the research team before contributing.

## 📄 License

This project contains unpublished research materials. All rights reserved.

## 📞 Contact

For questions about this research, please contact:
- Sophie Su - s.sophie@wustl.edu
- Dr.Jeff Zacks- jzacks@wustl.edu

##  Acknowledgments

- Experiment ID: exp168_ActionsInfluenceMemory
- Dynamic Cognition Lab

---

**Note:** This repository contains research code and data processing tools. The actual dataset is not included due to privacy and confidentiality requirements.
