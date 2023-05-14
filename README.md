

data architecture

data
└── nuscenes
    ├── v1.0-trainval (existing)
    ├── v1.0-test (existing)
    ├── sweeps  (existing)
    ├── samples (existing)
    └── gts (new)
ckpt
└── bevdet-occ-r50-4d-stereo-24e.pth
└── bevdet-occ-stbase-4d-stereo-512x1408-24e.pth




### generated the test's pkl

python tools/create_data_bevdet.py

### test the 42 mAP model

python tools/test.py ./configs/bevdet_occ/bevdet-occ-stbase-4d-stereo-512x1408-24e.py ./ckpt/bevdet-occ-stbase-4d-stereo-512x1408-24e.pth --format-only --eval-options 'submission_prefix=./occ_submission'


### test the 36 mAP model

python tools/test.py ./configs/bevdet_occ/bevdet-occ-r50-4d-stereo-24e.py ./ckpt/bevdet-occ-r50-4d-stereo-24e.pth --format-only --eval-options 'submission_prefix=./occ_submission'
