# 安装python虚拟化环境及ansible
<!-- TOC -->

- [安装python虚拟化环境及ansible](#安装python虚拟化环境及ansible)
    - [安装 pip](#安装-pip)
    - [安装python多版本管理工具pyenv](#安装python多版本管理工具pyenv)
    - [安装python虚拟化管理工具virtualenv](#安装python虚拟化管理工具virtualenv)
    - [使用pyenv安装python3.7](#使用pyenv安装python37)
    - [使用virtualenv安装python虚拟化环境](#使用virtualenv安装python虚拟化环境)
    - [安装ansible](#安装ansible)

<!-- /TOC -->
## 安装 pip 

```bash
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py

python get-pip.py
```

## 安装python多版本管理工具pyenv

```bash
git clone https://github.com/pyenv/pyenv.git ~/.pyenv

# 添加环境变量
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile

# pyenv命令的自动补全
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
```

## 安装python虚拟化管理工具virtualenv

```bash
pip install virtualenv
```

## 使用pyenv安装python3.7

```bash
# 查看有哪些python环境可以安装
pyenv install -l

# 安装python3之前需要安装libffi-devel、sqlites、readline、bzip2、bzip2-libs包
yum install libffi-devel sqlite sqlite-devel readline readline-devel bzip2 bzip2-libs -y

# 选择某个版本安装
pyenv install 3.7.1

# 默认python环境安装在 ~/.pyenv/versions/版本/

# 查看系统有哪些python环境，前边带*号的为正在使用的版本
pyenv versions

# 查看系统正在使用哪个python环境
pyenv version

#可以使用pyenv [ global | local ] python版本 来更改本地及全局python环境
```

## 使用virtualenv安装python虚拟化环境

```bash
mkdir /opt/python3.7
cd /opt/python3.7

# 指定-p 指定需要创建的python版本
virtualenv -p ~/.pyenv/versions/3.7.1/bin/python venv3.7

# 切换至指定的python虚拟化环境
. /opt/python3.7/venv3.7/bin/activate

#查看当前python版本
(venv3.7) [root@rancher ~]# python --version
Python 3.7.1

```

## 安装ansible

```bash
# 使用pip查看ansible版本
pip search ansbile

# 安装ansible
pip install ansible
```