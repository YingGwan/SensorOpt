<div align="center">

# Model-Free Co-Optimization of Manufacturable Sensor Layouts and Deformation Proprioception

**Yingjun Tian, Guoxin Fang, Aoran Lyu, Xilong Wang, Zikang Shi, Yuhu Guo, Weiming Wang and Charlie C.L. Wang***

\* *Corresponding Author*

Published in *IEEE Transactions on Robotics* (**T-RO**), 2026

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](https://github.com/YingGwan/SensorOpt/blob/main/TROSensorCoOptm_FinalVer.pdf)[![Code](https://img.shields.io/badge/Code-Github-black)](https://github.com/YingGwan/SensorOpt/tree/main)[![Video](https://img.shields.io/badge/Video-YouTube-red)](https://www.youtube.com/watch?v=dKYubu_igog)



## 💡 Motivation
Flexible sensors are increasingly employed in soft robotics and wearable devices to provide proprioception of freeform deformations. To reconstruct large deformations from sensor signals accurately, the **sensor layout**—specifically the number, shape, and placement of sensors—plays a critical role. However, prior designs typically rely on heuristics, trial-and-error, or expert intuition, leading to suboptimal prediction accuracy and potential manufacturing failures. 

This work introduces a **model-free, data-driven computational pipeline** that jointly **optimizes the sensor layout (number, length, and placement) **and the **deformation prediction network**. Unlike model-based approaches, our method relies solely on datasets of deformed shapes without requiring any physical simulation models, making it broadly applicable to diverse robotic sensing tasks!

## ⚙️ Method
Our framework co-optimizes the continuous spatial placement and discrete number of flexible length-measurement sensors alongside neural network parameters for shape prediction. We explicitly incorporate practical **manufacturability constraints** into the optimization process:
- **Overlap-free**: Prevents sensors from crossing, avoiding complex accumulation of material layers which introduces wrinkles and degrades sensing accuracy.
- **Inter-sensor distance**: Ensures sufficient spacing to avoid local stiffness discontinuities, stress concentration, and material fatigue on curved surfaces.
- **Length preference**: Controls the maximum and minimum continuous sensor lengths to guarantee signal reliability and fabrication stability.

By reformulating these inherently discrete fabrication requirements into **differentiable loss functions**, our pipeline can perform end-to-end gradient-based optimization using standard deep learning frameworks. We parameterize freeform shapes using B-spline surfaces and sensors as lines in the $(u, v)$-domain, unifying physical constraints and predictive accuracy into a single continuous differentiable space.

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
