# Learning to Predict Layout-to-image Conditional Convolutions for Semantic Image Synthesis


############################################
############################################

Small revision for using this code at windows.

[xh-liu's original code](https://github.com/xh-liu/CC-FPSE) was for linux with 16 GPUs.

But currently torch.distributed does not support windows.

So I edit some option to use it.


Some options who are related to torch.distributed are deleted.

Some options such as "gpu_ids", "save_latest_freq" revived.(Options of SPADE)


Below is my training command.

```bash
python train_spade.py --name coco_test --dataroot D:\Sanghun\SPADE\datasets\coco_stuff --batchSize 2 --ngpus_per_node 2 --gpu_ids 0,1
```

############################################
############################################




[Xihui Liu](https://xh-liu.github.io),  [Guojun Yin](https://gjyin91.github.io/), [Jing Shao](https://amandajshao.github.io/), [Xiaogang Wang](https://www.ee.cuhk.edu.hk/~xgwang/) and [Hongsheng Li](https://www.ee.cuhk.edu.hk/~hsli/).<br>
Published in NeurIPS 2019.

### [Paper](https://arxiv.org/abs/1910.06809) | [Poster](https://drive.google.com/open?id=10A2HdhI7kzDj3xelsxqlivtPQ3e5pVeQ) | [Slides](https://drive.google.com/open?id=1ocpgYFmRkG_myEMzWu7uFVx7_adJUD4r)


## Installation

Clone this repo.
```bash
git clone https://github.com/xh-liu/CC-FPSE.git
cd CC-FPSE/
```

This code requires PyTorch 1.1+ and python 3+. Please install dependencies by
```bash
pip install -r requirements.txt
```

The results reported in the paper is trained on 16 TITANX GPUs.

## Dataset Preparation

Follow the dataset preparation process in [SPADE](https://github.com/NVlabs/SPADE).

## Generating Images Using Pretrained Model

1. Download the pretrained models from [Google Drive Folder](https://drive.google.com/open?id=1m4JMtKLDfcXCW1HXHKz-fP6y3_SAaUqX), and extract it to 'checkpoints/'.

2. Generate images using the pretrained model with test_coco.sh, test_ade.sh, and test_cityscapes.sh.

3. The outputs images are stored at `./results/[type]_pretrained/` by default. You can view them using the autogenerated HTML file in the directory.

## Training New Models

New models can be trained with train.sh. This is an example of training the model on one machine.


### Citation
If you use this code for your research, please cite our papers.
```
@inproceedings{liu2019learning,
  title={Learning to Predict Layout-to-image Conditional Convolutions for Semantic Image Synthesis},
  author={Liu, Xihui and Yin, Guojun and Shao, Jing and Wang, Xiaogang and Li, Hongsheng},
  booktitle={Advances in Neural Information Processing Systems},
  year={2019}
}
```

## Acknowledgments
This code borrows heavily from [SPADE](https://github.com/NVlabs/SPADE).
