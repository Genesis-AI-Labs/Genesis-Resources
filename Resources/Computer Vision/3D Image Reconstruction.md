# Various Strategies described used in 3D Resconstruction
## Methodology
           

The pipeline for proceeding towards the reconstruction is defined as follows:

The input is a set of images -> First step is to be done is **Camera Pose estimation**, we try to match features sparsely defined between the images correspondingly, and then we solve the bundle adjustment problem which solves for the structure the 3D point location and the camera poses together.

Then we want to have a Dense Correspondences and we do this by shooting a ray for every pixel that projects into lines onto images and then on these lines we find correspondences so we try find the pixel that looks closest to the pixel in the input image by doing this, we get a set of **Depth Maps**. So, for each of the input images we have a depth map.

We now perform Depth Map Fusion to finally render a completed 3D reconstruction using any of the gold standard approaches such as **Curlees & Levoy Volumetric Fusion** and Idea here is to take 2.5D depth maps and projects depth information into the 3D space and then to calculate an implicit surface representation by going through every voxel in the 3D space and measuring distance to the closest surface.

We do this for every input image and their depth maps and fuse all this information by simply averaging the implicit representation and then from that extracting a zero-level set out again which gives you the surface.

**Dataset** : ShapeNet derived from Google Warehouse containing 3D CAD model 	information.

**OctNet** : Learning Deep 3d Representations at High Resolutions (2017)
*Used for Shape Classification*

#### Reconstruction Approaches :
**Volumetric Fusion** -> 

**Pros:**
Fast and Simple but with lot of noise,
**Cons:**
*cannot fill/producse missing spaces*

**TV-L1 Fusion** -> 

**Pros:**
Prior(extremely simple) on surface area, Noise is less, 
**Cons:**
*oversmooths the edges*, *Simplistic Local Prior*, *Cant complete missing surfaces*

**Learned Fusion / OctNet Fusion** ->

**Pros:** 
Learn noise suppression from data
Learn surface completion from data
**Cons:** 
Requires large 3D datasets for training
How to scale to high resolutions?





