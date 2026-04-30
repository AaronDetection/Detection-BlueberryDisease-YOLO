# 🫐 Blueberry Disease Detection — YOLOv8

Real-time object detection with YOLOv8 for common blueberry diseases, trained from scratch on field-captured imagery using a custom-annotated Roboflow dataset.

*****************************
Link to Dataset: [Blueberries_Diseases Dataset- v1 on Roboflow](https://app.roboflow.com/blueberriesaaron/blueberries_deseases-iuhlb/1) — public +300 images of blueberries diseases
*****************************

---

## What this project does

Detects 3 disease classes on blueberry leaves in live or static images:

| Class | Bounding Box |
|---|---|
| Powdery Mildew | Purple |
| Septoria Leaf Spot | Cyan |
| Necrosis | Red |

No pre-labeled dataset existed for this crop-disease combination, so the full data pipeline — capture, annotation, augmentation, training — was built from zero.

---

## Stack

- **Model:** YOLOv8-Medium (Ultralytics)
- **Annotation:** Roboflow (manual polygon labeling)
- **Training:** Google Colab / local GPU
- **Dataset:** 323 field images, 3 classes

---

## Key results

| Metric | Value |
|---|---|
| Precision | 0.68 |
| Recall | 0.52 |
| mAP@50 | 0.55 |

The precision/recall tradeoff was intentional — in precision agriculture, a false negative (missed disease) costs more than a false positive, so the model was tuned to prioritize detection sensitivity over perfect localization.

---

## Honest limitations

- 323 images is a small dataset for 3 visually similar classes
- val/box_loss oscillation toward epoch 150 indicates the model is near its generalization ceiling with current data volume
- A ~1,000 image dataset would likely push mAP@50 past 0.70

---

## Dataset

[Blueberries_Diseases Dataset- v1 on Roboflow](https://app.roboflow.com/blueberriesaaron/blueberries_deseases-iuhlb/1) — public +300 images of blueberries diseases
