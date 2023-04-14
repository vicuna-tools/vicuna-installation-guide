# Vicuna Installation Guide
The "vicuna-installation-guide" provides step-by-step instructions for installing and configuring Vicuna-13B
## Requirements
- The Vicuna model needs ~10GB of CPU RAM, If you don't have enough RAM, you can increase the size of your virtual RAM (swap)
  A tutorial on how to increase the swapfile on Linux: https://arcolinux.com/how-to-increase-the-size-of-your-swapfile/
- The git and wget package 

## Installation
### One-line install script for Vicuna 1.1
```
git clone https://github.com/ggerganov/llama.cpp && cd llama.cpp && make -j && cd models && wget -c https://huggingface.co/TheBloke/vicuna-13B-1.1-GPTQ-4bit-128g-GGML/resolve/main/vicuna-13B-1.1-GPTQ-4bit-128g.GGML.bin
```

### Manual Installation
#### 1. Clone the llama.cpp respository
```
git clone https://github.com/ggerganov/llama.cpp
```
#### 2. Make it!
```
make -j
```
#### 3. Move to the llama.cpp/models folder
```
cd llama.cpp/models
```
#### 4. Download the latest Vicuna model (13B) from Huggingface
```
wget https://huggingface.co/TheBloke/vicuna-13B-1.1-GPTQ-4bit-128g-GGML/resolve/main/vicuna-13B-1.1-GPTQ-4bit-128g.GGML.bin
```
## Usage
#### Navigate back to the llama.cpp folder
```
cd ..
```
#### Run the vicuna model with llama.cpp's chat-with-bob.txt
```
./main -m ./models/vicuna-13B-1.1-GPTQ-4bit-128g.GGML.bin --repeat_penalty 1.0 --color -i -r "User:" -f prompts/chat-with-bob.txt
```
