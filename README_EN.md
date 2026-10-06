# AUTOMATIC1111 Kaggle Easy

[한국어 README](README.md)

This educational notebook is a **Kaggle port of a Google Colab-based AUTOMATIC1111 workflow**.

It provides a button-based interface for selecting Checkpoints, LoRAs, LyCORIS models, ControlNet models, Embeddings, and VAEs. Required models can be downloaded from Google Drive, CivitAI, or Hugging Face without manually editing URLs in the code.

## Main Features

- Automatic Kaggle GPU and CUDA computation checks
- Automatic Python 3.10 virtual environment setup
- Automatic AUTOMATIC1111 installation
- Simultaneous selection of Checkpoints, LoRAs, ControlNet models, Embeddings, and VAEs
- Automatic model classification from a Google Drive `Auto1111` folder
- Support for CivitAI, Hugging Face, and Google Drive links
- Selective downloading of required models
- Configurable cache limit, automatic cleanup, pinning, and deletion
- WebUI access through a Cloudflare Quick Tunnel
- A new temporary password for every launch
- Password masking, display, and copy controls
- Installation and download cancellation
- ZIP download of generated images
- WebUI and tunnel termination

## Notebook File

```text
AUTOMATIC1111_Kaggle.ipynb
```

## Requirements

- A personal Kaggle account
- A phone-verified Kaggle account
- Available Kaggle GPU quota
- Internet access enabled in the Kaggle Notebook
- At least one Stable Diffusion Checkpoint

Each student should run a separate copy using their own Kaggle account. Do not share the instructor's account or another student's session.

## Quick Start

1. Upload `AUTOMATIC1111_Kaggle.ipynb` to Kaggle or import it from GitHub.
2. Click **Copy & Edit**.
3. Open **Settings** and select **Accelerator → GPU**.
4. Set **Internet → On**.
5. Click **Run All**.
6. Select at least one Checkpoint.
7. Select any required LoRA, ControlNet, Embedding, or VAE models.
8. Click **Apply Selected Models & Launch WebUI**.
9. Wait until the status becomes `5/5 · Ready to Connect`.
10. Click **Open AUTOMATIC1111 WebUI**.
11. Sign in with the username `a1111` and the temporary password shown in the panel.

GPU utilization may remain low or show 0% during installation and downloads. The GPU is mainly used when generating images in the WebUI.

## Google Drive Model Folder

Recommended structure:

```text
Auto1111/
├── checkpoints/
├── Lora/
├── LyCORIS/
├── ControlNet/
├── embeddings/
└── VAE/
```

1. Set the `Auto1111` folder permission to **Anyone with the link → Viewer**.
2. Paste the folder-sharing URL into the **Drive Folder** tab.
3. Click **Load Model List**.

Loading the list reads only filenames and model categories. It does not download every file. Only models selected with **Use** or **Download** are copied to the Kaggle working space.

The notebook does not modify or delete original Google Drive files.

## Individual Model Links

The **File Link** tab supports:

- CivitAI model pages or direct download URLs
- Hugging Face `/resolve/` file URLs
- Individual Google Drive file-sharing URLs

A filename must be entered for an individual Google Drive file.

For gated or private models, the following Kaggle Secrets can be used:

```text
CIVITAI_API_TOKEN
HF_TOKEN
```

Do not store tokens in source code, GitHub, URLs, or Notebook outputs.

## Model Management Buttons

| Button | Function |
|---|---|
| Use | Selects the model for the next WebUI launch |
| Download | Downloads only that model to the Kaggle working space |
| Pin | Protects the model from automatic cleanup |
| Delete | Deletes only the Kaggle copy |
| Cancel Task | Cancels an installation or download task |
| Apply Selected Models & Launch WebUI | Connects the selected models and launches the WebUI |
| Stop WebUI | Stops AUTOMATIC1111 and the tunnel |
| Download Image ZIP | Downloads generated images as a ZIP file |

At least one Checkpoint is required. Verify compatibility among SD 1.5 and SDXL Checkpoints, LoRAs, ControlNet models, and VAEs.

## Model Cache

The default cache limit is 20 GiB and can be changed under runtime settings. When the limit is exceeded, unused models are removed according to the selected policy.

The following items are protected:

- Currently selected models
- Models connected to the running WebUI
- Pinned models

The Kaggle working space is not permanent storage. Downloaded models and generated images may disappear when the session ends.

## WebUI Login

- Username: `a1111`
- Password: a temporary password generated for each launch
- URL: a temporary `trycloudflare.com` address generated for each launch

These credentials are not the user's Kaggle ID or password. The temporary password is hidden by default and can be copied with the password copy button.

A Cloudflare account is not required. Do not publicly share the temporary URL or password.

## Generated Images and Session Termination

Generated images are stored in:

```text
/kaggle/working/downloads/generated
```

To finish:

1. Download the results with **Download Image ZIP**.
2. Click **Stop WebUI**.
3. Select **Stop Session** from the Kaggle session menu.

Closing the browser tab may not stop the Kaggle GPU session.

## Public Repository Security

Do not upload:

- CivitAI or Hugging Face tokens
- Kaggle API keys or `kaggle.json`
- Temporary WebUI passwords or URLs
- Paid or redistribution-restricted model files
- Generated images containing personal information
- Logs containing authentication data

Clear Notebook outputs before committing to a public repository.

## Version Information

- AUTOMATIC1111: `v1.10.1`
- Python virtual environment: `3.10`
- PyTorch: `2.1.2`
- Torchvision: `0.16.2`
- PyTorch CUDA build: `cu121`

Changes to Kaggle runtime images, CUDA drivers, network policies, and upstream projects may require updates to this notebook.

## Terms of Use

This notebook is intended for education and research. AUTOMATIC1111, extensions, and model files remain subject to their respective licenses and terms. Do not include model files unless redistribution is explicitly permitted.

Users are responsible for checking copyright, portrait rights, privacy, misinformation, bias, and harmful-content issues in generated images.

## References

- [Kaggle Notebooks](https://www.kaggle.com/docs/notebooks)
- [Kaggle Efficient GPU Usage](https://www.kaggle.com/docs/efficient-gpu-usage)
- [AUTOMATIC1111 Stable Diffusion WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
- [Cloudflare Quick Tunnels](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/do-more-with-tunnels/trycloudflare/)
- [gdown](https://github.com/wkentaro/gdown)
- [CivitAI](https://civitai.com/)
- [Hugging Face Models](https://huggingface.co/models)
- [ControlNet WebUI Extension](https://github.com/Mikubill/sd-webui-controlnet)

## Reporting an Issue

Include the failed stage, Kaggle GPU type, Checkpoint architecture, error message, reproduction steps, and the relevant final log lines. Do not include tokens, temporary passwords, or private model URLs.
