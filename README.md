

### data architecture

data
└── nuscenes
    ├── v1.0-trainval (existing)
    ├── v1.0-test (existing)
    ├── sweeps  (existing)
    ├── samples (existing)
    └── gts (new)
    
### checkpoints
ckpt
└── bevdet-occ-r50-4d-stereo-24e.pth
└── bevdet-occ-stbase-4d-stereo-512x1408-24e.pth

### Nuscenes Occupancy
| Config                                                                    | mIOU       | Model | Log                                                                                            |
| ------------------------------------------------------------------------- | ---------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [**BEVDet-Occ-R50-4D-Stereo-2x**](configs/bevdet_occ/bevdet-occ-r50-4d-stereo-24e.py)                                 | 36.1     | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) |
| [**BEVDet-Occ-R50-4D-Stereo-2x-384x704**](configs/bevdet_occ/bevdet-occ-r50-4d-stereo-24e_384704.py)                  | 37.3     | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) |
| [**BEVDet-Occ-R50-4DLongterm-Stereo-2x-384x704**](configs/bevdet_occ/bevdet-occ-r50-4dlongterm-stereo-24e_384704.py)  | 39.3     | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) |
| [**BEVDet-Occ-STBase-4D-Stereo-2x**](configs/bevdet_occ/bevdet-occ-stbase-4d-stereo-512x1408-24e.py)                  | 42.0     | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) | [baidu](https://pan.baidu.com/s/1237QyV18zvRJ1pU3YzRItw?pwd=npe1) |


### generated the test's pkl

python tools/create_data_bevdet.py

### test the 42 mAP model

python tools/test.py ./configs/bevdet_occ/bevdet-occ-stbase-4d-stereo-512x1408-24e.py ./ckpt/bevdet-occ-stbase-4d-stereo-512x1408-24e.pth --format-only --eval-options 'submission_prefix=./occ_submission'


### test the 36 mAP model

python tools/test.py ./configs/bevdet_occ/bevdet-occ-r50-4d-stereo-24e.py ./ckpt/bevdet-occ-r50-4d-stereo-24e.pth --format-only --eval-options 'submission_prefix=./occ_submission'
