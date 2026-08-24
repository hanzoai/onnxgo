# hanzoai/onnxgo — ONNX Runtime Go Bindings

High-performance Go bindings for Microsoft ONNX Runtime.
GPU inference (CUDA, TensorRT, CoreML) for production AI workloads.

## Usage

```go
import ort "hanzo.ai/onnxgo"

ort.SetSharedLibraryPath("/usr/local/lib/libonnxruntime.so")
ort.InitializeEnvironment()
defer ort.DestroyEnvironment()

session, _ := ort.NewAdvancedSession("model.onnx",
    []string{"input"}, []string{"output"},
    ort.NewSessionOptions(),
)
defer session.Destroy()
```

## GPU Support

NVIDIA CUDA + cuDNN, TensorRT, Apple CoreML, DirectML, OpenVINO, ROCm.

## Origin

Forked from yalue/onnxruntime_go (2026-03-29). Rebranded for Hanzo AI infrastructure.
