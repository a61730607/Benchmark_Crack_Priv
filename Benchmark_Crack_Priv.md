
## Priv_Crack-Benchmark

### Priv_Crack_Dataset:
* The origin data come from CHINA ACADEMY OF RAILWAY SCIENCES, we label the images for classification and segmentation to find the cracks in iamges.
* v0.1 contain the 26512 railway tunnel images , most of them are nornal images, 
* v0.2 is is going on.

version |total |train positive|train negative|val positive|val nagative|test positive|test nagative|notes
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
v 0.1|26512|896|2104|869|2131|941|19571|备注

*v0.2 is going on
*计划 3000 张裂缝图像（小图） 1000 张分割图像（大图）   


### Classification  performance

* **Environment:**  `cuda: 8.0`, `cudnn: 6.0`, `GPU: titan xp`
* **Network:** `lr-decay: step`, `fix_bn: False`
* **Training:** `batch-size: 32`, `epochs: 100`,`base-size: 600`, `crop-size: 600`
* **validation:** `batch-size: 15`,  `base-size: 600`, `crop-size: 600`
* **Testing:** `crop-type: multi-crop`, `base-size: 632`, `crop-size: 600`
* **pre-train:** `fine-tuning from imagenet model`
#### 1 Performance on Caffe 
Network|crop type|base lr|weight decay|val top1|test acc|test precision|test recall|notes
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
resnet18|single-crop|0.001|0.0005|0.89|0.977|0.727|0.807|base_line
resnet18|multi-crop|0.001|0.0005|0.89|0.985|0.870|0.808|

#### 1 Performance on Pytorch
Network|crop type|base lr|weight decay|val top1|test acc|test precision|test recall|notes
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
resnet18-1x64d|single-crop|0.0025|0.0005|0.93|0.986|0.884|0.808|base_line
resnet18-1x64d|single-crop|0.001 |0.0005|0.92|0.980|0.753|0.850|point：800
resnet18-1x64d|single-crop|0.00025|0.0005|0.92|0.967|0.60|0.823|point：776
resnet18-1x64d|single-crop|0.0025|0.0005|0.927|0.9835|0.8099|0.8374|rotation(-10,10)point：788
resnet18-1x64d|single-crop|0.0025|0.0010|0.927|0.981|0.75|0.88|point：828




### Segmentation  performance













