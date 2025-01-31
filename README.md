# Conflict-Averse Gradient Descent for Multitask Learning (CAGrad)
This repo contains the source code for CAGrad, which has been accepted to **NeurIPS 2021**.

## Toy Optimization Problem

![Alt Text](https://github.com/Cranial-XIX/CAGrad/blob/main/misc/cagrad.gif)

To run the toy example:
```
python toy.py
```

## Image-to-Image Prediction
The supervised multitask learning experiments are conducted on NYU-v2 and CityScapes datasets. We follow the setup from [MTAN](https://github.com/lorenmt/mtan). The datasets could be downloaded from [NYU-v2](https://www.dropbox.com/sh/86nssgwm6hm3vkb/AACrnUQ4GxpdrBbLjb6n-mWNa?dl=0) and [CityScapes](https://www.dropbox.com/sh/gaw6vh6qusoyms6/AADwWi0Tp3E3M4B2xzeGlsEna?dl=0). After the datasets are downloaded, please follow the respective run.sh script in each folder. In particular, modify the dataroot variable to the downloaded dataset.

**update 2021/11/22:** Thank [@lushleaf](https://github.com/lushleaf) for finding that replacing the last `backward(retain_graph=True)` to  `backward()` saves much GPU memory.

## Multitask Reinforcement Learning (MTRL)
The MTRL experiments are conducted on [Metaworld](https://github.com/rlworkgroup/metaworld) benchmarks. In particular, we follow the [mtrl](https://github.com/facebookresearch/mtrl) codebase and the experiment setup in [this paper](http://proceedings.mlr.press/v139/sodhani21a/sodhani21a.pdf).

1. Install [mtrl](https://github.com/facebookresearch/mtrl) according to the instructions.

2. Git clone [Metaworld](https://github.com/rlworkgroup/metaworld) and change to `d9a75c451a15b0ba39d8b7a8b6d18d883b8655d8` commit (Feb 26, 2021). Install metaworld accordingly.

3. Copy the `mtrl_files` folder under mtrl of this repo to the cloned repo of mtrl. Then
```
cd PATH_TO_MTRL/mtrl_files/ && chmod +x mv.sh && ./mv.sh
```
Then follow the `run.sh` script to run experiments (We are still testing the results but the code should be runnable).


## Citations
If you find our work interesting or the repo useful, please consider citing [this paper](https://arxiv.org/pdf/2110.14048.pdf):
```
@article{liu2021conflict,
  title={Conflict-Averse Gradient Descent for Multi-task Learning},
  author={Liu, Bo and Liu, Xingchao and Jin, Xiaojie and Stone, Peter and Liu, Qiang},
  journal={arXiv preprint arXiv:2110.14048},
  year={2021}
}
```
