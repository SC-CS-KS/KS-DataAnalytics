#  [Jupyter Notebook](https://jupyter.org/)

Jupyter Notebook是基于网页的用于交互计算的应用程序。其可被应用于全过程计算：开发、文档编写、运行代码和展示结果。

是一个 Web 应用程序，便于创建和共享文学化程序文档，支持实时代码、数学方程、可视化和 Markdown，
其用途包括数据清理和转换、数值模拟、统计建模、机器学习等等。
目前，数据挖掘领域中最热门的比赛 Kaggle 里的资料都是 Jupyter 格式。

## 安装
```bash
pip3 install --user --upgrade pip # 更新pip版本

pip3 install --target=/home/sunny/deploy/jupyter/ -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade jupyter # 安装
## --target 指定安装目录

pip install --user -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade jupyterthemes
```

### 选型
```bash
# 代表进行全局安装，安装后全局可用。如果是信任的安装包可用使用该命令进行安装。
sudo pip3 install packagename

# 代表仅该用户的安装，安装后仅该用户可用。处于安全考虑，尽量使用该命令进行安装。
pip3 install --user packagename
```

## 启动
```bash
nohup ./bin/jupyter notebook --ip=0.0.0.0  --port=8898 &
```

```
http://ip:8898
```

### 问题

```bash
# Warning: pip is being invoked by an old script wrapper 错误
python3 -m pip install --upgrade --force-reinstall pip

# ReadTimeoutError: HTTPSConnectionPool
# 需要指定源
-i https://pypi.tuna.tsinghua.edu.cn/simple 

# 启动报错 ModuleNotFoundError: No module named 'jupyter_core'

```

## 扩展

* jupyter_contrib_nbextensions

```bash


```

## Usage
* 执行 shell
```sh
!ls
```