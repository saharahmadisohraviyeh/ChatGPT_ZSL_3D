# 3D-Scene-Generation-for-Zero-shot-Learning-using-ChatGPT-guided-Language-Prompts


Supported backbones:
- [x] [PointNet (CVPR'2017)](https://github.com/charlesq34/pointnet)
- [x] [PointConv (CVPR'2019)](https://github.com/DylanWusee/pointconv)
- [x] [EdgeConv (ACM'2019)](https://github.com/WangYueFt/dgcnn)


Supported Datasets:
- [x] [ModelNet40](https://modelnet.cs.princeton.edu/)
- [X] [ScanObjectNN](https://hkust-vgd.github.io/scanobjectnn/)
- [X] [SahpeNet](https://shapenet.org/)



Tasks:
- [x] ZSL + GZSL Pipeline 
- [x] Add Common Augmentations
- [x] Create Combinational Augmentation List and BERT Embeddings
- [x] Add Combinational Augmentations
   - [x] This is a [Object](blue).
   - [x] A big [Object](blue).
   - [x] A small [Object](blue).
   - [x] Two [Object](blue)s.
   - [x] Two close [Object](blue)s.
   - [x] A [ObjectA](blue) is close to [ObjectB](blue).
   - [x] A big [ObjectA](blue) is close to [ObjectB](blue).
   - [x] A small [ObjectA](blue) is close to [ObjectB](blue).
   - [x] [ObjectA](blue) is on [ObjectB](blue).
   - [x] [ObjectA](blue) is under [ObjectB](blue).
- [x] Add ChatGPT Augmentations for each Prompts
- [x] Embedding Visualization
- [x] Hyperparameter Tunning
- [ ] Add Supervised Contrastive Loss





Classification
```python
   # FIXME not working currently
   python train.py --config_path ./configs/pointnet/pointnet_modelnet40.yaml --backbone PointNet
```
```python
   # FIXME not working currently
   python train.py --config_path ./configs/pointconv/pointconv_modelnet40.yaml --backbone PointConv
```
```python
   # FIXME not working currently
   python train.py --config_path ./configs/edgeconv/edgeconv_modelnet40.yaml --backbone EdgeConv
```

Inductive ZSL
```python
   python train_inductive.py --config_path ./configs/pointnet/pointnet_modelnet40.yaml --dataset_eval ModelNet10 --backbone PointNet --alpha_sceneaug 0.9 --verbose --pbar


```
```python
   python train_inductive.py --config_path ./configs/pointnet/pointnet_scanobjectnn.yaml --dataset_eval ScanObjectNN --backbone PointNet --alpha_sceneaug 0.9 --verbose --pbar
```

Tune Inductive ZSL Models
```python
   python tunning_inductive.py --config_path ./configs/pointnet/pointnet_modelnet40.yaml --dataset_eval ModelNet10 --backbone PointNet --alpha_sceneaug 0.9 --verbose --pbar
```
```python
   python train_inductive.py --config_path ./configs/pointnet/pointnet_shapnet44.yaml --dataset_train Shapnet44  --dataset_eval ScanObject15 --backbone PointNet --alpha_sceneaug 0.9  --pbar --bs 64
```
```python
   python tunning_inductive.py --config_path ./configs/pointnet/pointnet_scanobjectnn.yaml --dataset_eval ScanObjectNN --backbone PointNet --alpha_sceneaug 0.9  --pbar --bs 64
```

