# Face editing with Style GAN 2 and facial segmentation (Ceteris Paribus Face Challenge Intercentrales 2022)

[![Release](https://img.shields.io/github/v/release/valentingol/gan-face-editing)](https://github.com/valentingol/gan-face-editing/releases)
![PythonVersion](https://img.shields.io/badge/python-3.7%20%7C%203.8%20%7C%203.9%20%7C%203.10-informational)
[![License](https://img.shields.io/github/license/valentingol/gan-face-editing?color=brightgreen)](https://stringfixer.com/fr/MIT_license)

[![Pycodestyle](https://github.com/valentingol/gan-face-editing/actions/workflows/pycodestyle.yaml/badge.svg)](https://github.com/valentingol/gan-face-editing/actions/workflows/pycodestyle.yaml)
[![Flake8](https://github.com/valentingol/gan-face-editing/actions/workflows/flake.yaml/badge.svg)](https://github.com/valentingol/gan-face-editing/actions/workflows/flake.yaml)
[![Pydocstyle](https://github.com/valentingol/gan-face-editing/actions/workflows/pydocstyle.yaml/badge.svg)](https://github.com/valentingol/gan-face-editing/actions/workflows/pydocstyle.yaml)
[![Isort](https://github.com/valentingol/gan-face-editing/actions/workflows/isort.yaml/badge.svg)](https://github.com/valentingol/gan-face-editing/actions/workflows/isort.yaml)
[![PyLint](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/valentingol/c60e6ce49447254be085193c99b8425b/raw/gan_face_editing_pylint_badge.json)](https://github.com/valentingol/gan-face-editing/actions/workflows/pylint.yaml)

**NOTE** : This is work based on the winner team repository of Inter-Centrales 2022 AI competition: Ceteris Paribus Face Challenge: [site of the competition](https://transfer-learning.org/competition.html) plus the work of the second team composed by Thibault Le Sellier De Chezelles and Hédi Razgallah (original work can be found [here](https://github.com/HediRaz/InterCentrales).


## Quick Start

**Note**: you need a Nvidia GPU to run the processing. Only editor API with pre-computed latent vectors is available with CPU.

### Installation

Clone this repository and pull the models required from postprocessing via LFS:

```script
git clone git@github.com:valentingol/gan-face-editing.git
cd gan-face-editing
git lfs pull
```

Then, create a new virtual environment and install all the required packages:

```bash
pip install -e .
pip install -r requirements.txt
```


```yaml
# configs/exp/
data_dir: data/my_dataset_name
```


Note that if you not used the characteristics in the image, you can name the translation vectors as you want.

**Important:** To use the semantic segmentation mixup, the algorithm should understand the part of the face you want to modify (and the part of the image you want to preserve from the original image). To do so, you need to add a particular prefix for the translation vectors: for instance for eyes change, you need to use the prefix 'N'. For instance `N_0` is a valid translation that will only edit the eyes. The table of prefix is:

| Part to modify    | Prefix             |
| :---------------: |:------------------:|
| All the face      | A, Ch, Se or Sk    |
| Hair              | B, Hc or Hs        |
| Nose              | Pn                 |
| Eyes              | Bn or N            |
| Just under eyes   | Be                 |
| Lips              | Bp                 |

If you don't use one of the prefix above, no segmentation mixup will be applied. You can use the prefix you want for custom transformations. More intuitive prefix will be available later (e.g 'eyes' for eyes, 'face' for all the face ...).

### Extract other attribute directions

:construction:

### Retrain the GAN

To retrain the GAN you need to install [horovod](https://github.com/horovod/horovod) (Mac or Linux only).

:construction:
