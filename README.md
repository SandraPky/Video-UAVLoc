# Video-UAVLoc
fFor experiments on sequential image/video geo-localization tasks
**Video-UAVLoc** is a benchmark dataset specifically designed for **sequential image/video-based geo-localization tasks using UAV imagery**. It aims to address the limitations of existing datasets by providing geographically diverse, realistic, and high-quality sequences captured from UAV flights over various terrains.

---

## 🔍 Background

Most public UAV video datasets focus on tasks such as object detection or pose estimation. Datasets suitable for geo-localization are either unpublished or too simple—limited in flight altitude, scene diversity, or sequence structure.

To address these gaps, we utilize the open-source [**UAV-VisLoc** dataset](https://github.com/IntelliSensing/UAV-VisLoc) [1](https://arxiv.org/abs/2405.11936), which provides a large number of UAV images with geographic annotations. UAV-VisLoc captures real-world scenes across multiple regions in China, including:

- The Yangtze River Basin
- Taizhou (Jiangsu)
- Yunnan
- Zhuxi
- Donghuayuan
- Huzhou
- Huailai
- Shandan (Gansu)

The scenes cover a wide range of geographical types: farmland, towns, urban areas, and rivers, enabling models to generalize across diverse environments.

---

## 📦 Dataset Construction: Video-UAVLoc

We build the **Video-UAVLoc** dataset by treating consecutive UAV images as video keyframes, simulating realistic UAV video footage. As illustrated below (adapted from UAV-VisLoc), red dots represent UAV image centers, yellow arrows show flight direction, and the white dashed boxes indicate how sequential clips are extracted.

![Dataset Structure](path_to_your_fig32.png)

### 🧱 Sequence Construction Strategies:

To form video-like sequential image groups, we adopt the following configurations:

- `[1×15]`: 15 images in a straight path
- `[2×8]`: two rows, 8 images each
- `[3×5]`: grid of 15 images
- `[4×4]`: grid of 16 images

> These different grouping strategies reflect possible UAV flight patterns and camera coverage.

---

## 📐 Dataset Statistics

| Content                        | Description                          |
|-------------------------------|--------------------------------------|
| UAV Images                    | 6,742 images from UAV-VisLoc         |
| Satellite Maps                | 11 Google Earth maps (0.3m resolution) |
| Sequential Queries            | 120 test sequences, 180 validation sequences |
| Satellite Reference Tiles     | 1280×1280 pixel images with GPS center recorded |

Each UAV image is annotated with:
- GPS coordinates of the image center
- Altitude
- Heading angle
- Capture date

Satellite reference images are pre-cropped from Google Earth for each UAV flight and annotated with GPS bounding boxes.

---

## 🔗 Related Links

- 📄 UAV-VisLoc Dataset: [GitHub](https://github.com/IntelliSensing/UAV-VisLoc)
- 🛰️ Google Earth imagery used under [Google Earth Terms of Use](https://www.google.com/intl/en/help/terms_maps/)

---

## 📥 Download & License

> 🔐 *Currently, access to Video-UAVLoc is restricted for research purposes only. Please contact the authors to request access.*

<!-- Uncomment if dataset is public:
📦 [Download Video-UAVLoc Dataset](https://your-download-link.com)
-->

---

## 📌 Citation

If you use **Video-UAVLoc** in your research, please cite:
@misc{video-uavloc2025,
title={Video-UAVLoc: A Dataset for Sequential UAV Image Geo-localization},
author={Keyue Pan},
year={2025},
note={Under Review}
}

---

## ✉️ Contact

For questions, please contact: **keyuepan@qq.com**
