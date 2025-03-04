# OpenBuddy - Open Multilingual Chatbot for Everyone


<div align="center">
  <img src="media/logo.png" width="300px">
</div>


[中文](README.zh.md) | [English](README.md)

Website: [https://openbuddy.ai](https://openbuddy.ai)

GitHub: [https://github.com/OpenBuddy/OpenBuddy](https://github.com/OpenBuddy/OpenBuddy)

Huggingface: https://huggingface.co/OpenBuddy

![Demo](media/demo.png)

OpenBuddy is a powerful open multilingual chatbot model aimed at global users, emphasizing conversational AI and seamless multilingual support for English, Chinese, and other languages.

Built upon Facebook's LLaMA model, OpenBuddy is fine-tuned to include an extended vocabulary, additional common characters, and enhanced token embeddings. By leveraging these improvements and multi-turn dialogue datasets, OpenBuddy offers a robust model capable of answering questions and performing translation tasks across various languages.

Our mission with OpenBuddy is to provide a free, open, and offline-capable AI model that operates on users' devices, irrespective of their language or cultural background. We strive to empower individuals worldwide to access and benefit from AI technology.

## Online Demo

Currently, the OpenBuddy-13B demo is available on our Discord server. Please join our Discord server to try it out!

Discord: [![Discord](https://img.shields.io/discord/1100710961549168640?color=blueviolet&label=Discord)](https://discord.gg/6fU2s9cGjA)


## Key Features

- **Multilingual** conversational AI, Chinese, English, Japanese, Korean, French, Germany and more!
- Built on top of the LLaMA model from Facebook
- Enhanced vocabulary and support for common CJK characters
- Fine-tuned with multi-turn dialogue datasets for improved performance
- Two model versions: 7B and 13B
- 4-bit quantization for CPU deployment via llama.cpp (with slightly reduced output quality)
- Active development plans for future features and improvements

## Model Versions

OpenBuddy currently offers two model versions: 7B and 13B.

More information about downloading the models can be found in the [Models](models.md) page.

## Future Plans

- Enhancing multilingual performance
- Optimizing model quality post-quantization
- Developing a mechanism to assess content quality, safety, and inference capabilities
- Investigating Reinforcement Learning with Human Feedback (RLHF)
- Exploring the addition of multimodal capabilities for dialogues with image context

## Installation

Due to LLaMA licensing restrictions, you need the original LLaMA-7B model to utilize this model. To decrypt the model weights:

1. Acquire the original LLaMA-7B model (not the Huggingface version).
2. Clone this GitHub repository.
3. Ensure that you have Python 3.7 or higher and numpy installed, you can install numpy with `pip install numpy`.
4. Run the following command, try python3 if python does not work:

```
python decrypt.py [path-to-consolidated.00.pth] [path-to-our-model-folder]
```

## Usage with llama.cpp on CPU/GPU (Recommended)

The 7B model has been converted to ggml format, making it compatible with llama.cpp. llama.cpp is a pure C++ inference engine for LLaMA models, originally designed for CPU deployment.

After recent updates, llama.cpp now supports cuBLAS and OpenCL acceleration, which means you can utilize your AMD/NVIDIA GPU to accelerate inference.

The model is available at: [Models](models.md), `(5-bit, CPU/GPU, llama.cpp)` is the variant you should download.

After installing the model and [llama.cpp](https://github.com/ggerganov/llama.cpp), you can run the `chat-llamacpp.bat` or `chat-llamacpp.sh` script to interact with OpenBuddy through the interactive console.

## Usage with Transformers on GPU

Please ensure that your GPU supports bf16 (bfloat16) before attempting to use OpenBuddy with the huggingface's `Transformers` library on a GPU. A 7B model may require up to 24GB of GPU memory.

To use OpenBuddy with huggingface's Transformers library on a GPU, follow the [hello.py](examples/hello.py) example. For a more comprehensive understanding of text generation, please refer to the [Transformers documentation](https://huggingface.co/docs/transformers/index).

## Usage with Inference Frameworks

LLM inference frameworks including [Langport](https://github.com/vtuber-plan/langport) and [FastChat](https://github.com/lm-sys/FastChat), have been adapted to support OpenBuddy. Please refer to the respective repositories for more information.

We are actively working on developing our own inference system, [GrandSage](https://github.com/OpenBuddy/GrandSage). GrandSage is currently in the early stages of development.

## Disclaimer

OpenBuddy is provided as-is without any warranty of any kind, either express or implied. The authors and contributors shall not be held liable for any damages resulting from the use or inability to use this software. By using OpenBuddy, you agree to these terms and conditions.

## License Restrictions

OpenBuddy is intended for non-commercial research purposes only, following the same restrictions as the LLaMA model. Any use outside of this scope is strictly prohibited. For more information, please refer to the LLaMA license.

## Acknowledgements

We want to thank [AIOS.club](https://github.com/aios-club) for their invaluable support and collaboration in this project. Our appreciation extends to the Facebook AI team for releasing the LLaMA model, which has served as a solid foundation for OpenBuddy's development. Finally, we extend our thanks to the open-source community for their continued support and contributions.
