# Serpens

fork of teddykoker's Image GPT, basilisk's cousin. See https://github.com/teddykoker/image-gpt.

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


## WIP
 - [ ] Batched *k*-means on GPU for quantization of larger datasets (currently using
     `sklearn.cluster.MiniBatchKMeans`.)
 - [ ] BERT-style pretraining (currently only generative is supported.)
 - [ ] Load pretrained models from OpenAI.
 - [ ] Reproduce at least iGPT-S results.

According to their [blog post](https://openai.com/blog/image-gpt/), the largest
model, iGPT-L (1.4 M parameters), was trained for 2500 V100-days. By greatly reducing the number of
attention head, number of layers, and input size (which effects model size
quadratically), we can train our own model (26 K parameters) on
[Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist) on a single
NVIDIA 2070 in less than 2 hours.

- [Image GPT](#image-gpt)
  * [Usage](#usage)
    + [Pre-trained Models](#pre-trained-models)
    + [Compute Centroids](#compute-centroids)
    + [Training](#training)
      - [Generative Pre-training](#generative-pre-training)
      - [Classification Fine-tuning](#classification-fine-tuning)
    + [Sampling](#sampling)
