# TIR
This is the official implementation with training code for 'Trajectory Guided Robust Visual Object Tracking with Selective Remedy'.

Introduction
--------------------------------
We propose a fast yet robust tracking algorithm with two light-load novel modules: Trajectory Guidance Module (TGM) and Selective Refinement Module (SRM). Specifically, TGM encourages to pay more attention on possible target location based on historical trajectory. SRM selectively remedies the tracking results at the risk of failure with little impact on the speed. The proposed algorithm can be easily incorporated into existing Siamese trackers and obtains the state-of-the-art performance on six benchmarks with high real-time tracking speed.

Installation
--------------------------
Please refer to [PySOT_INSTALL.md](https://github.com/STVIR/pysot/blob/master/INSTALL.md) and [PreciseRoIPooling_README.md](https://github.com/vacancy/PreciseRoIPooling) for installation.

Due to PreciseRoIPooling, **PLEASE USE THE COMMAND TO DOWNLOADE THE CODE:** ```git clone https://github.com/TJUMMG/TGSR.git```

Requirements
--------------------------
1. Ubuntu 20.04
2. Pytorch 1.3.1
3. Python 3.7


Usage
--------------------------
### Download models and tracking results
[Baidupan](https://pan.baidu.com/s/1lkb6tApeoGKJO4deVWQ8Qw), keyword: 9tu5

The folder has five files:
- result.zip : the tracking result on the six benchmarks
- research.zip : the tracking result for ALTL, should be unzipped to './pioneer/research/'
- snapshot_test.zip : the model of TGSR, should be unzipped to './snapshot_test'
- cxcy_uav123.txt : the training data for TPN, should be unzipped to './pioneer/data/'
- experiments.zip : the model of SiamRPN++ and SiamMask, should be unzipped to './experiments'

### Eval ALTL
1. run the './pioneer/research/eval_tool.py'

### Test
1. Modify the dataset path 'dataset_root'.
2. run the './tools/test_SiamRPN++_VOT.py'.

### Train
1. run the './pioneer/traj_predict_train.py' to train TPN
2. run the './pioneer/IoU_train.py' to train IPN
3. run the './pioneer/Refine_train.py' to train BRN

Acknowledgments
------------------------------
1. [PySOT](https://github.com/STVIR/pysot)
2. [pytracking](https://github.com/visionml/pytracking)
3. [PreciseRoIPooling_README.md](https://github.com/vacancy/PreciseRoIPooling)
4. [DR_Loss](https://github.com/idstcv/DR_loss)
