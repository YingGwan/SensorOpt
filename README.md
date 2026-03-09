<div align="center">

# Model-Free Co-Optimization of Manufacturable Sensor Layouts and Deformation Proprioception

**Yingjun Tian, Guoxin Fang, Aoran Lyu, Xilong Wang, Zikang Shi, Yuhu Guo, Weiming Wang and Charlie C.L. Wang***

\* *Corresponding Author*

Published in *IEEE Transactions on Robotics* (**T-RO**), 2026

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](https://github.com/YingGwan/SensorOpt/blob/main/TROSensorCoOptm_FinalVer.pdf) &nbsp;&nbsp; [![Code](https://img.shields.io/badge/Code-Github-black)](https://github.com/YingGwan/SensorOpt/tree/main) &nbsp;&nbsp; [![Video](https://img.shields.io/badge/Video-YouTube-red)](https://www.youtube.com/watch?v=dKYubu_igog)

<br>
<hr />
<br>

<h3>✨ <font color="#d9534f">Heuristic Trial-and-Error</font> vs. <font color="#2980b9">Task-Gradient Optimization</font>: Who Wins?</h3>

**Are massive, densely-packed sensor arrays truly better? Does designing them manually via trial-and-error have to be so painstakingly time-consuming?** 🤔

*No! We present a novel simulator-free computational design framework that uses **task gradients** to optimize an initial massive number of random sensors down to a sparse, physics-ready, and highly accurate layout. By encoding strict discrete fabrication rules into **differentiable loss functions**, our method autonomously co-optimizes the sensor layout alongside a shape prediction network via end-to-end gradient descent!* ✨

<br>

<a href="https://youtu.be/dKYubu_igog" target="_blank">
  <img src="https://img.youtube.com/vi/dKYubu_igog/maxresdefault.jpg" alt="Watch the video" width="85%" />
</a>

<br>

</div>

<hr />

## 💡 Motivation
Flexible sensors are increasingly employed in soft robotics and wearable devices to provide proprioception of freeform deformations. To reconstruct large deformations from signals accurately, the **sensor layout**—specifically the number, shape, and placement of sensors—plays a critical role. **More sensors do not equate to better performance**, as redundant sensors needlessly increase fabrication complexity and material interference without actually improving accuracy.

Furthermore, deciding layouts manually using heuristic decision-making involves immense **trial-and-error**. This process is notoriously **time-consuming** and frequently leads to suboptimal prediction accuracy or manufacturing failures. To overcome this, our work introduces a **model-free, data-driven framework** that leverages task-specific gradients to prune and optimize an initial random distribution of sensors. It completely eliminates the need for complex physical simulation models, making it broadly applicable to diverse robotic sensing tasks!

## ⚙️ Method
Our framework concurrently optimizes both the continuous spatial placement and discrete number of flexible sensors alongside neural network parameters for 3D shape prediction. A core novelty of our approach is reformulating inherently discrete fabrication requirements into **differentiable loss functions**. We explicitly incorporate the following practical **manufacturability constraints** into the optimization process:
- **Overlap-free**: Prevents sensors from crossing, avoiding complex accumulation of material layers which introduces wrinkles and degrades sensing accuracy.
- **Inter-sensor distance**: Ensures sufficient spacing to avoid local stiffness discontinuities, stress concentration, and material fatigue on curved surfaces.
- **Length preference**: Controls the maximum and minimum continuous sensor lengths to guarantee signal reliability and fabrication stability.

By parameterizing freeform shapes via B-spline surfaces and mapping sensors as lines in the $(u, v)$-domain, we successfully unify physical manufacturing constraints and predictive accuracy into a single continuous differentiable space.

## 🚀 Results & Applications
We validated the effectiveness and generality of our approach on multiple physical prototypes:
1. **Soft Manipulator**: Reduced the sensors required from an initial 20 to just 6, achieving significantly lower shape prediction errors compared to unoptimized layouts.
2. **Deformation Sensing Wearable (Shoulder)**: Successfully co-optimized 4 compact sensors that accurately predict full shoulder deformations under various motions tracked via MoCap systems.
3. **Deformable Mannequin**: Discovered a 10-sensor optimal layout that substantially outperformed a heuristic layout designed by garment industry experts utilizing the same number of sensors, while strictly maintaining physical constraints.

The optimized layouts not only significantly improve deformation prediction accuracy but are readily physically realizable due to the rigorous embedding of our manufacturability constraints.

## 💻 Code
**Code would be released soon.**

## 📝 Citation
If you find our work useful, please consider citing our paper:
```bibtex
@article{tian2026SensnorOpt,
  title={Model-Free Co-Optimization of Manufacturable Sensor Layouts and Deformation Proprioception},
  author={Tian, Yingjun and Fang, Guoxin and Lyu, Aoran and Wang, Xilong and Shi, Zikang and Guo, Yuhu and Wang, Weiming and Wang, Charlie C.L.},
  journal={IEEE Transactions on Robotics},
  year={2026}
}
```
