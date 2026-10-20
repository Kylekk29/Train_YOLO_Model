[English](README.md) | **简体中文**

# Train YOLO Model（训练 YOLO 模型）

用 [Ultralytics YOLO11](https://docs.ultralytics.com/) 训练自定义目标检测模型的 Notebook 和小脚本，训练后可用来检测图片、视频或摄像头画面。

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Kylekk29/Train_YOLO_Model/blob/main/Train_YOLO_Models.ipynb)

## 包含什么

| 文件 | 用途 |
|---|---|
| `Train_YOLO_Models.ipynb` | 用你自己标注的图片训练，可在 Colab 或本机运行 |
| `Train_YOLO_Models_roboflow_colab.ipynb` | 同上，适用于从 Roboflow 导出的数据集 |
| `train_val_split.py` | 把图片和标注文件夹拆分成训练集和验证集 |
| `yolo_detect.py` | 用训练好的模型检测图片、文件夹、视频或摄像头 |

## 训练

**方式一：Google Colab。** 点击上面的徽章，上传图片数据集，依次运行各个单元格。这是最简单的方式，不需要自己的显卡。

**方式二：Roboflow 数据集。** [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Kylekk29/Train_YOLO_Model/blob/main/Train_YOLO_Models_roboflow_colab.ipynb)

**方式三：在自己的电脑上。** 在本机运行同一个 Notebook，强烈建议使用 Nvidia 显卡。

```bash
pip install -r requirements.txt
```

## 拆分数据

```bash
python train_val_split.py --datapath path/to/data --train_pct 0.9
```

## 运行模型

```bash
python yolo_detect.py --model runs/detect/train/weights/best.pt --source test.jpg --thresh 0.4
```

`--source` 可以是图片、文件夹、视频或摄像头。加上 `--resolution 640x480 --record` 可把结果保存为视频。

## 致谢

Notebook 和脚本参考了 Ultralytics 的 YOLO 教程。YOLO 和 `ultralytics` 软件包由 Ultralytics 以 AGPL-3.0 授权，用于产品前请先查看他们的条款。

## 许可证

见 [LICENSE](LICENSE)。
