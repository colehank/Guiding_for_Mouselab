# CM\_环境配置

## 1 python 3.7

在anaconda创建后，在terminal激活，示例环境名为'**py37**'

```auto
 . /Users/zgh/opt/anaconda3/bin/activate && conda activate /Users/zgh/opt/anaconda3/envs/py37;
```

## 2 安装配置环境

```auto
git clone https://github.com/RationalityEnhancement/ComputationalMicroscope.git
```

```auto
cd /Users/zgh/Desktop/ComputationalMicroscope/src
pip3 install -r requirements.txt
```

初次使用，在macos一些可能需要手动安装的包

```auto
brew install freetype
brew install pkg-config
HOMEBREW_NO_INSTALL_CLEANUP //这是清除brew安装的
```

[](null)

**做法（**[使用macos下的matplotlib](https://matplotlib.org/2.2.2/faq/osx_framework.html#pythonhome-function)**）：**

以conda为例

```auto
conda install python.app
//在后续python命令中，使用pythonw而非python

//若报错，更新conda是一个好的办法
conda update conda
conda update --force conda//升级报错可尝试强制升级
```

## 3 使用

### 3\.1 构建trail与策略数据库

```auto
pythonw infer_sequences.py increasing_variance test none
#pythonw#//在env里使用框架macos的python命令,是CM要求的
```

### 3\.2 输出策略统计图

```auto
pythonw analyze_sequences.py increasing_variance test none
```

python输出图时容易崩溃，可以新建一个terminal尝试

### 3\.3 输出某一被试策略数据库

```auto
python3 infer_participant_sequences.py <pid> <exp_num> [<block>]
//数据在python/results/inferred_sequences/<exp_num>
//没搞通，run不了，可以为单独被试新建csv用3.1方法解决
```

## 4\. 帮助文稿

```auto
python3 infer_sequences.py help
```

关于输出的策略见`result`

关于输出的策略说明见`result/check_pkl.py`
