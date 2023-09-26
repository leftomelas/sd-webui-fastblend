# FastBlend Extension for Stable-Diffusion-Webui
This is an extension of [Stable-Diffusion-Webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui). You can use this extension to make your video smooth! Let's say goodbye to flicker.

## Installation

1. Open "Extensions" tab.
2. Open "Install from URL" tab in the tab.
3. Enter `https://github.com/Artiprocher/sd-webui-fastblend.git` to "URL for extension's git repository".
4. Press "Install" button.
5. Wait for 5 seconds, and you will see the message "Installed into stable-diffusion-webui\extensions\sd-webui-fastblend. Use Installed tab to restart".
6. Go to "Installed" tab, click "Check for updates", and then click "Apply and restart UI".
7. Enjoy the coherent and fluent videos!

## Example

### Blend

https://github.com/Artiprocher/sd-webui-fastblend/assets/35051019/208d902d-6aba-48d7-b7d5-cd120ebd306d

1. The original video is [here](https://www.bilibili.com/video/BV1K14y1Z7cp/). We only use the first 236 frames.
2. Re-render each frame independently. The parameters are
   1. Prompt: masterpiece, best quality, anime screencap, cute, petite, long hair, black hair, blue eyes, hoodie, breasts, smile, short sleeves, hands, blue bowknot, wind, depth of field, forest, close-up,
   2. Negative prompt: (worst quality, low quality:1.4), monochrome, zombie, (interlocked fingers:1.2), extra arms,
   3. Steps: 20,
   4. Sampler: DPM++ 2M Karras,
   5. CFG scale: 7,
   6. Seed: 3010302656,
   7. Size: 768x512,
   8. Model hash: 4c79dd451a,
   9. Model: aingdiffusion_v90,
   10. Denoising strength: 1,
   11. Clip skip: 2,
   12. ControlNet 0: "Module: tile_resample, Model: control_v11f1e_sd15_tile [a371b31b], Weight: 0.4, Resize Mode: Crop and Resize, Low Vram: False, Threshold A: 1, Guidance Start: 0, Guidance End: 1, Pixel Perfect: True, Control Mode: Balanced",
   13. ControlNet 1: "Module: softedge_pidinet, Model: control_v11p_sd15_softedge [a8575a2a], Weight: 1, Resize Mode: Crop and Resize, Low Vram: False, Processor Res: 512, Guidance Start: 0, Guidance End: 1, Pixel Perfect: True, Control Mode: Balanced",
   14. ControlNet 2: "Module: depth_midas, Model: control_v11f1p_sd15_depth [cfd03158], Weight: 1, Resize Mode: Crop and Resize, Low Vram: False, Processor Res: 512, Guidance Start: 0, Guidance End: 1, Pixel Perfect: True, Control Mode: Balanced",
   15. Version: v1.6.0
3. Open "FastBlend" tab. Upload the original video to "Guide video". Upload the re-rendered video to "Style video". We use the following settings:
   1. Inference mode: Fast mode
   2. Sliding window size: 30
   3. Patch size: 11
   4. Number of iterations: 6
   5. Guide weight: 100.0
   6. GPU ID:0 (You must ensure you have an Nvidia GPU.)
   7. Post-process (contrast): 1.0
   8. Post-process (sharpness): 1.0
4. Click "Run". Wait a minute... (I tested this extension on an Nvidia RTX3060 laptop. It cost about half hours.)
5. Now you have obtained a fluent video. Go to "Extras" to upscale it using "R-ESRGAN 4+ Anime6B".

### Interpolate

https://github.com/Artiprocher/sd-webui-fastblend/assets/35051019/3490c5b4-8f67-478f-86de-f9adc2ace16a
