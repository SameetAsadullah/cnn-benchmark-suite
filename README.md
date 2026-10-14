# Vision Eval: CNN Model Evaluation (PyTorch)

A scalable framework for benchmarking deep convolutional architectures on classification tasks. This project evaluates the impact of optimizers, learning rates, and batch sizes across multiple CNN backbones — providing a reproducible experimental setup aligned with research and production best practices.

[![Notebook checks](https://github.com/SameetAsadullah/vision-eval/actions/workflows/quality.yml/badge.svg)](https://github.com/SameetAsadullah/vision-eval/actions/workflows/quality.yml)

---

## 🚀 Key Highlights

- Plug-and-play support for multiple CNN architectures
- Scalable benchmarking with grid search over:
  - Optimizers: `SGD`, `Adam`
  - Learning Rates: `0.01`, `0.1`
  - Batch Sizes: `32`, `64`
- Data augmentation, normalization, and stratified validation split
- Detailed metrics logging + real-time visualization support
- Model weights saved automatically for top-performing configs

---

## 🧠 Architectures Supported

- **Custom Lightweight CNN** (baseline)
- **ResNet-18**
- **MobileNetV2**
- **GoogleNet**
- **AlexNet** *(included for completeness; not recommended for production)*

> 🛡️ Modular design allows easy plug-in of ViT, EfficientNet, ConvNext, etc.

---

## Comparison workflow

The notebook trains each CNN with the configured optimizer, learning rate, and batch size, then records epoch metrics and validation results. It selects the best configuration per architecture on validation accuracy before reporting test performance. The exported CSV files in `results/` keep those stages separate.

---

## 📊 Experiments & Logging

- Validation and test performance tracked across all combinations
- Key metrics:
  - Train & Val Accuracy/Loss (per epoch)
  - Best Validation Accuracy (per config)
  - Final Test Accuracy (per model)
- Automatic selection of best model per architecture
- Visual analytics:
  - Accuracy trends
  - Impact of learning rate
  - Batch size comparison
  - Model vs Optimizer performance

---

## 🔁 Use Cases

- Model architecture benchmarking
- Optimizer sensitivity studies
- Lightweight deployment model search
- Reproducible architecture and optimizer benchmarks

## Repository layout

- `notebooks/cnn-benchmark.ipynb` — architecture training and comparison pipeline
- `results/` — epoch, validation, and test metrics exported by the benchmark

## Run the benchmark

```bash
cd notebooks
jupyter lab cnn-benchmark.ipynb
```
