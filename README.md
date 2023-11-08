# Edit Temporal-Consistent Videos with Image Diffusion Model (TCVE)

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

## Limitations and Failure case.

While our method showcases commendable outcomes, it is not without its limitations. Specifically, during the execution of intricate editing tasks such as simultaneous alterations of style, objects, and backgrounds, our method may yield less satisfactory results, as shown below. In this case, only two cows are changed to two sheep, but the style and background can not be edited successfully. 

<div align=center><img src="failure case.png" width="100%"></img></div>

This could be attributed to the fact that the text conditioning embedding stems from the CLIP text encoder, which aligns predominantly with image-based embeddings and may not seamlessly correspond with video samples. A potential solution is to use an additional video-based CLIP model as text embedding. This avenue of research is left as future work.
