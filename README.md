# Vicuna Installation Guide


[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]

Detailed instructions for installing and configuring Vicuna

<a href="#installation">Installation</a> - <a href="#usage">Usage</a>


### latest changes
- added instructions for 7B model
- fixed the `wget` command 
- modified the `chat-with-vicuna-v1.txt` in my llama.cpp fork
- updated this guide to vicuna version 1.1
## Requirements
- The Vicuna 13B model needs ~10GB of CPU RAM, If you don't have enough RAM, you can increase the size of your virtual RAM (swap)
  A tutorial on how to increase the swapfile on Linux: https://arcolinux.com/how-to-increase-the-size-of-your-swapfile/
- The git and wget package 
- A Unix based operating system is recommended

## Installation
### One-line install script for Vicuna-1.1-13B
```
git clone https://github.com/fredi-python/llama.cpp.git && cd llama.cpp && make -j && cd models && wget -c https://huggingface.co/eachadea/ggml-vicuna-13b-1.1/resolve/main/ggml-vic13b-uncensored-q5_1.bin
```
### One-line install script for Vicuna-1.1-7B
```
git clone https://github.com/fredi-python/llama.cpp.git && cd llama.cpp && make -j && cd models && wget -c https://huggingface.co/eachadea/ggml-vicuna-7b-1.1/resolve/main/ggml-vic7b-uncensored-q5_1.bin
```

### Manual Installation
#### 1. Clone the llama.cpp respository
```
git clone https://github.com/fredi-python/llama.cpp.git
```
#### 2. Change directory
```
cd llama.cpp
```
#### 3. Make it!
```
make -j
```
#### 4. Move to the llama.cpp/models folder
```
cd models
```
#### 5. a) Download the latest Vicuna model (13B) from Huggingface
```
wget https://huggingface.co/eachadea/ggml-vicuna-13b-1.1/resolve/main/ggml-vic13b-uncensored-q5_1.bin
```
#### 5. b) Download the latest Vicuna model (7B) from Huggingface
```
wget https://huggingface.co/eachadea/ggml-vicuna-7b-1.1/resolve/main/ggml-vic7b-uncensored-q5_1.bin
```
## Usage
#### Navigate back to the llama.cpp folder
```
cd ..
```
#### Example of how to run the 13b model with llama.cpp's chat-with-vicuna-v1.txt 
```
./main -m models/ggml-vic13b-q5_1.bin -f 'prompts/chat-with-vicuna-v1.txt' -r 'User:' --temp 0.36
```


[stars-shield]: https://img.shields.io/github/stars/vicuna-tools/vicuna-installation-guide.svg?style=for-the-badge
[stars-url]: https://github.com/vicuna-tools/vicuna-installation-guide/stargazers
[forks-shield]: https://img.shields.io/github/forks/vicuna-tools/vicuna-installation-guide.svg?style=for-the-badge
[forks-url]: https://github.com/vicuna-tools/vicuna-installation-guide/network/members