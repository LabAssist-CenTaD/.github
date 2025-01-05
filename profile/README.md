# LabAssist

LabAssist is an AI-powered laboratory assistant designed to help students perform chemistry experiments more accurately while reducing teacher workload. The system leverages cutting-edge computer vision techniques to detect and provide real-time feedback on common mistakes during laboratory procedures, with an initial focus on titration experiments.

## 🔬 Problem Statement

In school laboratories, teachers face significant challenges:

- **Overwhelming Class Sizes**: Monitoring over 30 students simultaneously during experiments is demanding.
- **Complexity of Procedures**: Each experiment requires attention to unique steps, making it hard to track errors across multiple activities.
- **Subtle Procedural Mistakes**: Errors like neglecting to place a white tile under a conical flask often go unnoticed.
- **Safety Compliance**: Ensuring all students adhere to safety protocols while providing individual attention is challenging.

## 🎯 Key Features

### Real-time Error Detection
- Utilises advanced AI to identify and categorise mistakes during laboratory experiments.

### Dual AI System
- **Object Detection**: Powered by YOLOv10m, recognises laboratory equipment and safety gear.
- **Action Detection**: Employs X3D_M to analyse procedural execution (e.g., swirling technique).

### Comprehensive UI
- **Timeline View**: Chronologically tracks errors.
- **Summary Dashboard**: Offers a performance overview.
- **Error Navigation**: One-click access to specific error instances in videos.

## 🤖 Technical Architecture

### Backend

- **Object Detection Model**: 
  - Built on YOLOv10m architecture.
  - Trained on a dataset augmented to 22,500 images.
  - Detects 9 key objects: beaker, burette, pipette, conical flask, volumetric flask, funnel, white tile, face, and lab goggles.

- **Action Detection Model**:
  - Based on PyTorchVideo’s X3D_M.
  - Processes temporal data for sequential action detection.

### Frontend

- Built with **React**.
- Features an interactive timeline and summary dashboard.
- Optimised for user-friendly video playback and analysis.

### Performance Metrics

- **Object Detection**: Achieved >90% mAP50 across all classes, with standout accuracies of 99% for conical flasks and 95% for burettes.
- **Action Detection**: Averaged 95% accuracy across swirling techniques (correct, incorrect, none).

## 📊 Experimental Results

### Object Detection
- Improved reliability by expanding object classes from 4 to 9.
- Reduced false positives and negatives, especially for visually similar apparatus.

### Action Detection
- Boosting technique enhanced accuracy by chaining object detection outputs as preprocessing for action detection.
- Reduced processing time while maintaining high prediction reliability.

### Multiprocessing
- Implemented multiprocessing for concurrent video loading and inference.
- Achieved a 7.7x improvement in processing speed.

### User Interface
- Transitioned from a desktop application to a web-based platform.
- Accessible via any device, eliminating setup complexities.
- Highlights errors on a timeline and provides a checklist for performance review.

## 🚀 Future Development

- Expanding detection capabilities to other experiments like separation techniques and salt preparation.
- Optimising mobile compatibility for seamless video uploads.
- Scaling backend to handle higher workloads for large-scale deployment.

## 🔗 References

1. Chen, L., Chen, P., & Lin, Z. (2020). Artificial intelligence in education: A review. *IEEE Access, 8*, 75264–75278. https://doi.org/10.1109/ACCESS.2020.2988510
2. Ling, X., Yang, J., Liang, J., Zhu, H., & Sun, H. (2022). A Deep-Learning Based Method for Analysis of Students’ Attention in Offline Class. *Electronics, 11*(17), 2663. https://doi.org/10.3390/electronics11172663
3. Gligorea, I., et al. (2023). Adaptive Learning Using Artificial Intelligence in e-Learning: A Literature Review. *Education Sciences, 13*(12), 1216. https://doi.org/10.3390/educsci13121216
