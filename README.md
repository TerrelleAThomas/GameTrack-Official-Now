# Adversarial Patch Impact on Object Detection Models

## Table: Object Prediction Before & After Adversarial Patch

| **Metric**                 | **YOLOv8**                        | **SSD**                             | **Faster R-CNN**                   | **DETR**                            |
|----------------------------|----------------------------------|-------------------------------------|-------------------------------------|-------------------------------------|
| **Original Object Detected** | `Car`                            | `Car`                               | `Car`                               | `Car`                               |
| **Prediction After Patch**  | ❌ `Stop sign, tree, random shape` | ❌ `Person, bike, background noise` | ✅ `Still Car (minor distortion)`    | ⚠️ `Truck, Van (still vehicle)`     |
| **Bounding Box Shift (%)**  | `30-50% (High variance)`        | `40-60% (Severe shift)`            | `10-20% (Minimal impact)`          | `20-35% (Moderate shift)`          |
| **Detection Confidence (%)** | `90% → Drops to 45%`            | `85% → Drops to 35%`               | `95% → Drops to 80%`               | `97% → Drops to 75%`               |
| **Missed Detections (%)**   | `5% → Rises to 40%`             | `10% → Rises to 55%`               | `2% → Rises to 15%`                | `3% → Rises to 25%`                |
| **False Detections (%)**    | `5% → Rises to 30%`             | `10% → Rises to 45%`               | `3% → Rises to 10%`                | `5% → Rises to 15%`                |
| **Inference Time (ms)**     | `8-12ms (Fastest)`              | `15-25ms`                          | `50-150ms (Slow)`                  | `80-200ms (Slowest)`               |
| **Robustness Score (1-10)** | `4/10 (Highly vulnerable)`      | `3/10 (Most vulnerable)`           | `8/10 (Most robust)`               | `6/10 (Moderate res
