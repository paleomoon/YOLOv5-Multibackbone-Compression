训练：

```

python train.py --data SHWD-MINI.yaml --cfg hat-yolov5s.yaml --weights yolov5s.pt --name yolov5s_hat --device 0 --imgsz 512 --epochs 200 --batch 16

```

all classes 0.905 mAP@0.5

推理：

```

python detect.py --source data/images/test.jpg --weights runs/train/yolov5s_hat/weights/best.pt --img 512

```

Model Summary: 213 layers, 7015519 parameters, 0 gradients, 15.8 GFLOPs

image 1/1 /home/huge/YOLOv5-Multibackbone-Compression/data/images/test.jpg: 288x512 2 hats, Done. (0.049s)

Speed: 0.8ms pre-process, 48.9ms inference, 4.1ms NMS per image at shape (1, 3, 512, 512)

稀疏化训练：

```

python train.py --data SHWD-MINI.yaml --cfg models/prunModels/yolov5s-pruning.yaml --weights yolov5s.pt --imgsz 512 --epochs 200 --batch 16 --sparse

```
