# MeshGPT
Implementation for [MeshGPT]("https://arxiv.org/abs/2311.15475") in Pytorch

<img src="./pics/vocab.png" width="450px"></img>

<img src="./pics/GPT2.png" width="450px"></img>

# Details
- Dataset
    - [ShapeNetV2](http://shapenet.cs.stanford.edu/shapenet/obj-zip/ShapeNetCore.v2.zip), 55 categories.
    - Chair, Table, Bench, Lamp as test data.
    - Preprocess
        - Planar Decimation
            - Blender
            - $\alpha \in [1,60]$
            - Hansdorff distance $d \lt \delta_{hansdorff}$
        - Filter
            - $\leq$ 800 faces
            - resulting in 28980 in data size.
        - Normalization
            - centered at origin
            - longest side = 1
        - Augmentation
            - Scaling [0.75, 1.25], then normalize
            - Jitter shift [-0.1, 0.1]
            - Planar Decimation, varying levels

- Training
- Model