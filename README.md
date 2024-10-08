# zuansi
这是一个基于 Flask 的 AI 聊天代理服务。

## 功能特点

- 支持多种 AI 模型的映射
- 处理流式和非流式响应
- 兼容 OpenAI API 格式
- 支持 Docker 部署

## 支持的模型

目前支持以下模型：

- gpt-4o
- gpt-4-turbo-2024-04-09
- gpt-4o-mini
- claude-3-haiku-20240307
- claude-3-5-sonnet-20240620
- gemini-1.5-pro-latest
- gemini-1.5-pro-exp-0801
- Meta-Llama-3.1-70B-Instruct-Turbo
- Meta-Llama-3.1-405B-Instruct-Turbo
- llama-3.1-sonar-large-128k-online
- mistral-large-2407

## 快速开始

1. 克隆仓库：

   ```
   git clone https://github.com/venbow/zuansi.git
   cd zuansi
   ```

2. 创建并填写必要的配置文件：
   获取这些值的方法：
   1. 登录 chat.notdiamond.ai
   2. 打开浏览器开发者工具（F12）
   3. 在网站上发送一个问题
   4. 在网络面板中找到对应的请求
   5. 在请求头中找到 `next-action` 和 `cookie` 的值
   6. 将这些值分别复制到 `NEXT_ACTION` 和 `COOKIES` 变量中
   7. 如文件不存在则在项目目录创建即可

3. 使用 Docker Compose 启动服务：

   ```
    docker-compose up --build -d && docker-compose logs -f
   ```

4. 服务将在 `http://localhost:5000` 上运行

## API 接口

- GET `/v1/models`：获取可用模型列表
- POST `/v1/chat/completions`：发送聊天完成请求

## 配置

- 在 `app.py` 中的 `MODEL_MAPPINGS` 字典中定义模型映射
- 环境变量：
  - `PORT`：指定服务运行的端口（默认为 5000）

## 文件结构

- `app.py`：主应用程序代码
- `Dockerfile`：Docker 镜像构建文件
- `docker-compose.yml`：Docker Compose 配置文件
- `requirements.txt`：Python 依赖列表


## 注意事项

- 定期更新 `next_action` 和 `cookies` 中的值，因为它们可能会过期

## 贡献
Fork from Jiabinone

## 许可证

本项目仅供学习使用，24小时后请删除。不得用于商业或其他目的。
