# GS Methods Information

From several GS methods that have been proposed in the past, a subset was selected according to the synthesis performance, training and synthesis speed, and suitability to the considered scene classes:

| GS Method                                                           | Description |
|:--------------------------------------------------------------------:|:------------|
| [3DGS](https://github.com/graphdeco-inria/gaussian-splatting)        | Proposes a novel explicit radiance field representation using anisotropic 3D Gaussians to model a scene’s radiance field. Each Gaussian is parameterized by its position, rotation, scale, opacity, and Spherical Harmonics (SH) coefficients, enabling efficient view-dependent color rendering. The method employs a tile-based rasterizer and an adaptive density control mechanism that dynamically adjusts the number and distribution of Gaussians. This groundbreaking approach enables high-quality novel view synthesis while ensuring considerably faster training and rendering regarding NeRF methods. |
| [Mip-Splatting](https://github.com/autonomousvision/mip-splatting)   | Proposes a solution for aliasing and high-frequency artifacts that occur in 3DGS rendering when changing sampling rates (e.g., zooming in/out). It introduces two key improvements: a 3D smoothing filter to suppress high-frequency artifacts when zooming in, and a 2D MIP filter that replaces traditional dilation with a Mipmap-like approach, for alias-free rendering at different scales. These modifications improve visual quality and robustness across varying resolutions while maintaining real-time performance. |
| [LightGaussian](https://github.com/VITA-Group/LightGaussian)         | Proposes a Gaussian pruning and recovery strategy to reduce redundancy while preserving visual quality. A distillation process is used to obtain a more compact representation, reducing SH coefficients to a lower degree. Furthermore, vector quantization is applied on the Gaussian parameters reducing precision for less significant features. These techniques reduce the model size and boosts the speed of 3DGS. |
| [Scaffold-GS](https://github.com/city-super/Scaffold-GS)             | Proposes a structured approach by using anchor points to distribute local Gaussians. These anchors are placed in a sparse voxel grid and adapt dynamically based on viewing direction and distance, allowing efficient rendering with fewer primitives. Anchor growing and pruning strategies reduce redundant Gaussians and enhance rendering quality, particularly in scenes with diverse levels of detail (LOD) and view-dependent observations. |
| [EAGLES](https://github.com/Sharath-girish/efficientgaussian)        | Proposes quantized embeddings to compress the color and rotation parameters of each Gaussian, decreasing the overall memory storage. Additionally, it employs a coarse-to-fine training strategy to enhance optimization stability and convergence speed. A pruning stage is also incorporated to remove redundant Gaussians. Collectively, these strategies enable EAGLES to achieve faster training speeds than 3DGS, while maintaining high-quality results. |
| [SOG](https://github.com/fraunhoferhhi/Self-Organizing-Gaussians)    | Proposes a method to organize Gaussian parameters into a 2D grid enabling efficient use of image codecs. A parallel linear assignment sorting algorithm arranges Gaussians efficiently, preserving their neighborhood structure, thus improving compression performance. By enforcing local smoothness between the sorted parameters in the 2D grid during training, it further enhances rendering quality. |
| [Octree-GS](https://github.com/city-super/Octree-GS)                 | Proposes a LOD structured approach that organizes Gaussians within an octree structure, enabling adaptive rendering for large scenes with complex details. The method dynamically selects the appropriate LOD based on the camera view, achieving consistent real-time rendering performance across scenes of varying complexity. |

The table above presents a summarized description of each selected GS method. All methods have been applied to all scenes.


# References

[1] B. Kerbl, G. Kopanas, T. Leimkuehler, and G. Drettakis, “3D Gaussian Splatting for Real-Time Radiance Field Rendering,” ACM Trans Graph, vol. 42, no. 4, Art. no. 4, Jul. 2023.

[2] Z. Yu, A. Chen, B. Huang, T. Sattler, and A. Geiger, “Mip-Splatting: Alias-free 3D Gaussian Splatting,” in Proc. IEEE/CVF Conf. Comput. Vis. Pattern Recognit. (CVPR), Seattle, WA, USA, Jun. 2024, pp.
19447–19456.

[3] Z. Fan, K. Wang, K. Wen, Z. Zhu, D. Xu, and Z. Wang, “LightGaussian: Unbounded 3D Gaussian Compression with 15x Reduction and 200+ FPS,” Nov. 12, 2024, arXiv:2311.17245 [cs.CV]: arXiv:2311.17245 [cs.CV].

[4] T. Lu et al., “Scaffold-GS: Structured 3D Gaussians for View-Adaptive Rendering,” in Proc. IEEE/CVF Conf. Comput. Vis. Pattern Recognit. (CVPR), Seattle, WA, USA, Jun. 2024, pp. 20654–20664.

[5] S. Girish, K. Gupta, and A. Shrivastava, “EAGLES: Efficient Accelerated 3D Gaussians with Lightweight EncodingS,” in Eur. Conf. Comput. Vis. (ECCV), Berlin, Heidelberg, Nov. 2024, pp. 54–71.

[6] W. Morgenstern, F. Barthel, A. Hilsmann, and P. Eisert, “Compact 3D Scene Representation via Self-Organizing Gaussian Grids,” in Eur. Conf. Comput. Vis. (ECCV), A. Leonardis, E. Ricci, S. Roth, O. Russakovsky, T. Sattler, and G. Varol, Eds., Berlin, Heidelberg, Nov. 2024, pp. 18–34.

[7] K. Ren et al., “Octree-GS: Towards Consistent Real-time Rendering with LOD-Structured 3D Gaussians,” Oct. 17, 2024, arXiv:2403.17898 [cs.CV]: arXiv:2403.17898 [cs.CV].