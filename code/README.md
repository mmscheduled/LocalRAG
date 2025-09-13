<div align="center">
<h1> 🐧 LocalRAG </h1>
</div>

> 1. 完善ollama推荐使用的模型，便于用户直接通过电脑配置选择合适的模型
> 2. 删除API，保护隐私

## 🚀 使用方法

### 环境准备

1.  **拉取项目仓库**
    ```bash
    git clone https://github.com/mmscheduled/LocalRAG.git
    ```
2.  **创建并激活虚拟环境** (推荐使用Python 3.9+):
    ```bash
    conda create -n localrag python=3.10

    ```
3.  **安装依赖项**:
    ```bash
    pip install -r requirements.txt
    ```
4.  **安装并启动Ollama服务** (如果希望使用本地大模型):
    *   访问 [https://ollama.com/download](https://ollama.com/download) 下载并安装Ollama。
    *   启动Ollama服务: `ollama serve`
    *   拉取所需模型，例如: `ollama pull deepseek-r1:1.5b` 或 `ollama pull deepseek-r1:7b` (根据您的硬件配置选择)。本项目默认尝试使用`deepseek-r1:1.5b` 和 `deepseek-r1:7b`。
5.  **配置API密钥 (可选)**:
    在项目根目录创建 `.env` 文件，并按需添加以下内容：
    ```env
    # 用于联网搜索
    SERPAPI_KEY=您的SERPAPI密钥

    # 用于SiliconFlow云端大模型
    SILICONFLOW_API_KEY=您的SiliconFlow API密钥
    # SILICONFLOW_API_URL=https://api.siliconflow.cn/v1/chat/completions (不需要修改)
    ```

### 启动服务

```bash
python rag_demo_pro.py
```
服务启动后，通常会自动在浏览器中打开 `http://127.0.0.1:17995` (或自动选择的其他可用端口)。




# FAQ

1. 运行`ollama serve`时，确保没有打开ollma的图形化界面，否则会出现端口占用冲突，显示以下报错：
```bash
Error: listen tcp 127.0.0.1:11434: bind: Only one usage of each socket address (protocol/network address/port) is normally permitted.
```
2. 