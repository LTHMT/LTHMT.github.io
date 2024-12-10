
## 1. **Conda 虚拟环境（Virtual Environment）**

### **定义：**
- **Conda 虚拟环境**是一个隔离的工作环境，可以安装不同版本的 Python 和相关的依赖包。
- 每个虚拟环境都是独立的，确保项目依赖不会相互干扰。

### **特点：**
- 你可以为每个项目创建独立的环境。
- 在同一台机器上，可以有多个不同的 Python 版本和依赖包集合。
- 通过 `conda create -n myenv python=3.9` 创建。
- 通过 `conda activate myenv` 激活。

### **常用命令：**
- **创建环境**：
  ```bash
  conda create -n myenv python=3.9

  conda create --prefix D:\my_envs\lt_env python=3.9 -y // 指定路径

  ```
  - `-n myenv`:命名
  - `--prefix D:\my_envs\lt_env`：将环境创建在 D:\my_envs\lt_env 目录下。
  - `python=3.9`：指定 Python 版本。
  - `-y`：自动确认安装。

- **激活环境**：
  ```bash
  conda activate myenv

  conda activate D:\my_envs\lt_env // 指定路径

  ```
- **查看所有环境**：
  ```bash
  conda info --envs
  ```
- **删除环境**：
  ```bash
  conda remove myenv
  conda remove --prefix D:\my_envs\lt_env --all

  ```




---

## 2. **Jupyter Notebook Kernel**

### **定义：**
- **Kernel** 是 Jupyter Notebook 执行代码的后端引擎。
- 每个 Kernel 关联着一个特定的 Python 解释器和依赖包集合（可以是 Conda 虚拟环境，也可以是系统默认的 Python 环境）。
- 你可以在 Jupyter Notebook 中为不同的 Conda 环境添加多个 Kernel，从而在 Notebook 中切换不同的环境。

### **特点：**
- 每个 Kernel 都与某个特定的 Python 环境绑定。
- 支持多种编程语言（如 Python、R、Julia 等）。
- 通过 `ipykernel` 注册虚拟环境到 Jupyter Notebook。

### **常用命令：**
- **将 Conda 环境添加为 Jupyter Kernel**：
  ```bash
  conda activate myenv
  python -m ipykernel install --user --name=myenv --display-name "Python (myenv)"
  ```
- **查看所有可用的 Kernels**：
  ```bash
  jupyter kernelspec list
  ```

- **删除已安装的 Kernel**：
  ```bash
  jupyter kernelspec uninstall myenv
  ```

### 完整实例

``` bash
conda activate YOUR_ENVNAME
pip install jupyterlab
pip install ipykernel
python -m ipykernel install --user --name YOUR_ENVNAME

conda deactivate

```

- **解释**
 - `python -m ipykernel install`：调用 `ipykernel `模块，将当前 Python 环境注册为 Jupyter 内核。
 - `--user`：在当前用户级别安装内核，不需要管理员权限。
 - `--name myenv`：内核的内部名称为 myenv。
 - `--display-name "Python (myenv)"`：Jupyter Notebook 界面中显示的内核名称。

- **常用指令**
``` bash
jupyter kernelspec list //查看kernel列表

jupyter kernelspec uninstall myenv  // 删除kernel


```
---

## 3. **两者的关系**

1. **Conda 虚拟环境** 提供隔离的 Python 解释器和依赖包。
2. **Jupyter Kernel** 是一个接口，让 Jupyter Notebook 可以使用特定的 Python 环境（如 Conda 虚拟环境）。
3. **将 Conda 环境注册为 Kernel** 后，你可以在 Jupyter Notebook 中选择该环境来运行代码。


?> **总结**

| **特性**            | **Conda 虚拟环境**                                   | **Jupyter Notebook Kernel**                         |
|---------------------|------------------------------------------------------|----------------------------------------------------|
| **定义**            | 独立的 Python 解释器和依赖包环境                     | Jupyter Notebook 中用于执行代码的后端引擎          |
| **作用**            | 提供隔离的开发环境，避免依赖冲突                     | 连接 Jupyter Notebook 与特定 Python 环境           |
| **创建方式**        | `conda create -n myenv python=3.9`                   | `python -m ipykernel install --user --name=myenv` |
| **激活方式**        | `conda activate myenv`                               | 在 Jupyter Notebook 中选择相应 Kernel              |
| **用途**            | 为不同项目创建独立环境                               | 在 Notebook 中运行代码时指定 Python 解释器         |

- **简单理解：**
  - **Conda 虚拟环境** 是一个容器，里面有 Python 和依赖。
  - **Jupyter Kernel** 是一个桥梁，让 Jupyter Notebook 使用这个容器来运行代码。

  通过这种方式，你可以在 Jupyter Notebook 中自由切换不同的 Conda 环境来满足不同项目的需求。



