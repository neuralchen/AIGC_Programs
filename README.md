# AIGC Programs
Introduction to AIGC Projects

# 1. 视频换衣
### 主要内容：
实现高时序一致性（包括衣服的一致性、人脸、四肢）的换衣视频生成或者直接替换视频中人物的衣物。
现有的视频换衣大多直接沿用了[Animate Anyone](https://arxiv.org/abs/2311.17117)中的ReferenceNet结构，存在稳定性较差、时序抖动严重，人脸、衣服一致性差等问题，并且生成过程中资源开销较大。其生成的时间窗口或称image token数较低，无法生成长时间（超过30秒以上）的高一致性视频。

### 前置知识：
Diffusion Models、Video Generation and Editing、Human Image Animation

### 参考文献：
[1. MIMO: Controllable Character Video Synthesis with Spatial Decomposed Modeling](https://arxiv.org/abs/2409.16160)

[2. ViViD: Video Virtual Try-on using Diffusion Models](https://arxiv.org/abs/2405.11794)

[3. Try-on: Excavating Spatial-temporal Tunnels for High-quality Virtual Try-on in Videos](https://arxiv.org/abs/2404.17571)

[4. AnyFit: Controllable Virtual Try-on for Any Combination of Attire Across Any Scenario](https://arxiv.org/abs/2405.18172)

[5. A Recipe for Scaling up Text-to-Video Generation with Text-free Videos](https://arxiv.org/abs/2312.15770)

# 2. Animatable Single-Image 3D Avatar Reconstruction
### 主要内容：
从单图人体输入图实现可驱动的人体重建，同时要求重建出的人体具有高清晰度的纹理材质。
现有的单图人体重建大多关注于更精确的几何表面重建，通常利用multi-view diffusion模型幻想出两个视角或四个视角的图像，然后通过“脑补”的图像估计出人体的SDF或隐式表面，最后还原出高细节的人体Mesh。
但在实践中发现，这种pipeline构建出的mesh难以实现高精度的骨骼绑定（rigging），更有甚者无法实现骨骼绑定，从而导致现有单张图重建方法在animation层面上存在较大困难与挑战。

### 前置知识：
Diffusion Models、Video Generation and Editing、SMPL、Single-Image Human Reconstruction

### 参考文献：

[1. SIFU: Side-view Conditioned Implicit Function for Real-world Usable Clothed Human Reconstruction](https://arxiv.org/abs/2312.06704)

[2. SiTH: Single-view Textured Human Reconstruction with Image-Conditioned Diffusion](https://arxiv.org/abs/2311.15855)

[3. Semantic Human Mesh Reconstruction with Textures](https://arxiv.org/abs/2403.02561)

[4. Edify 3D: Scalable High-Quality 3D Asset Generation](https://arxiv.org/abs/2411.07135)

[5. CharacterGen: Efficient 3D Character Generation from Single Images with Multi-View Pose Canonicalization](https://arxiv.org/abs/2402.17214)

# 3.

# 4.



### 相关信息

任何问题请邮件：[xuanhong chen](mailto:chenxuanhongzju@outlook.com)

对研究项目感兴趣的同学也可以邮件咨询，欢迎对于***虚拟人***、***电影换脸***、***人脸重建***、***AIGC***感兴趣的同学前来咨询。

## 相关链接：
- https://github.com/neuralchen/SimSwap
- https://github.com/neuralchen/SimSwapPlus
- (***AIGC入门教程，强烈建议***) https://github.com/neuralchen/NeuralRenderingTutorial
