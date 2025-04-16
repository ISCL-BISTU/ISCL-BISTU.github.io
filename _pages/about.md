---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<!-- <span class='anchor' id='about-me'></span> -->

# 👨‍🔬 Introduction
The Intelligent Sensing and Computing Laboratory is dedicated to advancing the field of intelligent detection and information processing through innovative research and cutting-edge technology. Rooted in the robust theoretical foundations of deep learning and multimodal large models, our laboratory spearheads efforts in developing state-of-the-art methodologies and applications.
Our research portfolio spans a diverse range of areas including target detection, pedestrian re-identification, behavior analysis, and multimodal intelligent human-machine interaction. In addition, we explore advanced techniques in infrared image processing, optical fiber signal intelligent detection, and biomedical signal analysis. By integrating these disciplines, we aim to create intelligent systems that can efficiently and accurately interpret complex data from various sources.
Committed to pushing the boundaries of artificial intelligence, our laboratory focuses on both theoretical research and practical implementations. We strive to address real-world challenges by developing novel algorithms and systems, fostering an environment of interdisciplinary collaboration, and contributing to the evolution of intelligent sensing and computing technologies.

# 💻 Dataset 

  **Mouse pose dataset from open-field test (MPD-OFT)** \\ 
  The MPD-OFT dataset employs a top–down perspective. The closed-circuit television (CCTV) cameras are set
  at different heights to accommodate different sizes and shapes
  of open fields, such as small rectangular open fields, spacious
  circular water mazes, or Y-shaped and cross mazes, ensuring
  full coverage of the experimental areas. As shown in the figure,
  (a) Top-view open-field conditions aimed to record the natural behavior of the mouse in system setup diagram. (b) and
  (c) Rectangular open-field images. (d)–(f) Cross-maze open-field images.
  (g) Morris circle water maze image. (h) Y-maze image.

<!-- <img src="images/fig3.png" alt="fig3" style="display: block; margin: 0 auto;" width="80%"> -->
<img src="images/fig3.png" alt="fig3" style="display: block; margin: 0 auto;" width="70%">

**Features**
  - Diversity of Open Field
  - Multiheight and Multiresolution Camera Settings
  - Open Scene With Background

The MPD-OFT dataset includes a total of 14,586 images. These images span multiple resolutions (e.g., 640×480, 1280×960, 1920×1080) and were collected at distances ranging from 60 cm to 180 cm between camera and subject. Scene-specific image counts range from a few hundred to over 2,700, ensuring broad coverage and high diversity to support robust and generalizable pose estimation models.
<!-- <img src="images/tab1.png" alt="tab1" style="display: block; margin: 0 auto;" width="60%"> -->
<img src="images/tab1.png" alt="tab1" style="display: block; margin: 0 auto;" width="55%">
Each image was annotated with seven keypoints—snout, left ear, right ear, body center, tail base, left hip, and right hip—along with a bounding box tightly enclosing the head and torso.
<div style="display: flex; justify-content: center; gap: 20px; margin-top: 20px;">
  <img src="images/fig4.png" alt="Image 1" style="width: 35%;">
  <img src="images/fig5.png" alt="Image 2" style="width: 45%;">
</div>

The annotation files are provided in two formats. The .txt files follow the YOLO format, containing annotations in the structure:
{class, Cx, Cy, W, H, K1_x, K1_y, K1_v, ..., K7_x, K7_y, K7_v},
where Cx, Cy, W, and H represent the normalized center coordinates, width, and height of the bounding box, and K1 to K7 denote the coordinates and visibility of the seven keypoints.

The .json files are the original annotations generated using LabelMe. The label mouse_rect defines the top-left and bottom-right corners of the bounding box, while segmentation provides the segmentation mask of the mouse. 

Labels 0 to 6 represent the coordinates of the seven keypoints: the snout, right ear, right hip, tail base, left hip, left ear, and body center, respectively.



