# SOF-VSR (Super-resolving Optical Flow for Video Super-Resolution)
Pytorch implementation of "Learning for Video Super-Resolution through HR Optical Flow Estimation", ACCV 2018.

[[arXiv]](http://arxiv.org/abs/1809.08573)

## Overview
![overview](./Figs/overview.png)

Figure 1. Overview of our SOF-VSR network.

<img width="500" src="https://github.com/LongguangWang/SOF-VSR/blob/master/Figs/temporal_profiles.png"/></div>

Figure 2. Comparison with the state-of-the-arts.

## Requirements
- Python 3
- pytorch (0.4), torchvision (0.2)
- numpy, PIL
- Matlab (For PSNR/SSIM evaluation)

## Datasets
We use the Vid4 dataset and a subset of the DAVIS dataset (namely, DAVIS-10) for benchmark test.
- [Vid4](https://pan.baidu.com/s/1q947P3mvPaOjTZ5f1kXoTg)
- [DAVIS-10](https://davischallenge.org/)  
We use 10 scenes in the DAVIS-2017 test set including boxing, demolition, dive-in, dog-control, dolphins, kart-turn, ocean-birds, pole-vault, speed-skating and wings-trun.

## Test
Currently, we release our code for testing. We provide the pretrained model for 4x SR on BI degradation model. Note that we made some modifications to the original code and it should produce comparable or even better results.

- Run on CPU:
```bash
python demo_Vid4.py --video_name calendar --upscale_factor 4
```

- Run on GPU:
```bash
python demo_Vid4.py --video_name calendar --upscale_factor 4 --gpu_mode True
```

You can download [Vid4](https://pan.baidu.com/s/1q947P3mvPaOjTZ5f1kXoTg) dataset and unzip in `data` directory. Then you can test our network on other scenes.
## Results
![Vid4](./Figs/results_Vid4.png)

Figure 3. Comparative results achieved on the Vid4 dataset. Zoom-in regions from left to right: IDNnet, VSRnet, TDVSR, our SOF-VSR, DRVSR and our SOF-VSR-BD. 

![DAVIS-10](./Figs/results_DAVIS.png)

Figure 4. Comparative results achieved on the DAVIS-10 dataset. Zoom-in regions from left to right: IDNnet, VSRnet, our SOF-VSR, DRVSR and our SOF-VSR-BD. 

![temporal_profiles](./Figs/temporal_profiles.gif)

Figure 5. Visual comparison of 4x SR results. From left to right: VSRnet, TDVSR, our SOF-VSR and the groundtruth.

## Citation
```
@InProceedings{2018-LearningforVideoSuperResolutionthroughHROpticalFlowEstimation-LongguangWang--,
  author    = {Longguang Wang and Yulan Guo and Zaiping Lin and Xinpu Deng and Wei An},
  title     = {Learning for Video Super-Resolution through {HR} Optical Flow Estimation},
  booktitle = {ACCV},
  year      = {2018},
}
```
## Contact
For questions, please send an email to wanglongguang15@nudt.edu.cn
