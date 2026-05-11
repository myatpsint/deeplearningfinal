[![license](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](./LICENSE)

## ECG classification using MIT-BIH dataset 

This repo is an implementation of https://www.nature.com/articles/s41591-018-0268-3 and https://arxiv.org/abs/1707.01836 and focus on training using a MIT-BIH dataset. If you want to train using CINC or open irhythm data, see the open source which the authors of the original research paper have coded at https://github.com/awni/ecg

Introduction to MIT-BIH dataset at physionet : https://physionet.org/physiobank/database/mitdb/

How to run on Google Colab:

!nvidia-smi
!python --version

from google.colab import drive
drive.mount('/content/drive')

%cd /content/drive/MyDrive
!pwd
!ls

!git clone https://github.com/physhik/ecg-mit-bih.git

%cd /content/drive/MyDrive/ecg-mit-bih
!pwd
!ls

!ls src

!pip install --upgrade pip
!pip install -r requirements.txt
%cd /content/drive/MyDrive/ecg-mit-bih
!pip install --upgrade wfdb==4.3.1 pandas==3.0.2
!python -u src/data.py --downloading True
!find dataset -maxdepth 2 -type f
!ls -lh dataset
import os
os.environ["CUDA_VISIBLE_DEVICES"] = "-1"
%cd /content/drive/MyDrive/ecg-mit-bih
!pwd
!ls
!python -u src/train.py

import matplotlib.pyplot as plt
import numpy as np


The original research papers
https://www.nature.com/articles/s41591-018-0268-3
https://arxiv.org/abs/1707.01836

The open source by authors
https://github.com/awni/ecg

also noticable 
https://github.com/fernandoandreotti/cinc-challenge2017/tree/master/deeplearn-approach
