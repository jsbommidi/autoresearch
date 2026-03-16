# Environment Setup: `ar` Conda Environment

## Create the Environment

```bash
conda create -n ar python=3.11 -y
conda activate ar
```

> Python 3.11 matches the `joe_da` environment.

---

## Install PyTorch (matching `joe_da`)

`joe_da` uses `torch==2.10.0+cu128`. Install the same stack:

```bash
pip install torch==2.10.0+cu128 torchaudio==2.10.0+cu128 torchvision==0.25.0+cu128 \
    --index-url https://download.pytorch.org/whl/cu128
```

---

## Install Project Dependencies

From inside `autoresearch/` (where `pyproject.toml` lives):

```bash
cd /home/jamiehumphries/projects/autoresearch/autoresearch
pip install -e . --no-deps
pip install kernels matplotlib numpy pandas pyarrow requests tiktoken
```

> `--no-deps` prevents pip from overriding the torch version you just installed.
> `rustbpe` requires Rust/Cargo — install with `curl https://sh.rustup.rs -sSf | sh` if needed.

---

## Full Library List from `joe_da` (reference)

| Package | Version | Notes |
|---|---|---|
| **Python** | 3.11.14 | Base interpreter |
| **torch** | 2.10.0+cu128 | PyTorch, CUDA 12.8 |
| **torchaudio** | 2.10.0+cu128 | Audio extension |
| **torchvision** | 0.25.0+cu128 | Vision extension |
| **torchcodec** | 0.8.1 | Video decoding |
| **torchmetrics** | 1.8.2 | Metrics for PyTorch |
| **pytorch-lightning** | 2.6.1 | Training framework |
| **lightning** | 2.6.1 | Lightning core |
| **lightning-utilities** | 0.15.2 | Lightning utils |
| **triton** | 3.6.0 | GPU kernel compiler |
| **numpy** | 2.3.5 | Numerical computing |
| **pandas** | 2.2.3 | Data manipulation |
| **pyarrow** | 23.0.1 | Columnar data |
| **scipy** | 1.17.0 | Scientific computing |
| **scikit-learn** | 1.8.0 | Machine learning |
| **scikit-image** | 0.25.2 | Image processing |
| **matplotlib** | 3.10.8 | Plotting |
| **seaborn** | 0.13.2 | Statistical plots |
| **Pillow** | 10.4.0 | Image I/O |
| **opencv-python** | 4.13.0.90 | Computer vision |
| **opencv-contrib-python** | 4.10.0.84 | OpenCV extras |
| **opencv-python-headless** | 4.13.0.90 | Headless OpenCV |
| **timm** | 1.0.24 | Image model zoo |
| **kornia** | 0.8.2 | Differentiable CV |
| **kornia_rs** | 0.1.10 | Rust backend for kornia |
| **einops** | 0.8.2 | Tensor ops |
| **albumentations** | 2.0.8 | Image augmentations |
| **albucore** | 0.0.24 | Albumentations core |
| **anomalib** | 2.2.0 | Anomaly detection |
| **faiss** | 1.9.0 | Similarity search |
| **cupy-cuda12x** | 14.0.1 | GPU arrays (CUDA 12) |
| **cucim-cu12** | 26.2.0 | GPU image processing |
| **numba** | 0.64.0 | JIT compiler |
| **llvmlite** | 0.46.0 | LLVM bindings for numba |
| **nvidia-cublas-cu12** | 12.8.4.1 | cuBLAS |
| **nvidia-cuda-cupti-cu12** | 12.8.90 | CUDA profiling |
| **nvidia-cuda-nvrtc-cu12** | 12.8.93 | CUDA runtime compiler |
| **nvidia-cuda-runtime-cu12** | 12.8.90 | CUDA runtime |
| **nvidia-cudnn-cu12** | 9.10.2.21 | cuDNN |
| **nvidia-cufft-cu12** | 11.3.3.83 | cuFFT |
| **nvidia-cufile-cu12** | 1.13.1.3 | GPUDirect Storage |
| **nvidia-curand-cu12** | 10.3.9.90 | cuRAND |
| **nvidia-cusolver-cu12** | 11.7.3.90 | cuSolver |
| **nvidia-cusparse-cu12** | 12.5.8.93 | cuSparse |
| **nvidia-cusparselt-cu12** | 0.7.1 | cuSPARSELt |
| **nvidia-nccl-cu12** | 2.27.5 | Multi-GPU comms |
| **nvidia-nvimgcodec-cu12** | 0.7.0.11 | GPU image codec |
| **nvidia-nvjitlink-cu12** | 12.8.93 | JIT linking |
| **nvidia-nvshmem-cu12** | 3.4.5 | GPU shared memory |
| **nvidia-nvtx-cu12** | 12.8.90 | NVIDIA profiling |
| **cuda-bindings** | 12.9.4 | CUDA Python bindings |
| **cuda-pathfinder** | 1.4.0 | CUDA path utilities |
| **onnx** | 1.20.1 | Model exchange format |
| **onnx-ir** | 0.2.0 | ONNX IR |
| **onnxscript** | 0.6.2 | ONNX scripting |
| **tensorboard** | 2.20.0 | Training visualization |
| **tensorboard-data-server** | 0.7.2 | TensorBoard backend |
| **optuna** | 4.7.0 | Hyperparameter tuning |
| **omegaconf** | 2.3.0 | Config management |
| **huggingface_hub** | 1.6.0 | HuggingFace model hub |
| **safetensors** | 0.7.0 | Safe tensor serialization |
| **modelscope** | 1.34.0 | ModelScope framework |
| **paddlepaddle** | 3.2.2 | PaddlePaddle DL framework |
| **paddleocr** | 3.4.0 | OCR toolkit |
| **paddlex** | 3.4.2 | PaddlePaddle pipeline |
| **easyocr** | 1.7.2 | Easy OCR |
| **pytesseract** | 0.3.13 | Tesseract OCR wrapper |
| **tesserocr** | 2.7.1 | Tesseract bindings |
| **PyMuPDF** | 1.27.1 | PDF processing |
| **pypdfium2** | 5.4.0 | PDF rendering |
| **imagecodecs** | 2026.1.14 | Image codecs |
| **ImageIO** | 2.37.2 | Image I/O |
| **tifffile** | 2026.1.28 | TIFF I/O |
| **shapely** | 2.1.2 | Geometric operations |
| **FrEIA** | 0.2 | Normalizing flows |
| **patchcore-chrom** | 0.1.0 | PatchCore anomaly (local editable) |
| **mpi4py** | 4.1.1 | MPI for Python |
| **aiohttp** | 3.13.3 | Async HTTP |
| **requests** | 2.32.5 | HTTP library |
| **httpx** | 0.28.1 | Modern HTTP client |
| **pydantic** | 2.12.5 | Data validation |
| **SQLAlchemy** | 2.0.46 | Database ORM |
| **psycopg2-binary** | 2.9.11 | PostgreSQL adapter |
| **alembic** | 1.18.4 | DB migrations |
| **protobuf** | 6.33.5 | Protocol Buffers |
| **grpcio** | 1.76.0 | gRPC |
| **opt-einsum** | 3.3.0 | Optimized einsum |
| **optree** | 0.18.0 | PyTree operations |
| **sympy** | 1.14.0 | Symbolic math |
| **networkx** | 3.6.1 | Graph algorithms |
| **joblib** | 1.5.3 | Parallel computing |
| **tqdm** | 4.67.3 | Progress bars |
| **rich** | 14.3.3 | Rich terminal output |
| **typer** | 0.24.1 | CLI builder |
| **click** | 8.3.1 | CLI toolkit |
| **PyYAML** | 6.0.3 | YAML parsing |
| **ruamel.yaml** | 0.19.1 | YAML with comments |
| **jsonschema** | 4.26.0 | JSON Schema validation |
| **jsonargparse** | 4.46.0 | JSON argument parsing |
| **psutil** | 7.2.2 | System/process info |
| **packaging** | 26.0 | Version parsing |
| **filelock** | 3.25.0 | File locking |
| **fsspec** | 2026.2.0 | Filesystem abstraction |
| **Jinja2** | 3.1.6 | Templating |
| **Markdown** | 3.10.1 | Markdown parsing |
| **Werkzeug** | 3.1.5 | WSGI utilities |
| **aistudio-sdk** | 0.3.8 | AI Studio SDK |
| **ninja** | 1.13.0 | Build system |
| **pybind11** | 3.0.1 | C++ bindings |
| **simsimd** | 6.5.12 | SIMD similarity ops |
| **stringzilla** | 4.6.0 | Fast string ops |
| **ml_dtypes** | 0.5.4 | ML numeric types |
| **absl-py** | 2.4.0 | Abseil Python |
| **six** | 1.17.0 | Py2/3 compat |
| **python-dateutil** | 2.9.0 | Date utilities |
| **pytz** | 2025.2 | Timezone data |
| **tzdata** | 2025.3 | IANA timezone data |
