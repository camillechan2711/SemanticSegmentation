# COMP9517 - Semantic Segmentation on the WildScenes dataset

# Introduction

Welcome to the repository for our project on semantic segmentation. This repository contains implementations of various semantic segmentation methods explored during the project. Our goal was to investigate and compare deep learning approaches to segment images.

The methods includes Convolutional Neural Networks (CNNs) with U-Net, DeepLabV3+, and Vision Transformers. Each method has been carefully implemented and tailored to address the unique challenges presented by the dataset and task.

This README provides an overview of the setup instructions, and guidelines for running our code.

# Running maskformer.ipynb, cnn.py, and cnn_predict.ipynb

## Running in a non-virtual environment
You can install the required packages using the command below:

```bash
pip install -r requirements.txt
```

## Running in a virtual environment

Below is the setup instrutctions for creating a virtual environment using miniconda3 (https://docs.anaconda.com/miniconda/miniconda-install/) to run `maskformer.ipynb`, `cnn.py`, and `cnn_predict.ipynb`.

Open Anaconda Prompt, install the required packages on conda environment using the command below on Anaconda Prompt:

```bash
conda create -n wildscenes python=3.9
conda activate wildscenes
pip install -r requirements.txt
```

Creating a new kernel to work with the virtual environment using the command below on Anaconda Prompt:
```bash
python -m ipykernel install --user --name=wildscenes --display-name "wildscenes"
```

Make sure to select the newly created kernel to run .ipynb file.
![alt text](image.png)

Select the interpreter of conda environment to run .py file.
![alt text](image-1.png)

# Running DeepLabV3.ipynb

DeepLabV3.ipynb uses a specific version of tensorflow and numpy, using a virtual environment is recommended.

Open Anaconda Prompt, install the required packages on conda environment using the command below on Anaconda Prompt:

```bash
conda create -n wildscenes_dl python=3.9
conda activate wildscenes_dl
pip install -r requirements_dl.txt
```

Creating a new kernel to work with the virtual environment using the command below on Anaconda Prompt:

```bash
python -m ipykernel install --user --name=wildscenes_dl --display-name "wildscenes_dl"
```

Make sure to select the kernel `wildscenes_dl` to run `DeepLabV3.ipynb`.

# Directory structure

Our models is designed to work in the `WildScenes` directory, with the directory structure created by the `setup_data.py` script provided by the WildScenes authors.

Before running our code, you should replace the train/test/val CSV files under `data/splits/opt2d` with the CSV files we provided in `opt2d`, and run `setup_data.py` script provided by the WildScenes author.

## Downloading trained model (`maskformer.ipynb` & `DeepLabV3.ipynb`)

When executing the code in `maskformer.ipynb` and `DeepLabV3.ipynb`, the trained model will be downloaded from a drive into your current directory. Ensure that these files are downloaded in the **same directory** as the `maskformer.ipynb` and `DeepLabV3.ipynb`.

## Running inference (`maskformer.ipynb`)

For running inference on single images in `maskformer.ipynb`, navigate to the `Inference` section of the notebook and execute the codes under `Inference Single`. Ensure the paths to the images are correct. Currently, the implementation is set up to run on a single image. To perform inference on multiple images, call the relevant functions multiple times, providing the necessary image paths. Some example images can be found under `img` directory.

### Citation

@misc{vidanapathirana2023wildscenes,
      title={WildScenes: A Benchmark for 2D and 3D Semantic Segmentation in Large-scale Natural Environments}, 
      author={Kavisha Vidanapathirana and Joshua Knights and Stephen Hausler and Mark Cox and Milad Ramezani and Jason Jooste and Ethan Griffiths and Shaheer Mohamed and Sridha Sridharan and Clinton Fookes and Peyman Moghadam},
      year={2023},
      eprint={2312.15364},
      archivePrefix={arXiv},
      primaryClass={cs.RO}
}
```
