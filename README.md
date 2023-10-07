# AI-TOD


## Download 

You need to download the following two parts (Part1: xView training set, Part2: part of AI-TOD) and use our end-to-end synthesis tool to generate the complete AI-TOD dataset. (Note the we have released the **complete annotations** of AI-TOD, you only need to **generate images**)
* xView training set. [[Website]](http://xviewdataset.org/#dataset) 
* Part of AI-TOD. [[OneDrive]](https://1drv.ms/u/s!Ao5UiAkIbGJ7xHCGhQe2tsU1Ut5i?e=SrUdYp)
* E2E aitodtoolkit. [[Folder]](aitodtoolkit)

<!-- * AI-TOD_wo_xview. [[BaiduDrive(Password:w2dy)]](https://pan.baidu.com/s/1AlhHIxpvkJ1-2ql9JdWqKg) [[OneDrive]](https://1drv.ms/u/s!Ao5UiAkIbGJ7xHCGhQe2tsU1Ut5i?e=SrUdYp) -->
<!-- You can download the dataset on [Google Drive](https://drive.google.com/drive/folders/1mokzFtLCjyqalSEajYTUmyzXvOHAa4WX?usp=sharing) or [Baidu Drive](https://pan.baidu.com/s/1r2C_fBwQL4q2NRmDM3-RUw) (Password: 0ire). -->

## A Guide on Generating AI-TOD
**Step 1:** Download the xView training set, AI-TOD without xview, and clone the aitodtoolkit.

```
git clone https://github.com/SaShukla090/AI-TOD_data_generation.git
```

**Step 2:** Organize the downloaded files in the following way.

```
├─aitod
│  ├─annotations ## put the downloaded annotations of AI-TOD_wo_xview (.json)
│  └─images ## unzip the downloaded AI-TOD_wo_xview image sets, put them (.png) in the corresponding folder
│      ├─test ## directly put the images in it without extra folder
│      ├─train 
│      ├─trainval 
│      └─val 
├─aitod_xview ## here are six files (.txt)
├─xview
│  ├─ori
│  │   └─train_images ## unzip the downloaded xView training set images, put them (.tif) here
│  └─xView_train.geojson ## the annotation file of xView training set
└─generate_aitod.py ## end-to-end tool
```

**Step 3:** Install required packages.

* Required environment (make the conda env using using 'data/aitod/AI-TOD/conda_env_aitod.yml' file)
```
conda env create -f conda_env_aitod.yml
conda activate aitod
pip install -r requirements.txt
```

* [mmcv](https://github.com/open-mmlab/mmcv)  install mmcv==1.0 (don't isntall mmcv 2.0 version which is default)

```
pip install mmcv==1.0.0 -f https://download.openmmlab.com/mmcv/dist/cu118/torch2.0/index.html
```





**Step 4:** Run the E2E aitodtoolkit and get AI-TOD, it might take around an hour, then the full image sets of AI-TOD can be found in the **aitod** folder. And you can delete other files in other folders to avoid taking up too much space.

```
python generate_aitod_imgs.py
```


## Evaluation
Training, Validation and Testing sets are both publicly available now. We report the COCO style performance in the original paper, you can use the [cocoapi-aitod](https://github.com/jwwangchn/cocoapi-aitod) to evaluate the model performance.


## Citation

If you use this dataset in your research, please consider citing these papers.

```
@inproceedings{AI-TOD_2020_ICPR,
    title={Tiny Object Detection in Aerial Images},
    author={Wang, Jinwang and Yang, Wen and Guo, Haowen and Zhang, Ruixiang and Xia, Gui-Song},
    booktitle=ICPR,
    pages={3791--3798},
    year={2021},
}
```

```
@article{NWD_2021_arXiv,
  title={A Normalized Gaussian Wasserstein Distance for Tiny Object Detection},
  author={Wang, Jinwang and Xu, Chang and Yang, Wen and Yu, Lei},
  journal={arXiv preprint arXiv:2110.13389},
  year={2021}
}
```
## Reference
[xView Dataset](http://xviewdataset.org/)

## License

The AI-TOD dataset is licensed under the Attribution-NonCommercial-ShareAlike 4.0 International ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)). Thus AI-TOD dataset are freely available for academic purpose or individual reserach, but restricted for commercial use. Besides, the underlying codes are licensed under the MIT license.
