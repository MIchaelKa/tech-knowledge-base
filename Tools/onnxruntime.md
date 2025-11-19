

Notion
https://www.notion.so/ONNX-Runtime-655bc32f9fe64f8299db75254bcb00c4

# Links

[[Neural Net Optimization (NNO)]]
[[Edge Devices]]

# Docs

Enable type reduction
- operator type reduction
- With ONNX Runtime version 1.7 and later it is possible to limit the data types the required operators support to **further reduce the build size**.
- `required_operators_and_types.config`

Save optimized ONNX model
- For debugging in netron

Model Usability Checker
- `...with_runtime_opt.ort`
- https://onnxruntime.ai/docs/tutorials/mobile/helpers/model-usability-checker.html
- it will estimate if using NNAPI or CoreML is likely to be beneficial
- dynamic input shapes may prevent optimal performance

# ORT model format

ORT model format
- https://onnxruntime.ai/docs/performance/model-optimizations/ort-format-models.html
- The ORT format is the format supported by reduced size ONNX Runtime builds.

Optimization style
- Specify whether the converted model will be fully optimized (“Fixed”) or have saved runtime optimizations (“Runtime”).
	- ort and with_runtime_opt ? - YES
	- What means fully optimized (“Fixed”)? Plain .ort model? - YES

ORT Format Model Runtime Optimization
- https://onnxruntime.ai/docs/performance/model-optimizations/ort-format-model-runtime-optimization.html
- support for graph optimizations at runtime for ORT
	- To reduce the binary size, some or all of the graph optimizer code is excluded from a minimal build.
	- GraphOptimizationLevel does not matter with ort?

These only apply to extended minimal builds or full builds.
- Do we use extended minimal builds?

Saved runtime optimizations
- Saved runtime optimizations are only applied at runtime if they are still applicable.
- with_runtime_opt

Generally, the choice is between using an ORT format model with saved runtime optimizations and using a **fully optimized ORT format model**.

with_runtime_opt vs. ort
- https://chatgpt.com/c/691b2766-9ed4-8333-9dd5-6ca706347b08
- The `.ort` model has CPU-centric, fixed graph optimizations baked in.

Graph Optimizations
- https://onnxruntime.ai/docs/performance/model-optimizations/graph-optimizations.html
- performed either online or offline
- in offline mode, the runtime **saves the optimized graph to disk**
- это связано с моделями `with_runtime_opt.ort` ?
- graph partitioning