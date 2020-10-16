![Logo](https://lightport.hu/img/logo_lp.png)

# VEKOP-2.1.7-15-2016-00558 azonosítójú projek

A projekt célja egy könnyen üzembe helyezhető és integráltható, költséghatékony, környezettudatos szempontokat figyelembe vevő – közúti adatgyűjtő prototípus gép fejlesztése, közúti, közterületi létesítmény elemek rendszeres ellenőrzésének és automatizált feladatkiosztáson alapuló karbantartásának támogatása.

## Technikai információk

### Szofver követelmény

| Eszkösz | Verziószám |
|-----------|-------------|
| [Tensorflow](https://www.tensorflow.org/) | • 1.12.2 |
| [Python](https://www.python.org/download/releases/3.0/) | • 3 |
| [NVIDIA driver](https://www.nvidia.com/en-us/geforce/drivers/) | • 384.183|
| [CUDA toolkit](https://developer.nvidia.com/cuda-90-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1604&target_type=deblocal) | • 9(.0.176) |
| [CUDNN toolkit](https://developer.nvidia.com/cudnn) | • 7.6.1|

### Hardver követelmény
| Eszkösz | Típus |
|-----------|-------------|
| GPU | • NVIDIA GeForce GTX 1080|


### Felhasznált előre betanított modell

A projekthez a [faster_rcnn_inception_v2_coco_2018_01_28](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/tree/master/research/object_detection/faster_rcnn_inception_v2_coco_2018_01_28) előre betanított modellt használtuk fel, amelyet tovább tanítottunk saját adatokkal.

### Adathalmaz

| Tábla | [Címke](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/training/labelmap.pbtxt) | Darabszám(tanítás/teszt) | Mintakép | Inferált kép |
|-----------|-------------|-------------|-------------|-------------|
| Sesesség korlázotás: 40 | speed_limit_40 | 25/65 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/EMER190726-161252F.MP4.thumb0006.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190712-091517F.shrink.mp4.thumb0002.jpg.infer.jpg) |
| Sesesség korlázotás: 60 | speed_limit_60 | 30/100 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/FILE190713-090605F.shrink.mp4.thumb0028.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190726-161127F.MP4.thumb0057.jpg.infer.jpg) |
| Sesesség korlázotás: 70 | speed_limit_70 | 25/80 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/FILE190713-105959F.shrink.mp4.thumb0003.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190726-152235F.MP4.thumb0024.jpg.infer.jpg) |
| Előzni tilos | no_overtaking | 40/130 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/FILE190713-091407F.shrink.mp4.thumb0012.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190726-161127F.MP4.thumb0057.jpg.infer.jpg) |
| Parkolni tilos | no_parking | 27/90 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/FILE190712-091116F.shrink.mp4.thumb0015.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190713-120332F.shrink.mp4.thumb0010.jpg.infer.jpg) |
| Gyalogos átkelő | pedestrian_crossing | 26/95 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/FILE190726-170026F.MP4.thumb0045.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190903-123157F.MP4.thumb0019.jpg.infer.jpg) |
| Főútvonal | priority_road | 36/137 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/FILE190713-094119F.shrink.mp4.thumb0012.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190903-123157F.MP4.thumb0019.jpg.infer.jpg) |
| Figyelmeztető tábla | warning | 35/141 | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/images/train/FILE190712-091718F.shrink.mp4.thumb0013.jpg) | [kép](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/blob/master/research/object_detection/InferredImages/FILE190713-094220F.shrink.mp4.thumb0015.jpg.infer.jpg) |


| Date | News |
|------|------|
| July 10, 2020 | TensorFlow 2 meets the [Object Detection API](https://github.com/tensorflow/models/tree/master/research/object_detection) ([Blog](https://blog.tensorflow.org/2020/07/tensorflow-2-meets-object-detection-api.html)) |
| June 30, 2020 | [SpineNet: Learning Scale-Permuted Backbone for Recognition and Localization](https://github.com/tensorflow/models/tree/master/official/vision/detection#train-a-spinenet-49-based-mask-r-cnn) released ([Tweet](https://twitter.com/GoogleAI/status/1278016712978264064)) |
| June 17, 2020 | [Context R-CNN: Long Term Temporal Context for Per-Camera Object Detection](https://github.com/tensorflow/models/tree/master/research/object_detection#june-17th-2020) released ([Tweet](https://twitter.com/GoogleAI/status/1276571419422253057)) |
| May 21, 2020 | [Unifying Deep Local and Global Features for Image Search (DELG)](https://github.com/tensorflow/models/tree/master/research/delf#delg) code released |
| May 19, 2020 | [MobileDets: Searching for Object Detection Architectures for Mobile Accelerators](https://github.com/tensorflow/models/tree/master/research/object_detection#may-19th-2020) released |
| May 7, 2020 | [MnasFPN with MobileNet-V2 backbone](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md#mobile-models) released for object detection |
| May 1, 2020 | [DELF: DEep Local Features](https://github.com/tensorflow/models/tree/master/research/delf) updated to support TensorFlow 2.1 |
| March 31, 2020 | [Introducing the Model Garden for TensorFlow 2](https://blog.tensorflow.org/2020/03/introducing-model-garden-for-tensorflow-2.html) ([Tweet](https://twitter.com/TensorFlow/status/1245029834633297921)) |

## Contributions

[![help wanted:paper implementation](https://img.shields.io/github/issues/tensorflow/models/help%20wanted%3Apaper%20implementation)](https://github.com/tensorflow/models/labels/help%20wanted%3Apaper%20implementation)

If you want to contribute, please review the [contribution guidelines](https://github.com/tensorflow/models/wiki/How-to-contribute).

## License

[Apache License 2.0](LICENSE)
