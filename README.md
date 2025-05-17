创建干净的 Conda 环境
conda create -n rknn_new python=3.8 -y
conda activate rknn_new

安装 MKL 核心依赖（兼容 numpy=1.19.5）
conda install -c intel mkl=2020.4 mkl-service=2.3.0 mkl-fft=1.3.0 mkl-random=1.1.1 -y

通过 Conda 安装关键科学计算包
conda install numpy=1.19.5 scipy=1.5.4 libprotobuf=3.12.2 -y

降级 setuptools 并升级 pip
pip install setuptools==58.0.4 pip==23.3.2 --force-reinstall


步骤 0：安装基础工具包
pip install \
  requests==2.27.1 \
  psutil==5.9.0 \
  ruamel.yaml==0.17.4 \
  tqdm==4.64.0 \
  flatbuffers==1.12 \
  protobuf…rt numpy; print(numpy.get_include())')"

1. 安装 numpy 并验证版本
python -c "import numpy; print(numpy.__version__)"
//如果输出 1.19.5，继续下一步。
# 安装编译依赖
sudo apt install build-essential python3.8-dev -y

2. 安装 bfloat16
# 强制从源码安装（指定 numpy 头文件路径）
pip install bfloat16==1.1 --no-binary=bfloat16 --no-cache-dir \
  --global-option="--include-dirs=$(python -c 'import numpy; print(numpy.get_include())')"

3. 安装 OpenCV
pip install opencv-python==4.5.5.64 -i https://pypi.tuna.tsinghua.edu.cn/simple

5. 安装 ONNX 相关包
  pip install \
  onnx==1.9.0 \
  onnxoptimizer==0.2.7 \
  onnxruntime==1.10.0 \
  -i [https://mirror.baidu.com/pypi/simple](https://pypi.tuna.tsinghua.edu.cn/simple) 
6. 安装 PyTorch 和 TensorFlow
  # PyTorch（通过 Conda 安装）
conda install pytorch==1.10.1 torchvision==0.11.2 -c pytorch -y
# TensorFlow
pip install tensorflow==2.6.2 -i [https://mirror.baidu.com/pypi/simple](https://pypi.tuna.tsinghua.edu.cn/simple)

error:
pip list 检查版本是否有冲突
