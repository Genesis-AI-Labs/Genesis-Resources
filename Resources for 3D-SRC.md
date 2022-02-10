## Resources

Github Repositories and the codes with their respective papers are being listed on **paperswithcode**

Mostly project to be implemented and done by the help of the CoReNet repo by Google Research -> [GitHub Repository](https://github.com/google-research/corenet#readme)

Several Datasets are being used in the paper:
Useful Library -> [Shapenet](https://shapenet.org/)

### Paper Reading 
Following Papers to be read:
[CoReNet](https://arxiv.org/abs/2004.12989)
[The Replica Dataset](https://arxiv.org/pdf/1906.05797v1.pdf)
[MSRF-Net](https://arxiv.org/pdf/2105.07451v2.pdf)

### Usefull frameworks
[Kornia](https://github.com/kornia/kornia) - Differentiable CV lib.

### Models without 3D supervision acting on 2D supervision
1. **PiFu**: Pixel-Aligned implicit Function [PiFu](https://arxiv.org/pdf/1905.05172.pdf)
-> Support multi-view integration
2. **PointRend**: Image segmentation as Rendering -> similar idea as Occupency network to improve results of maskRCNN by having a occupancyNET head that can then be queried to refine the boundaries.
[Code and Paper](https://paperswithcode.com/paper/pointrend-image-segmentation-as-rendering#code)

### Summary
Neural Implicit Models:
- Effective output representation for shape, appearance, material, motion, etc.
- No dicretization, model arbitrary topology
- Can be efficiently learned using 2D supervision
- Many applications: Reconstruction, view synthesis, segmentation, etc.

Challenges: 
- Geometry must be extracted in post-processing step (1-3 seconds for ONet)
- Extension to 4D not straightforward (curse of dimensionality)
- Fully connected architectures and global condition leads to oversmooth results
- Promisings: local features (**ConvONet**, **PiFu**), Better input encoding (**NeRF**)

