# SGF3D : Similarity-guided fusion network for 3D object detection
 This is the official implementation of SGF3D: Similarity-guided fusion network for 3D object detection

## Installation
1. Prepare for the running environment.

    You can refer to the [`OpenPCDet`](https://github.com/open-mmlab/OpenPCDet) to prepare the training environment.
2. Prepare for the data.

    Please prepare KITTI dataset as [`OpenPCDet`](https://github.com/open-mmlab/OpenPCDet). Then download the generated pseudo point cloud from [Baidu](https://ww) (the data is being uploaded)
   Finally, your data should be prepared as follows:
    ```
    SGF3D
    ├── data
    │   ├── kitti_sgf_seguv_twise
    │   │   │── ImageSets
    │   │   │── training
    │   │   │   ├──calib & velodyne & label_2 & image_2 & (optional: planes) & depth_dense_twise & depth_pseudo_rgbseguv_twise
    │   │   │── testing
    │   │   │   ├──calib & velodyne & image_2 & depth_dense_twise & depth_pseudo_rgbseguv_twise
    │   │   │── gt_database
    │   │   │── gt_database_pseudo_seguv
    │   │   │── kitti_dbinfos_train_sgf_seguv.pkl
    │   │   │── kitti_infos_test.pkl
    │   │   │── kitti_infos_train.pkl
    │   │   │── kitti_infos_trainval.pkl
    │   │   │── kitti_infos_val.pkl
    ├── pcdet
    ├── tools
    ```

 You can also generate pseudo point cloud by yourself:
   
   ```
    cd SGF3D
    python depth_to_lidar.py
   ```
## Well-trained weights
   You can download our well-trained weights from [Baidu](https://pan.baidu.com/s/1mDUlFULQZfkv5LR66gp-oA?pwd=cssj) 
   
## Getting Started
1. Training.

    ```
    cd SGF3D/tools
    python train.py --cfg_file cfgs/kitti_models/sgf.yaml
    ```

2. Evaluation.

    ```
    cd SGF3D/tools
    python test.py --cfg_file cfgs/kitti_models/sgf.yaml --ckpt checkpoint_epoch_66.pth
    ```

3. Visualization.

   You can refer to [3D-Detection-Tracking-Viewer]('https://github.com/hailanyi/3D-Detection-Tracking-Viewer') or [3d-object-vis]('https://github.com/DeclK/3d-object-vis) for visualization. Both of these visualization tools are based on [vedo]('https://github.com/marcomusy/vedo').
You can also use Open3D or mayavi for visualization.





