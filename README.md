# Finetune-SVD
Finetune stable video diffusion(`image-to-video` model).

## SVD-MV(Multi-View Generation)
| Init Image        | Before Fine-tuning |After Fine-tuning |
|---------------|-----------------------------|-----------------------------|
| ![demo](https://github.com/wangqiang9/Finetune-SVD/blob/main/data/1.jpg)    | ![ori](https://github.com/wangqiang9/Finetune-SVD/blob/main/data/1.gif)   | ![ft](https://github.com/wangqiang9/Finetune-SVD/blob/main/data/11cdaf2939502622815a10e5a35009c9%20(1).gif)|

The original dataset is ShapeNet, and the method for processing it into videos is referenced [binvox_rw](https://github.com/wangqiang9/binvox_rw). I processed 1k image-to-3D datasets and attempted to finetune the effect of reproducing SVD-MV. I am trying to add more datas to train and opensource it up in the future.

## Text-to-Video
I Trained on the `WebVid-10M` dataset and obtained in the `text-to-video` model, replace text embeddings that are fed into the base model with the CLIP image embedding of the conditioning.
| Prompt        | Result Video |
|---------------|-----------------------------|
| Pine trees forest in winter, view from above | ![demo1](https://github.com/wangqiang9/Finetune-SVD/blob/main/data/10032980_Pine_trees_forest_in_winter%2C_view_from_above.gif) |
| Aerial united kingdom loch_lomond, loch lomond | ![demo2](https://github.com/wangqiang9/Finetune-SVD/blob/main/data/10058684_Aerial_united_kingdom-loch_lomond_2005__loch_lomond.gif) |
| shocking aerial of devastation from the 2017 santa rosa tubbs fire disaster which destroyed whole neighborhoods | ![demo3](https://github.com/wangqiang9/Finetune-SVD/blob/main/data/1006603312_Santa_rosa%2C_ca_-_circa_2010s_-_shocking_aerial_of_devastation_from_the_2017_santa_rosa_tubbs_fire_disaster_which_destroyed_whole_neighborhoods..gif) |

## Datasets
The `train.csv` file format is as follows:
```
video_path
...
```

## Installation
```
conda create -n finetune_svd python=3.8
conda activate finetune_svd
pip install -r requirements.txt
```

## Train
```
python train.py
```

# Acknowledgements
* [diffusers](https://github.com/huggingface/diffusers)
* [Text-To-Video-Finetuning](https://github.com/ExponentialML/Text-To-Video-Finetuning)

## Contact
If you have any questions about the code, please contact wanqqiang@bupt.edu.cn 
