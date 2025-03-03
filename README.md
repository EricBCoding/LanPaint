# LanPaint

Powerful Training Free Inpainting Tool Works for Every SD Model. Official Implementation of "Lanpaint: Training-Free Diffusion Inpainting with Exact and Fast Conditional Inference".

## Features

- 🎨 **Zero-Training Inpainting** - Works immediately with ANY SD model, even custom models you've trained yourself
- 🛠️ **Simple Integration** - Same workflow as standard ComfyUI KSampler
- 🚀 **Quality Enhancements** - High quality and seamless inpainting

## Example Results

### Example 1 (LanPaint K Sampler)
![Inpainting Result 1](https://github.com/scraed/LanPaint/blob/master/examples/InpaintChara_04.jpg)  
[View Workflow & Masks](https://github.com/scraed/LanPaint/tree/master/examples/Example_1) 
[Model Used in This Example](https://civitai.com/models/1188071?modelVersionId=1408658) 
### Example 2: (LanPaint K Sampler (Advanced))
![Inpainting Result 2](https://github.com/scraed/LanPaint/blob/master/examples/InpaintChara_05.jpg)  
[View Workflow & Masks](https://github.com/scraed/LanPaint/tree/master/examples/Example_2)
[Model Used in This Example](https://civitai.com/models/1188071?modelVersionId=1408658)
### Example 3: (LanPaint K Sampler (Advanced))
![Inpainting Result 3](https://github.com/scraed/LanPaint/blob/master/examples/InpaintChara_06.jpg)  
[View Workflow & Masks](https://github.com/scraed/LanPaint/tree/master/examples/Example_3)
[Model Used in This Example](https://civitai.com/models/133005/juggernaut-xl)

Each example includes:
- Original masked image
- Full ComfyUI workflow


## Quickstart

1. **Install ComfyUI**: Follow the official [ComfyUI installation guide](https://docs.comfy.org/get_started) to set up ComfyUI on your system.  
2. **Install ComfyUI-Manager**: Add the [ComfyUI-Manager](https://github.com/ltdrdata/ComfyUI-Manager) for easy extension management.  
3. **Install LanPaint Nodes**:  
   - **Via ComfyUI-Manager**: Search for "LanPaint" in the manager and install it directly.  
   - **Manually**: Click "Install via Git URL" in ComfyUI-Manager and input the GitHub repository link:  
     ```
     https://github.com/scraed/LanPaint.git
     ```  
     Alternatively, clone this repository into the `ComfyUI/custom_nodes` folder.  
4. **Restart ComfyUI**: Restart ComfyUI to load the LanPaint nodes.  

Once installed, you'll find the LanPaint nodes under the "sampling" category in ComfyUI. Use them just like the default KSampler for high-quality inpainting!

## Usage

**Workflow Setup**  
Same as default ComfyUI KSampler - simply replace with LanPaint KSampler nodes. The inpainting workflow is the same as the [SetLatentNoiseMask](https://comfyui-wiki.com/zh/comfyui-nodes/latent/inpaint/set-latent-noise-mask) inpainting workflow.

**Note**
LanPaint requires binary masks (values of 0 or 1) without opacity or smoothing. To ensure compatibility, set the mask's **opacity and hardness to maximum** in your mask editor. During inpainting, any mask with smoothing or gradients will automatically be converted to a binary mask.

### Basic Sampler

**LanPaint KSampler**  
Simplified interface with recommended defaults:

- Steps: 50+ recommended
- LanPaint NumSteps: 1-10 (complexity of edits)
- Built-in parameter presets

### Advanced Sampler 

**LanPaint KSampler (Advanced)**  
Full parameter control:
## Key Parameters

| Parameter | Range | Description |
|-----------|-------|-------------|
| `LanPaint_NumSteps` | 0-20 | Reasoning iterations per denoising step ("thinking depth") |
| `LanPaint_Lambda` | 0.1-50 | Content preservation strength (higher = stricter) |
| `LanPaint_StepSize` | 0.0001-0.5 | Convergence speed (higher = faster but riskier) |
| `LanPaint_Beta` | 0.0001-5 | Novelty generation intensity |
| `LanPaint_Friction` | 1-50 | System stability (higher = more stable) |
| `LanPaint_Tamed` | 0-20 | Noise regularization strength |

## Usage Tips

1. **Start Simple** - Begin with basic sampler and default values
2. **Increase Steps** - 50-100 steps recommended for complex edits
3. **Tune Gradually** - Adjust parameters in 10-20% increments
4. **Monitor Stability** - If artifacts appear, increase Friction/Tamed


## Citation

If you use LanPaint in your research or projects, please cite our work:

```bibtex
@misc{zheng2025lanpainttrainingfreediffusioninpainting,
      title={Lanpaint: Training-Free Diffusion Inpainting with Exact and Fast Conditional Inference}, 
      author={Candi Zheng and Yuan Lan and Yang Wang},
      year={2025},
      eprint={2502.03491},
      archivePrefix={arXiv},
      primaryClass={eess.IV},
      url={https://arxiv.org/abs/2502.03491}, 
}
```



