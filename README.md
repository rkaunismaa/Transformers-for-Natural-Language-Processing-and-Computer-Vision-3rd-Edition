# Transformers-for-Natural-Language-Processing-and-Computer-Vision-3rd-Edition

This will be a walk through of select code samples of the book "Transformers for Natural Language Processing and Computer Vision" 3rd Edition by Denis Rothman

<img src="Transformers_3rd_Edition.jpg?raw=tru" alt="drawing" width="400"/>

## Tuesday, March 12, 2024

* pip install -U trax --dry-run

I ran the above just to see what would get installed if I ran it, and it will install tensorflow-2.16.1-cp311-cp311-manylinux_2_17_x86_64.manylinux2014_x86_64.whl so I did NOT run the actual install command. I MAY do that some later time if I think it will be useful. Another consideration is to create another conda environment for any and all Tensorflow/TRAX related notebooks. 

Hmm actually, what I am going to do is this ... I am going to clone this conda environment 't4nlpacv' to 't4nlpacv-2' and then I will install the latest version of Tensorflow and TRAX in that new environment.

 1) mamba create -n t4nlpacv-2 --clone t4nlpacv
 2) mamba activate t4nlpacv-2
 3) pip install tensorflow
 4) pip install -U trax
 5) pip install googletrans==4.0.0-rc1 

## Monday, March 11, 2024

I created a conda environment for this repository:

 1) mamba create -n t4nlpacv python=3.11
 2) mamba activate t4nlpacv
 3) mamba install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
 4) mamba install conda-forge::transformers
 5) mamba install conda-forge::jupyterlab
 6) mamba install conda-forge::ipywidgets
 7) mamba install conda-forge::accelerate
 8) mamba install conda-forge::bitsandbytes
 9) mamba install conda-forge::scikit-learn
10) mamba install conda-forge::matplotlib ... this did not install due to many conflicts ... will address later

Ugh ... I need matplotlib to install, so I am going to try this again, but uninstall scikit-learn first: ...

11) mamba uninstall scikit-learn
12) mamba install conda-forge:scikit-learn==1.2.0
13) mamba install conda-forge::matplotlib ... sigh nope! Still a ton of conflicts! ... whelp, gonna kill this environment, and start over ..

14) mamba env remove -n t4nlpacv

STARTING OVER ....

  1) mamba create -n t4nlpacv python=3.11
  2) mamba activate t4nlpacv
  3) mamba install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
  4) mamba install conda-forge::scikit-learn==1.3.0
  5) mamba install conda-forge::matplotlib
  6) mamba install conda-forge::jupyterlab
  7) mamba install conda-forge::ipywidgets
  8) mamba install conda-forge::pandas

 OK! I am able to run the notebooks from Chapter01! (except for the TensorFlow parts) Nice!

  9) mamba install conda-forge::transformers
 10) mamba install conda-forge::gensim
 11) mamba install conda-forge::nltk
