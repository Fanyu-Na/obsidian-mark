---
title: Linux 安装Miniconda3
cid: 3
type: post
created: 1741186634
modified: 1741186634
slug: 3
---

1. 获取conda

```sh
wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
2. 安装conda：

```sh
bash Miniconda3-latest-Linux-x86_64.sh
```
3. 重启终端:

4. 查看镜像：

```sh
conda config --show-sources
```

5. 配置镜像（北外）：

```sh
conda config --set show_channel_urls yes
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/pkgs/free/ 
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/pkgs/main/ 
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/conda-forge/ 
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/msys2/
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/pytorch/
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/bioconda/
```
6. 创建环境 

```sh
conda create -n env python=3.7
```
7. 激活环境：

```sh
conda activate env
```
8. 退出环境:

```sh
conda deactivate
```
