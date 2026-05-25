# ECG_SSML
Self-Supervised Multimodal Learning Method Comparison with ECG Signals and Images

### Dataset downloading
Datasets we used are as follows:
- **MIMIC-IV-ECG**: We downloaded the [MIMIC-IV-ECG](https://physionet.org/content/mimic-iv-ecg/1.0/) dataset as the ECG signals.
Due to limited training time, we used only 200,000 samples from the MIMIC-IV-ECG dataset. The CSV file containing the list of used data is provided [here](https://drive.google.com/drive/folders/14XD8k3BXa7nYv1U3jqDiGRcY72J-N4Wl).

### Pre-training
To run pre-training:
```bash
PYTHONPATH=. torchrun "./pretrain/main.py" \
                      --config_path "./config/pretrain.yaml"
```
Pre-trained models can be found [here](https://drive.google.com/drive/folders/1AC1QJL96RWL3VEunZYNWMBXLL17RrCN3).

Pre-trained weights is organized as follows:
- **unimodal_init/**: Weights for initializing each encoder before multimodal pre-training, shared across both methods.
- **contrastive_encoder**: Best image encoder and signal encoder from the contrastive-based method
- **generative_ckpt**: Best pre-trained model from the generative-based method (image and signal encoders are not separated).