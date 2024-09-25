# Installation

### 1. Install Required Libraries from Snail-SSL

Follow the instructions in the [snail-ssl quickstart guide](snail-ssl/README.md#quickstart) to install the necessary dependencies.

```bash
cd snail-ssl
pip install -e .
```

### 2. Install PyTorchVideo

First, install the required dependency fvcore:
```bash
pip install fvcore
```
Next, install [PyTorchVideo](https://github.com/facebookresearch/pytorchvideo):
```bash
pip install "git+https://github.com/facebookresearch/pytorchvideo.git"
```
### 3. Install PyTorchVideo Trainer

PyTorchVideo Trainer is a PyTorch Lightning-based trainer that supports PyTorchVideo models and dataloaders for various video understanding tasks.

1.	Install the additional `recipes` dependency:
```bash
pip install --no-deps "git+https://github.com/facebookresearch/recipes.git"
```
2.	Then, install the PyTorchVideo Trainer:
```bash
pip install "git+https://github.com/facebookresearch/pytorchvideo.git#egg=pytorchvideo_trainer&subdirectory=pytorchvideo_trainer"
```
### 4. Install Decord
```bash
pip install decord
```