# 📝 Related Paper 

  [YOLO-MousePose: A Novel Framework and Dataset for Mouse Pose Estimation From a Top–Down View](https://ieeexplore.ieee.org/document/10929680). 
  Mingxin Yu, Hao Dong, Rui You, Shengjun Liang, Qihao Zhang, Yiyuan Ge, Mingwei Lin, Zeshui Xu. Which has been accepted by IEEE Transactions on Instrumentation and Measurement,
<!-- <div class='paper-box' style="position: relative;">
  <img src="images/fig7.png" alt="sym" style="width: 90%; height: auto; display: block;">
  <div class="badge" style="
    position: absolute;
    top: 10px;
    left: 10px;
    background: #ffcc00;
    padding: 4px 8px;
    font-weight: bold;
    border-radius: 4px;
    font-size: 14px;
  ">
    TIM 2025
  </div>
  <div class='paper-box-text' markdown="1">
  </div>
</div> -->
<div class='paper-box' style="position: relative; width: fit-content; margin: 0 auto;">
  <img src="images/fig7.png" alt="sym" style="width: 90%; height: auto; display: block;">
  <div class="badge" style="
    position: absolute;
    top: 10px;
    left: 10px;
    background: #ffcc00;
    padding: 4px 8px;
    font-weight: bold;
    border-radius: 4px;
    font-size: 14px;
  ">
    TIM 2025
  </div>
</div>
**Abstract**
    The top–down view is particularly advantageous
    for mouse pose estimation as it provides a clear, unobstructed
    perspective of the body of the mouse, enabling more accurate
    behavioral analysis. However, physiological differences make
    existing human pose estimation algorithms less applicable to
    mice, and the lack of open-source datasets hinders algorithmic
    progress in this field. To address these challenges, we present
    YOLO-MousePose, an enhanced version of the YOLO-Pose
    specifically designed for mouse pose estimation from a top–down
    view. We also construct the mouse pose dataset from open-field
    test (MPD-OFT), which includes 14,586 annotated images, with
    each image containing a single mouse. YOLO-MousePose uses
    a regression-based approach for precise keypoint localization,
    simultaneously detecting the bounding box and 2-D pose of the
    mouse in a single forward pass. The model features a fusion
    channel-specialized encoder (FCSE) module that selectively fuses
    multiscale feature information, improving sensitivity to small
    objects and effectively addressing the challenges of small object
    detection and keypoint localization. Additionally, we optimize the
    keypoint localization loss function to accelerate convergence and
    prevent performance degradation. On our open-source dataset,
    YOLO-MousePose achieves a root-mean-square error (RMSE)
    of 8.41 mm, a mean absolute error (MAE) of 5.52 mm, and an
    average percentage of correct keypoints (PCKs) score of 96.1%
    at a 0.1 threshold, matching the accuracy of the previous state
    of-the-art (SOTA) algorithm GM-SCENet while using only 28%
    of its parameters. The dataset and code are publicly available at
    https://github.com/bujihao/YOLO-MousePose.


<!-- <div class='paper-box'><div class='paper-box-image'><div><div class="badge">TIM 2025</div><img src='images/fig7.png' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

[YOLO-MousePose: A Novel Framework and Dataset for Mouse Pose Estimation From a Top–Down View](https://ieeexplore.ieee.org/document/10929680)\\
Mingxin Yu, Hao Dong, Rui You, Shengjun Liang, Qihao Zhang, Yiyuan Ge, Mingwei Lin，Zeshui Xu\\
**Abstract**
The top–down view is particularly advantageous
for mouse pose estimation as it provides a clear, unobstructed
perspective of the body of the mouse, enabling more accurate
behavioral analysis. However, physiological differences make
existing human pose estimation algorithms less applicable to
mice, and the lack of open-source datasets hinders algorithmic
progress in this field. To address these challenges, we present
YOLO-MousePose, an enhanced version of the YOLO-Pose
specifically designed for mouse pose estimation from a top–down
view. We also construct the mouse pose dataset from open-field
test (MPD-OFT), which includes 14 586 annotated images, with
each image containing a single mouse. YOLO-MousePose uses
a regression-based approach for precise keypoint localization,
simultaneously detecting the bounding box and 2-D pose of the
mouse in a single forward pass. The model features a fusion
channel-specialized encoder (FCSE) module that selectively fuses
multiscale feature information, improving sensitivity to small
objects and effectively addressing the challenges of small object
detection and keypoint localization. Additionally, we optimize the
keypoint localization loss function to accelerate convergence and
prevent performance degradation. On our open-source dataset,
YOLO-MousePose achieves a root-mean-square error (RMSE)
of 8.41 mm, a mean absolute error (MAE) of 5.52 mm, and an
average percentage of correct keypoints (PCKs) score of 96.1%
at a 0.1 threshold, matching the accuracy of the previous stateof-the-art (SOTA) algorithm GM-SCENet while using only 28%
of its parameters. The dataset and code are publicly available at
https://github.com/bujihao/YOLO-MousePose.
</div>
</div> -->


# 📖 Dataset Usage Guidelines
This dataset is released solely for research and educational purposes. Commercial use in any form is strictly prohibited. Users must comply with all applicable laws and regulations when accessing or using this dataset. Any use of the dataset, in whole or in part, for commercial purposes—including but not limited to product development, commercial services, demonstrations, or redistribution—is not permitted. Publications or reports that utilize this dataset must acknowledge its source.
We kindly ask users to cite the following paper when using this dataset:
Mingxin Yu, Hao Dong, Rui You, Shengjun Liang, Qihao Zhang, Yiyuan Ge, Mingwei Lin, and Zeshui Xu,
"YOLO-MousePose: A Novel Framework and Dataset for Mouse Pose Estimation From a Top–Down View,"
IEEE Transactions on Instrumentation and Measurement, vol. 74, pp. 1–19, 2025, Art no. 5019319,
doi: 10.1109/TIM.2025.3551854.
We also gratefully acknowledge the support of the Intelligent Sensing and Computing Laboratory, Beijing Information Science and Technology University, for the development and release of this dataset.


# 💬 Acknowledgements
We would like to express our sincere gratitude to Mr. Qihao Zhang from Beijing Qiaqia Cloud Technology Co., Ltd. for providing the original dataset. We thank Hao Dong for his significant contributions to data organization, annotation, model construction, training, testing, and manuscript writing. We are also grateful to Shengjun Liang and Yiyuan Ge for their valuable guidance on data analysis and model development. Special thanks go to Xufan Miao and Chengda Yao from our laboratory for their dedicated efforts in data annotation.

# 🔥 How to get the dataset
**If you need to obtain the dataset, please contact [yumingxin@bistu.edu.cn](yumingxin@bistu.edu.cn) or [540083559@qq.com](540083559@qq.com)**

<script type="text/javascript" src="//rf.revolvermaps.com/0/0/6.js?i=54e0ojatafc&amp;m=7&amp;c=e63100&amp;cr1=ffffff&amp;f=arial&amp;l=0&amp;bv=90&amp;lx=-420&amp;ly=420&amp;hi=20&amp;he=7&amp;hc=a8ddff&amp;rs=80" async="async"></script>
