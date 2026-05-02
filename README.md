# Soft-Masked Diffusion Language Models

#### Michael Hersche, Samuel Moor-Smith, Thomas Hofmann, Abbas Rahimi

Accepted as Conference Paper at the Fourteenth International Conference on Learning Representations 2026 [[Paper]](https://openreview.net/forum?id=Gba02UMvrG).

<div align="center">
  <img src='./assets/architecture.png' width="90%"/>
</div>

## 📰 Updates
* **[May 2, 2026]** Checkpoints for language modeling (OWT) released.
* **[Mar 2, 2026]** Initial release.

## Reproducing Results
Please refer to the [Coding](./coding/) and [Language](./language/) folders for experiments with Dream and MDLM, respectively. 

## Checkpoints Language Modeling
Soft-masking checkpoints for language modeling (OpenWebText) can be found in this [Box folder](https://ibm.box.com/s/wy1glqp1a4if4tj0y7ifeascaflvnjjy). 

## Acknowlegement
The coding part was built on top of [Dream-7B](https://github.com/DreamLM/Dream) and the langugae modeling part based on [Duo](https://github.com/s-sahoo/duo) and ReMDM [ReMDM](https://github.com/kuleshov-group/remdm).

## Citation 📚
If you use the work released here for your research, please consider citing our paper:
```
@inproceedings{
hersche_softmasking_2026,
title={Soft-Masked Diffusion Language Models},
author={Hersche, Michael and Moor-Smith, Samuel and Hofmann, Thomas and Rahimi, Abbas},
booktitle={The Fourteenth International Conference on Learning Representations (ICLR)},
year={2026},
url={https://openreview.net/forum?id=Gba02UMvrG}
}
```