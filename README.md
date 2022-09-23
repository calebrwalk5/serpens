# Serpens

fork of teddykoker's Image GPT, basilisk's cousin. See https://github.com/teddykoker/image-gpt.

### Installation

see ```./scripts/``` folder

### Training
```
python src/run.py
```
### GIF
```
python src/gif.py
```

# Image GPT

PyTorch implementation of Image GPT, based on paper *Generative Pretraining from Pixels* [(Chen et al.)](https://cdn.openai.com/papers/Generative_Pretraining_from_Pixels_V2.pdf)
and accompanying [code](https://github.com/openai/image-gpt).

<img src="figures/mnist.png" height="256px"/> <img src="figures/fmnist.png" height="256px"/>
<br>
*Model-generated completions of half-images from test set. First column is
input; last column is original image*

<img src="figures/cifar10.png" height="256px"/>
<br>

*iGPT-S pretrained on CIFAR10. Completions are fairly poor as the model was
only trained on CIFAR10, not all of ImageNet.*
