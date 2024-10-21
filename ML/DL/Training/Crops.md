
Train on crops, infer on large images
Обучаем на одном разрешении, а инферим на другом
Train on small images, infer on large images

https://chatgpt.com/c/66e0dd90-9a40-8000-8b22-13fd7afe0b4a

FCN сеть
FCN сеть c SE блоками

Для FCN не должно быть никакой разницы
В случае сегментации и простой [[UNet]] точно да

Train
- Тренировка с изменяющимся размером кропов.
- Тренировка с изменяющимся размером самой финальной картинки которая подается на вход.
- [[YOLOX]] ?

OD
- train object detection model on crops but infer on large images
- FasterRCNN infer on large images
- object detection on large images

FasterRCNN
- Какие были бы проблемы с FasterRCNN или SSD?
- FasterRCNN is fully convolutional
- https://paperswithcode.com/method/faster-r-cnn

Изменения в архитектуре
- Для FCN в архитектуру не нужно вносить какие-либо изменения чтобы делать предсказания на других разрешениях.
- Но иногда нужно соблюдать кратность.
	- mmdetection dbnet картинки кратные 32
	- В каких случаях?

Minimum size
- minimum image size for [[UNet]]
- Также нельзя подавать на вход разрешение меньше определенного, чтобы боттлнек был определенного разрешения.
- Может быть так, что боттлнек слой будет размеров в один пиксель в unet?

Когда могут быть именно проблемы с моделью?
- SE блоки
	- avg pooling
- Когда используем какой-то avg pooling со всей фичамапы.