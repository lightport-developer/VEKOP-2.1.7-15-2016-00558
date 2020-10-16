![Logo](https://lightport.hu/img/logo_lp.png)

# VEKOP-2.1.7-15-2016-00558 azonosítójú projekt

A projekt célja egy könnyen üzembe helyezhető és integráltható, költséghatékony, környezettudatos szempontokat figyelembe vevő – közúti adatgyűjtő prototípus gép fejlesztése, közúti, közterületi létesítmény elemek rendszeres ellenőrzésének és automatizált feladatkiosztáson alapuló karbantartásának támogatása.

## Technikai információk

### Szoftver követelmény

| Szoftver | Verziószám |
|-----------|-------------|
| [Tensorflow](https://www.tensorflow.org/) | 1.12.2 |
| [Python](https://www.python.org/download/releases/3.0/) | 3 |
| [NVIDIA driver](https://www.nvidia.com/en-us/geforce/drivers/) | 384.183|
| [CUDA toolkit](https://developer.nvidia.com/cuda-90-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1604&target_type=deblocal) | 9(.0.176) |
| [CUDNN toolkit](https://developer.nvidia.com/cudnn) | 7.6.1|

### Hardver követelmény
| Eszköz | Típus |
|-----------|-------------|
| GPU | NVIDIA GeForce GTX 1080|


### Felhasznált előre betanított modell

A projekthez a [faster_rcnn_inception_v2_coco_2018_01_28](https://github.com/lightport-developer/VEKOP-2.1.7-15-2016-00558/tree/master/research/object_detection/faster_rcnn_inception_v2_coco_2018_01_28) előre betanított modellt használtuk fel, amelyet tovább tanítottunk saját adatokkal.

### Adathalmaz

| Tábla | [Címke](research/object_detection/training/labelmap.pbtxt) | Darabszám(tanítás/teszt) | Mintakép | Inferált kép |
|-----------|-------------|-------------|-------------|-------------|
| Sebesség korlázotás: 40 | speed_limit_40 | 25/65 | [kép](research/object_detection/images/train/EMER190726-161252F.MP4.thumb0006.jpg) | [kép](research/object_detection/InferredImages/FILE190712-091517F.shrink.mp4.thumb0002.jpg.infer.jpg) |
| Sebesség korlázotás: 60 | speed_limit_60 | 30/100 | [kép](research/object_detection/images/train/FILE190713-090605F.shrink.mp4.thumb0028.jpg) | [kép](research/object_detection/InferredImages/FILE190726-161127F.MP4.thumb0057.jpg.infer.jpg) |
| Sebesség korlázotás: 70 | speed_limit_70 | 25/80 | [kép](research/object_detection/images/train/FILE190713-105959F.shrink.mp4.thumb0003.jpg) | [kép](research/object_detection/InferredImages/FILE190726-152235F.MP4.thumb0024.jpg.infer.jpg) |
| Előzni tilos | no_overtaking | 40/130 | [kép](research/object_detection/images/train/FILE190713-091407F.shrink.mp4.thumb0012.jpg) | [kép](research/object_detection/InferredImages/FILE190726-161127F.MP4.thumb0057.jpg.infer.jpg) |
| Parkolni tilos | no_parking | 27/90 | [kép](research/object_detection/images/train/FILE190712-091116F.shrink.mp4.thumb0015.jpg) | [kép](research/object_detection/InferredImages/FILE190713-120332F.shrink.mp4.thumb0010.jpg.infer.jpg) |
| Gyalogos átkelő | pedestrian_crossing | 26/95 | [kép](research/object_detection/images/train/FILE190726-170026F.MP4.thumb0045.jpg) | [kép](research/object_detection/InferredImages/FILE190903-123157F.MP4.thumb0019.jpg.infer.jpg) |
| Főútvonal | priority_road | 36/137 | [kép](research/object_detection/images/train/FILE190713-094119F.shrink.mp4.thumb0012.jpg) | [kép](research/object_detection/InferredImages/FILE190903-123157F.MP4.thumb0019.jpg.infer.jpg) |
| Figyelmeztető tábla | warning | 35/141 | [kép](research/object_detection/images/train/FILE190712-091718F.shrink.mp4.thumb0013.jpg) | [kép](research/object_detection/InferredImages/FILE190713-094220F.shrink.mp4.thumb0015.jpg.infer.jpg) |


## Inferálás futtatása

Hozzuk létre a tensorflow konténert: 
```bash
conda create -n tensorflow pip python=3.5
source activate tensorflow
```
Az elkészített konténerben telepítsük a fent részletezett szoftvereket. Ezután az alábbiakban leírt módon futtatható az inferálás:
```bash
idle3
```
A felugró ablakban megnyitjuk az [Object_detection_image.py](research/object_detection/Object_detection_image.py) vagy [Object_detection_video.py](research/object_detection/Object_detection_video.py) fájlt, majd a IMAGE_NAME/VIDEO_NAME változót átírjuk az inferálni kívánt fájl elérési útvonalára és az F5 gomb megnyomásával futtatjuk a programot.

## Eredmények

Néhány példa az eredmények bemutatására [videós](https://ingatlanflotta.hu/video/FILE190712-091217F.MP4.infer.webm), illetve [képes](research/object_detection/InferredImages/) formában.


