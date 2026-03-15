<p align="center">
<h1 align="center">Wan2.2-TI2V-5B-Turbo</h1>
<a href="https://github.com/quanhaol/Wan2.2-TI2V-5B-Turbo"><img src="https://img.shields.io/badge/GitHub-Repository-0066cc.svg" alt="GitHub"></a>
<a href="https://huggingface.co/quanhaol/Wan2.2-TI2V-5B-Turbo"><img src="https://img.shields.io/badge/🤗_HuggingFace-Model-ffbd45.svg" alt="HuggingFace"></a>
<a href="https://huggingface.co/datasets/quanhaol/MagicData"><img src="https://img.shields.io/badge/🤗_HuggingFace-Dataset-ffbd45.svg" alt="HuggingFace"></a>

Wan2.2-TI2V-5B-Turbo is designed for efficient step distillation and CFG distillation based on <a href="https://huggingface.co/Wan-AI/Wan2.2-TI2V-5B"><b>Wan2.2-TI2V-5B</b></a>. 

Leveraging the Self-Forcing framework, it enables 4-step TI2V-5B model training. **Our model can generate 121-frame videos at 24 FPS with a resolution of 1280×704 in just 4 steps, eliminating the need for the CFG trick.**

To the best of our knowledge, Wan2.2-TI2V-5B-Turbo is the **first** open-source repository of the distilled I2V version of Wan2.2-TI2V-5B.

## 🔥Video Demos
The videos below can be reproduced using [examples/example.csv](examples/example.csv).

<table border="0" style="width: 100%; text-align: left; margin-top: 20px;">
  <tr>
      <td>
          <video src="https://github.com/user-attachments/assets/dae5045c-c7a0-4e99-aa1c-e07d2300ea1c" width="100%" controls loop></video>
      </td>
      <td>
          <video src="https://github.com/user-attachments/assets/f6d66a0e-eb8b-4b69-a29f-9d9607c02dda" width="100%" controls loop></video>
      </td>
  </tr>
  <tr>
      <td>
          <video src="https://github.com/user-attachments/assets/0adc81ad-0389-4a06-b362-1078e5b4b564" width="100%" controls loop></video>
      </td>
      <td>
          <video src="https://github.com/user-attachments/assets/dcf860c4-1da7-469c-bd88-0ab8641d400a" width="100%" controls loop></video>
      </td>
  </tr>
  <tr>
      <td>
          <video src="https://github.com/user-attachments/assets/c5478230-2093-4443-8d76-f845675a4331" width="100%" controls loop></video>
      </td>
      <td>
          <video src="https://github.com/user-attachments/assets/661daf97-aff3-4c5d-8912-44696a86a24e" width="100%" controls loop></video>
      </td>
  </tr>
</table>

## 📣 Updates
- `2026/03/15` 🔥Based on our repository, FlashMotion has been accepted to CVPR 2026 and is now released [`here`](https://github.com/quanhaol/FlashMotion)!
- `2026/01/26` 🔥Thanks to [@kijai](https://github.com/kijai) for supporting Wan2.2-TI2V-5B-Turbo in ComfyUI! [Link](https://huggingface.co/Kijai/WanVideo_comfy)
- `2025/08/06` 🔥Wan2.2-TI2V-5B-Turbo has been released [`here`](https://huggingface.co/quanhaol/Wan2.2-TI2V-5B-Turbo).

## 🐍 Installation
Create a conda environment and install dependencies:
```bash
conda create -n wanturbo python=3.10 -y
conda activate wanturbo
pip install -r requirements.txt
pip install flash-attn --no-build-isolation
python setup.py develop
```

## 🚀Quick Start

### Checkpoint Download

```bash
pip install "huggingface_hub[hf_transfer]"
HF_HUB_ENABLE_HF_TRANSFER=1 huggingface-cli download Wan-AI/Wan2.2-TI2V-5B --local-dir wan_models/Wan2.2-TI2V-5B
HF_HUB_ENABLE_HF_TRANSFER=1 huggingface-cli download quanhaol/Wan2.2-TI2V-5B-Turbo --local-dir wan_models/Wan2.2-TI2V-5B-Turbo
```

### DMD Training 
```bash
bash running_scripts/train/Wan2.2/dmd.sh
```
The model was trained for 4,000 iterations under 48 hours using a cluster of 16 A100 GPUs.

### Fewstep Inference
```bash
bash running_scripts/inference/Wan2.2/i2v_fewstep.sh
```

## 🤝 Acknowledgements

We would like to express our gratitude to the following open-source projects that have been instrumental in the development of our project:

- [MagicMotion](https://github.com/quanhaol/MagicMotion)
- [CausVid](https://github.com/tianweiy/CausVid)
- [Self-Forcing](https://github.com/guandeh17/Self-Forcing)
- [Self-Forcing-Plus](https://github.com/GoatWu/Self-Forcing-Plus)
- [Wan2.1](https://github.com/Wan-Video/Wan2.1)
- [Wan2.2](https://github.com/Wan-Video/Wan2.2)

Special thanks to the contributors of these libraries for their hard work and dedication!

## 📚 Contact

If you have any suggestions or find our work helpful, feel free to contact us

Email: liqh24@m.fudan.edu.cn or zhenxingfd@gmail.com or wangrui21@m.fudan.edu.cn

If you find our work useful, <b>please consider giving a star to this github repository and citing it</b>:

```bibtex
@article{li2025magicmotion,
  title={MagicMotion: Controllable Video Generation with Dense-to-Sparse Trajectory Guidance},
  author={Li, Quanhao and Xing, Zhen and Wang, Rui and Zhang, Hui and Dai, Qi and Wu, Zuxuan},
  journal={arXiv preprint arXiv:2503.16421},
  year={2025}
}
```
