![alt text](image/Cloud_AI_100.png)


# Introduction Qualcomm ``efficient-transformers`` library
 
**Train anywhere, Infer on Qualcomm Cloud AI with a Developer-centric Toolchain**

This library provides reimplemented blocks of LLMs which are used to make the models functional and highly performant on Qualcomm Cloud AI 100.
We support wide range of [models](validated_models) architectures, for easy efficient deployment on Cloud AI 100 cards. Users only need to provide model card from HuggingFace or Path to the local model and the library will take care of transforming model to it's efficient implementation for Cloud AI 100.

For other models, there is comprehensive documentation to inspire upon the changes needed and How-To(s).

**Typically for LLMs, the library provides:**
1. Reimplemented blocks from Transformers which enable efficient on-device retention of intermediate states. read more [here](kv_cache)
2. Graph transformations to enable execution of key operations in lower precision
3. Graph transformations to replace some operations to other mathematically equivalent operations that are efficient/supported on HW backend
4. Handling for underflow and overflows in lower precision
5. Patcher modules to map weights of original model's operations to updated model's operations
6. Exporter module to export the model source into a `ONNX` Graph.
7. Sample example applications and demo notebooks
8. Unit test templates.

***Latest news*** : <br>

- [coming soon] Support for more popular [models](models_coming_soon)<br>
- [01/2025] [FP8 models support](https://huggingface.co/collections/neuralmagic/fp8-llms-for-vllm-666742ed2b78b7ac8df13127) Added support for inference of FP8 models.

- [01/2025] Added support for [Ibm-Granite](https://huggingface.co/ibm-granite/granite-3.1-8b-instruct)
- [11/2024] [finite adapters support](https://github.com/quic/efficient-transformers/pull/153) allows mixed adapter usage for peft models.
- [11/2024] [Speculative decoding TLM](https://github.com/quic/efficient-transformers/pull/119) QEFFAutoModelForCausalLM model can be compiled for returning more than 1 logits during decode for TLM.
- [11/2024] Added support for [Meta-Llama-3.3-70B-Instruct](https://huggingface.co/meta-llama/Llama-3.3-70B-Instruct), [Meta-Llama-3.2-1B](https://huggingface.co/meta-llama/Llama-3.2-1B) and [Meta-Llama-3.2-3B](https://huggingface.co/meta-llama/Llama-3.2-3B)
- [09/2024] [AWQ](https://arxiv.org/abs/2306.00978)/[GPTQ](https://arxiv.org/abs/2210.17323) 4-bit quantized models are supported
- [09/2024] Now we support [PEFT](https://huggingface.co/docs/peft/index) models
<details>
<summary>More</summary>

- [01/2025] Added support for [Ibm-Granite](https://huggingface.co/ibm-granite/granite-3.1-8b-instruct)
- [01/2025] Added support for [Ibm-Granite-Guardian](https://huggingface.co/ibm-granite/granite-guardian-3.1-8b)
- [09/2024] Added support for [Gemma-2-Family](https://huggingface.co/collections/google/gemma-2-release-667d6600fd5220e7b967f315)<br>
- [09/2024] Added support for [CodeGemma-Family](https://huggingface.co/collections/google/codegemma-release-66152ac7b683e2667abdee11)
- [09/2024] Added support for [Gemma-Family](https://huggingface.co/collections/google/gemma-release-65d5efbccdbb8c4202ec078b)
- [09/2024] Added support for [Meta-Llama-3.1-8B](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B)
- [09/2024] Added support for [Meta-Llama-3.1-8B-Instruct](https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct)
- [09/2024] Added support for [Meta-Llama-3.1-70B-Instruct](https://huggingface.co/meta-llama/Meta-Llama-3.1-70B-Instruct)
- [09/2024] Added support for [granite-20b-code-base](https://huggingface.co/ibm-granite/granite-20b-code-base-8k)
- [09/2024] Added support for [granite-20b-code-instruct-8k](https://huggingface.co/ibm-granite/granite-20b-code-instruct-8k)
- [09/2024] Added support for [Starcoder1-15B](https://huggingface.co/bigcode/starcoder)
- [08/2024] Added support for inference optimization technique ```continuous batching```
- [08/2024] Added support for [Jais-adapted-70b](https://huggingface.co/inceptionai/jais-adapted-70b)
- [08/2024] Added support for [Jais-adapted-13b-chat](https://huggingface.co/inceptionai/jais-adapted-13b-chat)
- [08/2024] Added support for [Jais-adapted-7b](https://huggingface.co/inceptionai/jais-adapted-7b)
- [06/2024] Added support for [GPT-J-6B](https://huggingface.co/EleutherAI/gpt-j-6b)
- [06/2024] Added support for [Qwen2-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2-1.5B-Instruct)
- [06/2024] Added support for [StarCoder2-15B](https://huggingface.co/bigcode/starcoder2-15b)
- [06/2024] Added support for [Phi3-Mini-4K-Instruct](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct)
- [06/2024] Added support for [Codestral-22B-v0.1](https://huggingface.co/mistralai/Codestral-22B-v0.1)
- [06/2024] Added support for [Vicuna-v1.5](https://huggingface.co/lmsys/vicuna-13b-v1.5)
- [05/2024] Added support for [Mixtral-8x7B](https://huggingface.co/mistralai/Mixtral-8x7B-v0.1) & [Mistral-7B-Instruct-v0.1](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.1).
- [04/2024] Initial release of [efficient transformers](https://github.com/quic/efficient-transformers) for seamless inference on pre-trained LLMs.
</details>