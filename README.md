# det_perspective_transform

## prepare yolov4 model
1. download weights from url https://docs.google.com/uc?export=download&id=1cewMfusmPjYWbrnuJRuKhPMwRe_b9PaT and save it to model directory
2. download cfg from https://raw.githubusercontent.com/opencv/opencv_extra/master/testdata/dnn/yolov4.cfg and save it to model directory

```
D:.
│  .gitignore
│  common.py
│  object_detection.py
│  test.ipynb
│  tf_text_graph_common.py
│  tf_text_graph_faster_rcnn.py
│  tf_text_graph_ssd.py
│
├─.ipynb_checkpoints
│      test-checkpoint.ipynb
│
├─data
│  │  data.txt
│  │  output.jpg
│  │  output.mp4
│  │  paper.png
│  │  PETS2009.avi
│  │  static_frame_from_video.jpg
│  │
│  └─.ipynb_checkpoints
│          output-checkpoint.jpg
│          paper-checkpoint.png
│          static_frame_from_video-checkpoint.jpg
│
├─model
│      model.txt
│      object_detection_classes_yolov3.txt
│      yolov4.cfg
│      yolov4.weights
```

## usage 
python object_detection.py --model model\yolov4.weights --config model\yolov4.cfg --classes model\object_detection_classes_yolov3.txt  --width 416 --height 416 --scale 0.00392 --rgb --input data\PETS2009.avi

# you can change the region of interest by modification of anchor_pts like below
anchor_pts = np.array([(402,138),(757,290),(570,470),(174,265)],dtype='float32')

the sequence of points must be four and in the order of top-left,top-right,bottom-right,bottom-left
