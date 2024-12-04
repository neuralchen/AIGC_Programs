# AIGC Programs

# 1. 视频换衣
### 主要内容：
实现高时序一致性（包括衣服的一致性、人脸、四肢）的换衣视频生成或者直接替换视频中人物的衣物。
现有的视频换衣大多直接沿用了[Animate Anyone](https://arxiv.org/abs/2311.17117)中的ReferenceNet结构，存在稳定性较差、时序抖动严重，人脸、衣服一致性差等问题，并且生成过程中资源开销较大。其生成的时间窗口或称image token数较低，无法生成长时间（超过30秒以上）的高一致性视频。

### 前置知识：
Diffusion Models、Video Generation and Editing、Human Image Animation

### 参考文献：
1. [MIMO: Controllable Character Video Synthesis with Spatial Decomposed Modeling](https://arxiv.org/abs/2409.16160)

2. [ViViD: Video Virtual Try-on using Diffusion Models](https://arxiv.org/abs/2405.11794)

3. [Try-on: Excavating Spatial-temporal Tunnels for High-quality Virtual Try-on in Videos](https://arxiv.org/abs/2404.17571)

4. [AnyFit: Controllable Virtual Try-on for Any Combination of Attire Across Any Scenario](https://arxiv.org/abs/2405.18172)

5. [A Recipe for Scaling up Text-to-Video Generation with Text-free Videos](https://arxiv.org/abs/2312.15770)

# 2. Animatable Single-Image 3D Avatar Reconstruction
### 主要内容：
从单图人体输入图实现可驱动的人体重建，同时要求重建出的人体具有高清晰度的纹理材质。
现有的单图人体重建大多关注于更精确的几何表面重建，通常利用Multi-View Diffusion模型幻想出两个视角或四个视角的图像，然后通过“脑补”的图像估计出人体的SDF或隐式表面，最后还原出高细节的人体Mesh。
但在实践中发现，这种pipeline构建出的Mesh难以实现高精度的骨骼绑定（Rigging），更有甚者无法实现骨骼绑定，从而导致现有单张图重建方法在Animation层面上存在较大困难与挑战。

### 前置知识：
Diffusion Models、SMPL、Single-Image Human Reconstruction

### 参考文献：

1. [SIFU: Side-view Conditioned Implicit Function for Real-world Usable Clothed Human Reconstruction](https://arxiv.org/abs/2312.06704)

2. [SiTH: Single-view Textured Human Reconstruction with Image-Conditioned Diffusion](https://arxiv.org/abs/2311.15855)

3. [Semantic Human Mesh Reconstruction with Textures](https://arxiv.org/abs/2403.02561)

4. [Edify 3D: Scalable High-Quality 3D Asset Generation](https://arxiv.org/abs/2411.07135)

5. [CharacterGen: Efficient 3D Character Generation from Single Images with Multi-View Pose Canonicalization](https://arxiv.org/abs/2402.17214)

6. [V3D: Video Diffusion Models are Effective 3D Generators](https://arxiv.org/abs/2403.06738)

# 3. 面向单目视频3DGS人体重建的数据增广训练技术
### 主要内容：
利用Pose可控的人体视频生成模型对In-the-wild的单目视频实现pose增广，利用增广后的数据来提升单目视频3DGS人体重建的质量及稳定性。
目前，针对单目视频的3D Gaussian Splatting (3DGS)人体重建技术存在对输入数据敏感问题，特别是对In-the-wild的视频输入重建成功率较低。
这由多方面原因造成：首先，重建通常依赖事先的SMPL人体参数模型估计精度，估计精度差往往会导致高斯球优化困难、空洞、漂浮高斯球等问题。
其次，输入的in-the-wild视频存在拍摄方式、拍摄角度不理想，人体动作单调等特点，这将导致数据的可用信息不足，无法给重建过程提供充足的视角、pose信息，最终导致重建失败或结果不理想。
实践过程中发现，利用SOTA的单目3DGS重建手段（例如：[HUGS](https://arxiv.org/abs/2311.17910)）对youtube下载的视频进行人体重建，重建结果的可用率不高于30%，这也反映了目前的重建手段对于in-the-wild的数据适应性较差，存在极大的改进空间。
前者一般通过引入更精确的人体关键点来解决，后者目前还未见理想的解决方案。本课题目标是用视频生成模型对3DGS的重建过程提供一定的生成能力来改善这一现状。


### 前置知识：
Diffusion Models、SMPL、Monocular Video Human Reconstruction

### 参考文献：

1. [HUGS: Human Gaussian Splats](https://arxiv.org/abs/2311.17910)

2. [HAHA: Highly Articulated Gaussian Human Avatars with Textured Mesh Prior](https://arxiv.org/abs/2404.01053)

3. [Expressive Whole-Body 3D Gaussian Avatar](https://arxiv.org/abs/2407.21686)

4. [3D Gaussian Splatting for Real-Time Radiance Field Rendering](https://arxiv.org/abs/2308.04079)

5. [Score-Guided Diffusion for 3D Human Recovery](https://arxiv.org/abs/2403.09623)


### 相关信息

任何问题请邮件：[xuanhong chen](mailto:chenxuanhongzju@outlook.com)

对研究项目感兴趣的同学也可以邮件咨询，欢迎对于***虚拟人***、***电影换脸***、***人脸重建***、***AIGC***、***AI for Science***感兴趣的同学前来咨询。

## 相关链接：
- https://github.com/neuralchen/SimSwap
- https://github.com/neuralchen/SimSwapPlus
- (***AIGC入门教程，强烈建议***) https://github.com/neuralchen/NeuralRenderingTutorial
