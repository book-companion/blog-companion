# Weights for chapter 15 (the digit-reader capstone)

`mnist_mlp.pt` is the trained state dict that chapter 15 of *Running Models* loads. The book does not train, so this is shipped pre-trained — exactly what "pretrained" means. It was produced by `train_mnist_mlp.py` (three epochs of Adam on MNIST, about a minute on a CPU) and scores 96.1% on the MNIST test set.

To regenerate it:

```bash
pip install torch torchvision
python train_mnist_mlp.py   # writes mnist_mlp.pt next to this file
```

The chapter loads it from:
`https://github.com/book-companion/blog-companion/raw/main/running-models-inside/weights/mnist_mlp.pt`

The architecture must stay in sync with the chapter:
`nn.Sequential(nn.Flatten(), nn.Linear(784, 128), nn.ReLU(), nn.Linear(128, 10))`.
