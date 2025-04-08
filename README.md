# 🖼️ Computer Vision Assignment

---

## 🔍 Project Overview

This project explores the application of various computer vision algorithms to detect and compare feature points in high-resolution images. Specifically, it implements:

- **SIFT** (Scale-Invariant Feature Transform)  
- **Shi-Tomasi Corner Detection**  
- **FAST** (Features from Accelerated Segment Test) Corner Detection  

These algorithms are evaluated based on their accuracy, speed, and performance on different image types and viewpoints.

---

## 🧠 Algorithms Implemented

### 1. 🔍 SIFT Feature Matching

- **Purpose**: Detect and match keypoints between two images of the Taj Mahal taken from different viewpoints.
- **Methodology**:
  - Apply SIFT to detect keypoints and compute descriptors.
  - Use Lowe’s ratio test to filter out false matches.
  - Visualize the strong and consistent matches across the images.

#### 📌 Observations:

Adjusting the ratio threshold impacts the quality of SIFT feature matching:

- **Higher thresholds (e.g., 0.80)** yield more matches but may include false positives.
- **Lower thresholds (e.g., 0.60)** reduce false matches but may miss valid keypoints.

This highlights the trade-off between **match quantity and accuracy**.

---

### 2. 🟨 Shi-Tomasi Corner Detection

- **Purpose**: Precisely detect corners in images with clean and distinct features.
- **Methodology**:
  - Resize the image for optimal performance.
  - Apply Shi-Tomasi corner detection using `cv2.goodFeaturesToTrack`.

#### 📌 Observation:

Tuning the parameters of the Shi-Tomasi corner detector demonstrates a clear trade-off between the quantity and quality of detected features:

- Increasing `maxCorners` and reducing `minDistance` results in **more detected corners**, capturing finer details but often introducing **redundant or closely packed points**.
- Using stricter values yields **fewer, well-separated, and more reliable features**, enhancing **precision** and suitability for tasks requiring robust keypoints.

---

### 3. ⚡ FAST Corner Detection

- **Purpose**: Efficiently detect corners in high-resolution images.
- **Methodology**:
  - Apply the FAST algorithm to the image.
  - Detect a large number of corners quickly without computing descriptors.

#### 📌 Observation:

Reducing the circle radius from 6 to 3 improved the clarity of corner point visualization, especially in densely packed areas. Smaller markers helped distinguish closely located keypoints without overlap, enhancing interpretability. In contrast, larger circles made keypoints more prominent but often obscured nearby features.

---

## 🖼️ Sample Output Screenshots

The visual outputs (detected keypoints and matches) can be found inside the Jupyter notebook or the exported PDF report.

---

## 📊 Output Comparison

| Algorithm       | Speed         | Accuracy           | High-Res Compatible | Corners/Matches     |
|-----------------|---------------|--------------------|----------------------|----------------------|
| **FAST**        | 🚀 Very Fast   | ⚠️ Medium           | ✅ Yes               | ~800                |
| **Shi-Tomasi**  | 🐢 Slower      | ✅ High             | ⚠️ Needs Resizing    | ~100                |
| **SIFT**        | ⚡ Moderate    | ✅✅ Very High       | ✅ Yes               | Matched Points      |

---

## 🧪 Conclusion

This project demonstrates the practical effectiveness of various feature detection and matching techniques in computer vision, each with its own trade-offs:

- 🔍 **SIFT** is highly accurate and robust to changes in scale, rotation, and viewpoint—making it ideal for feature matching between different image perspectives.
- 🟨 **Shi-Tomasi Corner Detection** offers precise and reliable corner detection with tunable parameters for different levels of detail, though it may require resizing for high-resolution inputs.
- ⚡ **FAST** is optimized for speed and performs well on high-resolution images, but may produce less stable or accurate corners in complex scenes.

Choosing the right algorithm depends on your application's specific needs — whether you require **real-time speed**, **robust feature matching**, or **high precision** in corner detection. This understanding is essential for building reliable and efficient computer vision systems.

---

## 🚀 How to Run

Clone the repository and navigate to the project folder:

```bash
git clone https://github.com/Priyank2310/Computer-Vision-Assignment.git
cd Computer-Vision-Assignment
