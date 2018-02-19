# StackGAN-v2

- [StackGAN-v1: Tensorflow implementation](https://github.com/hanzhanggit/StackGAN)

- [StackGAN-v1: Pytorch implementation](https://github.com/hanzhanggit/StackGAN-Pytorch)

- [Inception score evaluation](https://github.com/hanzhanggit/StackGAN-inception-model)


Pytorch implementation for reproducing StackGAN_v2 results in the paper [StackGAN++: Realistic Image Synthesis with Stacked Generative Adversarial Networks](https://arxiv.org/abs/1710.10916) by Han Zhang*, Tao Xu*, Hongsheng Li, Shaoting Zhang, Xiaogang Wang,   Xiaolei Huang, Dimitris Metaxas.

<img src="examples/framework.jpg" width="900px" height="350px"/>



### Dependencies
python 2.7

Pytorch

In addition, please add the project folder to PYTHONPATH and `pip install` the following packages:
- `tensorboard`
- `python-dateutil`
- `easydict`
- `pandas`
- `torchfile`



**Data**

1. Download our preprocessed char-CNN-RNN text embeddings for [birds](https://drive.google.com/open?id=0B3y_msrWZaXLT1BZdVdycDY5TEE) and save them to `data/`
  - [Optional] Follow the instructions [reedscot/icml2016](https://github.com/reedscot/icml2016) to download the pretrained char-CNN-RNN text encoders and extract text embeddings.
2. Download the [birds](http://www.vision.caltech.edu/visipedia/CUB-200-2011.html) image data. Extract them to `data/birds/`
3. Download [ImageNet](http://image-net.org/download) dataset and extract the images to `data/imagenet/`
4. Download [LSUN](https://github.com/fyu/lsun) dataset and save the images to `data/lsun`




**Training**

- Train a StackGAN-v2 model on the bird (CUB) dataset using our preprocessed embeddings:
  -  `python main.py --cfg cfg/birds_3stages.yml --gpu 0`
- Train a StackGAN-v2 model on the ImageNet dog subset:
  -  `python main.py --cfg cfg/dog_3stages_color.yml --gpu 0`
- Train a StackGAN-v2 model on the ImageNet cat subset:
  -  `python main.py --cfg cfg/cat_3stages_color.yml --gpu 0`
- Train a StackGAN-v2 model on the lsun bedroom subset:
  -  `python main.py --cfg cfg/bedroom_3stages_color.yml --gpu 0`
- Train a StackGAN-v2 model on the lsun church subset:
  -  `python main.py --cfg cfg/church_3stages_color.yml --gpu 0`
- `*.yml` files are example configuration files for training/evaluation our models.
- If you want to try your own datasets, [here](https://github.com/soumith/ganhacks) are some good tips about how to train GAN. Also, we encourage to try different hyper-parameters and architectures, especially for more complex datasets.



**Pretrained Model**
- [StackGAN-v2 for bird](). Download and save it to `models/`
- [StackGAN-v2 for dog](). Download and save it to `models/`
- [StackGAN-v2 for cat](). Download and save it to `models/`
- [StackGAN-v2 for bedroom](). Download and save it to `models/`
- [StackGAN-v2 for church](). Download and save it to `models/`



**Evaluating**
- Run `python main.py --cfg cfg/eval_birds.yml --gpu 1` to generate samples from captions in birds validation set.
- Change the `eval_*.yml` files to generate images from other pre-trained models. 


**Examples generated by StackGAN-v2**
![](examples/examples_on_different_datasets.png)


### Citing StackGAN++
If you find StackGAN useful in your research, please consider citing:

```
@article{Han17stackgan2,
  author    = {Han Zhang and Tao Xu and Hongsheng Li and Shaoting Zhang and Xiaogang Wang and Xiaolei Huang and Dimitris Metaxas},
  title     = {StackGAN++: Realistic Image Synthesis with Stacked Generative Adversarial Networks},
  journal   = {arXiv: 1710.10916},
  year      = {2017},
}
```

```
@inproceedings{han2017stackgan,
Author = {Han Zhang and Tao Xu and Hongsheng Li and Shaoting Zhang and Xiaogang Wang and Xiaolei Huang and Dimitris Metaxas},
Title = {StackGAN: Text to Photo-realistic Image Synthesis with Stacked Generative Adversarial Networks},
Year = {2017},
booktitle = {{ICCV}},
}
```

**Our follow-up work**

- [AttnGAN: Fine-Grained Text to Image Generation with Attentional Generative Adversarial Networks](https://arxiv.org/abs/1711.10485) [[Supplementary]](https://1drv.ms/b/s!Aj4exx_cRA4ghK5-kUG-EqH7hgknUA)


**References**

- Generative Adversarial Text-to-Image Synthesis [Paper](https://arxiv.org/abs/1605.05396) [Code](https://github.com/reedscot/icml2016)
- Learning Deep Representations of Fine-grained Visual Descriptions [Paper](https://arxiv.org/abs/1605.05395) [Code](https://github.com/reedscot/cvpr2016)
