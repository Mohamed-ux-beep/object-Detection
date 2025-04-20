# 🚗🗑️ Object Detection with YOLOv8 – Cars & Trash Bins

This project demonstrates an end-to-end object detection workflow using [Ultralytics YOLOv8](https://docs.ultralytics.com/) to identify two object classes: **cars** and **trash bins**. All images used in this dataset were **personally collected and labeled** for this project.

## 📸 Dataset

The dataset consists of:
- ✅ 30+ images of **cars**
- ✅ 30+ images of **trash bins**
- ✅ Annotations created manually using [makesense.ai](https://www.makesense.ai/)

The data is organized as follows:

```
├── Dataset-ki/
│   ├── images/
│   │   └── train/
│   ├── labels/
│   │   └── train/
│   └── data.yaml
├── ObjektDetection.ipynb      ← Training & inference notebook
├── best.pt                    ← Trained YOLOv8 model
└── README.md                  ← Project documentation
```

## 🧠 Model Training

- **Model:** YOLOv8n (nano version for faster training and deployment)
- **Environment:** Google Colab with GPU acceleration
- **Framework:** [Ultralytics Python package](https://github.com/ultralytics/ultralytics)

Training was performed on the custom dataset with YOLO format annotations.

## 📊 Evaluation Metrics

| Metric                        | Value         |
|------------------------------|---------------|
| **Precision (B)**            | 0.9773        |
| **Recall (B)**               | 0.9690        |
| **mAP@0.5 (B)**              | 0.8494        |
| **mAP@0.5:0.95 (approx.)**   | 0.8288 – 0.8393 |

- `fitness`: **0.8494**
- Classes:
  - `0`: car
  - `1`: trash_bin

## 🧪 Run Inference

To test the trained model on an image from the dataset:

```python
from ultralytics import YOLO

model = YOLO("runs/detect/train/weights/best.pt")
model.predict(source="Dataset-ki/images/train/car_01.jpeg", conf=0.3, save=True)
```

## 🏁 Future Improvements

- Add more diverse backgrounds and lighting conditions
- Include more object classes (e.g., bikes, traffic signs)
- Try larger YOLO models (YOLOv8s or YOLOv8m) for better accuracy

## 📄 License

This project is released for educational and research use.  
All images were collected by the author and should not be redistributed without permission.

---

**Author:** Mohamed Abokahf  
**Email:** mohamed.abokahf@stud.fh-anhalt.de
