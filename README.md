**English** | [简体中文](README.zh-CN.md)

# Train YOLO Model

Notebooks and small scripts to train a custom object-detection model with [Ultralytics YOLO11](https://docs.ultralytics.com/), then run it on images, video or a webcam.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Kylekk29/Train_YOLO_Model/blob/main/Train_YOLO_Models.ipynb)

## What is here

| File | What it does |
|---|---|
| `Train_YOLO_Models.ipynb` | Train on your own labelled images, in Colab or locally |
| `Train_YOLO_Models_roboflow_colab.ipynb` | The same, for a dataset exported from Roboflow |
| `train_val_split.py` | Splits a folder of images and labels into train and validation sets |
| `yolo_detect.py` | Runs a trained model on an image, a folder, a video or a webcam |

## Train

**Option 1: Google Colab.** Click the badge above, upload your image dataset, and run the cells. This is the easiest route and needs no GPU of your own.

**Option 2: Roboflow dataset.** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Kylekk29/Train_YOLO_Model/blob/main/Train_YOLO_Models_roboflow_colab.ipynb)

**Option 3: Your own PC.** Run the same notebook locally. An Nvidia GPU is strongly recommended.

```bash
pip install -r requirements.txt
```

## Split your data

```bash
python train_val_split.py --datapath path/to/data --train_pct 0.9
```

## Run the model

```bash
python yolo_detect.py --model runs/detect/train/weights/best.pt --source test.jpg --thresh 0.4
```

`--source` can be an image, a folder, a video or a camera. Add `--resolution 640x480 --record` to save the result as a video.

## Credits

The notebooks and scripts follow the Ultralytics YOLO tutorials. YOLO and the `ultralytics` package are licensed by Ultralytics (AGPL-3.0), so check their terms before using this in a product.

## License

See [LICENSE](LICENSE).
