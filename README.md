
1. Pretrained_model_approach folder

•	The project is all about object detection of person and handbag classes which are classes of COCO dataset of 80 categories. So, all the pretrained models which are trained on COCO dataset can classify the person and handbag. But it will detect other 78 categories too.
•	So I Used GluonCV which is built on top of MXNet and PyTorch, which provides a good approach to detect desired categories by simply changing the class names and their weights.

2. VOC_Data_Creation and Model_training_approach folders
•	For creating data I first downloaded the coco annotation file. From there I extracted image id and annotation ids of images which contains both class person and handbag.
•	I was not able to directly convert annotation file which contained 80 classes to the desired e.g.2 classes(person,handbag).
•	So I converted all the annotations from COCO to VOC.
•	I removed classes other than person and handbag from VOC annotations  and did preprocessing on them e.g. converting bbox values from float to int(so that I can verify them in labelImg).
•	All the preprocessing scripts are in VOC_Data_creation folder.
•	I took data of 3740 images with 3000 in train and 370 in validation and 370 in test (0.8,0.1,0.1 ratio) and trained the faster rcnn model with below hyperparameters.

o	Learning rate : 0.001
o	Optimizer : SGD
o	Momentum : 0.9
o	weight_decay : 0.0001
o	Epochs : 10

•	Model gave accuracy of 90-92 during training while mAP was 0.48-0.49.
•	Due to the fact that pretrained model was already built on these classes the detection was good even though mAP was not much.

