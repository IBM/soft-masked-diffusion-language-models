# Language Modeling with Soft-Masked Diffusion Language Models

## 🔧 Requirements 

### Install Dependencies
To get started, create a conda environment containing the required dependencies.

```bash
conda create -n sm-env python=3.12
conda activate sm-env
conda install nvidia/label/cuda-12.4.0::cuda-toolkit
pip install -r requirements.txt
pip install flash_attn==2.7.4.post1 --no-build-isolation
```

We use **Weights & Biases** (W&B) to track training runs. To install and authenticate W&B, run:

```bash
pip install wandb
wandb login
```

### Download and Apply Patches
To download and apply patches to files which are directly used from DUO, please run the following bash script: 
``` bash
bash setup.sh
```

## Checkpoints Language Modeling
You can download the pretrained soft-masking checkpoints for language modeling (OpenWebText) from this [Box folder](https://ibm.box.com/v/soft-masked-dlm-checkpoints). They contain models in the iso-compute and iso-update regimes, both with pretraining continuation or training from scratch. 

## 🏋️‍♀️ Training the Models

For training continuation, you have to first download the binary MDLM from this [Google drive folder](https://drive.google.com/drive/folders/16LuuptK7Xfk-vzhQYZBZ0SA-B-BFluau?usp=sharing) and specify the checkpoint's location in the [training script](./scripts/01_sm_pretraining_cont_owt.sh). Then, run

```bash
./scripts/01_sm_pretraining_cont_owt.sh
```

To train SM on OWT from scratch, run the following script:
```bash
./scripts/02_sm_pretraining_scratch_owt.sh
```


## 📊 Evaluation

For unconstrained generation experiments, specify the checkpoint's location in the [evaluation script](./scripts/03_gen_ppl_owt_mdlm_sm.sh). For standard MDLM sampling `NFE` number of evaluations, run
```bash
./scripts/03_gen_ppl_owt_mdlm_sm.sh <NFE>
```
The generated samples as well as the metrics (generative perplexity, entropy, MAUVE) are in the `generations` folder. 

For experimenting with REMDM, run 
```bash
./scripts/04_gen_ppl_owt_remdm_cap_sm.sh <NFE>
```
for `NFE` in 128, 256, and 512. For `NFE=1024`, run 

```bash
./scripts/05_gen_ppl_owt_remdm_loop_sm.sh 1024
```


## Acknowledgements
This part of the repository was built on top of [Duo](https://github.com/s-sahoo/duo) and ReMDM [ReMDM](https://github.com/kuleshov-group/remdm). 

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
