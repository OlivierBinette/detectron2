<img src=".github/Detectron2-Logo-Horz.svg" width="300" >

---

# This repo contains the training configuration, code and trained model for [PubLayNet](https://github.com/ibm-aur-nlp/PubLayNet) dataset  

Important:
* Models are trained on a portion of the dataset (train-0.zip, train-1.zip, train-2.zip, train-3.zip)
* Trained on total 191832 images
* Models are evaluated on dev.zip
* Trained using Nvidia GTX 1080Ti 11GB

## For training from scratch use 
```
./tools/train_net_dla.py
```



## Mask-RCNN resnext101_32x8d backbone
Config file: 
```
./configs/DLA_mask_rcnn_X_101_32x8d_FPN_3x.yaml
```  
Trained model: https://www.dropbox.com/sh/jxuxu2oh4f8ogms/AADaG0U2hXORh_kd8NazDAgsa?dl=0

> To continue training the model use model_final.pth  
> To predict on image or fine tune use model_final_trimmed.pth

```
python demo/demo.py --config-file configs/DLA_mask_rcnn_X_101_32x8d_FPN_3x.yaml --input "<path to image.jpg>" --output <path to save the predicted image> --confidence-threshold 0.5 --opts MODEL.WEIGHTS <path to model_final_trimmed.pth> MODEL.DEVICE cpu
```

### Inference on validation data  
<img src="assets/images/resnext101_32x8d/result_resnext101_32x8d.JPG" > 



## Mask-RCNN resnet101 backbone  
Config file: 
```
./configs/DLA_mask_rcnn_R_101_FPN_3x.yaml
```    
Trained model: https://www.dropbox.com/sh/jxuxu2oh4f8ogms/AADaG0U2hXORh_kd8NazDAgsa?dl=0

### Inference on validation data  
<img src="assets/images/resnet101/result_resnet101.JPG" >

---

## Sample results from detectron2

<img src="assets/images/resnet101/PMC1247189_00000.jpg" >  

<img src="assets/images/resnet101/PMC2778503_00000.jpg" >  


 

---

Detectron2 is Facebook AI Research's next generation software system
that implements state-of-the-art object detection algorithms.
It is a ground-up rewrite of the previous version,
[Detectron](https://github.com/facebookresearch/Detectron/),
and it originates from [maskrcnn-benchmark](https://github.com/facebookresearch/maskrcnn-benchmark/).

<div align="center">
  <img src="https://user-images.githubusercontent.com/1381301/66535560-d3422200-eace-11e9-9123-5535d469db19.png"/>
</div>

### What's New
* It is powered by the [PyTorch](https://pytorch.org) deep learning framework.
* Includes more features such as panoptic segmentation, densepose, Cascade R-CNN, rotated bounding boxes, etc.
* Can be used as a library to support [different projects](projects/) on top of it.
  We'll open source more research projects in this way.
* It [trains much faster](https://detectron2.readthedocs.io/notes/benchmarks.html).

See our [blog post](https://ai.facebook.com/blog/-detectron2-a-pytorch-based-modular-object-detection-library-/)
to see more demos and learn about detectron2.

## Installation

See [INSTALL.md](INSTALL.md).

## Quick Start

See [GETTING_STARTED.md](GETTING_STARTED.md),
or the [Colab Notebook](https://colab.research.google.com/drive/16jcaJoc6bCFAQ96jDe2HwtXj7BMD_-m5).

Learn more at our [documentation](https://detectron2.readthedocs.org).
And see [projects/](projects/) for some projects that are built on top of detectron2.

## Model Zoo and Baselines

We provide a large set of baseline results and trained models available for download in the [Detectron2 Model Zoo](MODEL_ZOO.md).


## License

Detectron2 is released under the [Apache 2.0 license](LICENSE).

## Citing Detectron

If you use Detectron2 in your research or wish to refer to the baseline results published in the [Model Zoo](MODEL_ZOO.md), please use the following BibTeX entry.

```BibTeX
@misc{wu2019detectron2,
  author =       {Yuxin Wu and Alexander Kirillov and Francisco Massa and
                  Wan-Yen Lo and Ross Girshick},
  title =        {Detectron2},
  howpublished = {\url{https://github.com/facebookresearch/detectron2}},
  year =         {2019}
}
```
