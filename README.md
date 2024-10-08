# [Edit Temporal-Consistent Videos with Image Diffusion Model (TCVE)](https://arxiv.org/abs/2308.09091)

This repository is the official implementation of TCVE.

## Prerequisites

### Requirements
```shell
pip install -r requirements.txt
```

Installing [xformers](https://github.com/facebookresearch/xformers) is highly recommended for more efficiency and speed on GPUs. 
To enable xformers, set `enable_xformers_memory_efficient_attention=True` (default). 
Please make sure at least 24G GPU memory is available.

### Downloading pretrained Stable Diffusion Model

The pretrained Stable Diffusion models can be downloaded from Hugging Face (e.g., [Stable Diffusion v1-4](https://huggingface.co/CompVis/stable-diffusion-v1-4)).  The downloaded model should be placed in the `./checkpoints`.


## Usage

To edit videos by our TCVE, please run this command:
```bash
accelerate launch video_editing.py --config="configs/surfer-on-wave.yaml"
```
And, the results including well-trained models and edited videos (i.e., `./samples`) are saved in `./output`.

### Citation
If you find the code helpful in your research or work, please cite the following paper.
```
@article{TCVE,
	author = {Wang, Yuanzhi and Li, Yong and Zhang, Xiaoya and Liu, Xin and Dai, Anbo and Chan, Antoni B. and Cui, Zhen},
	title = {Edit Temporal-Consistent Videos with Image Diffusion Model},
	journal = {ACM Transactions on Multimedia Computing, Communications, and Applications}
  	year = {2024}
}
```
