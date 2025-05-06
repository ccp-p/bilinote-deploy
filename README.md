# BiliNote Deploy

这是 [BiliNote](https://github.com/JefferyHcool/BiliNote) 的官方 Docker 部署仓库。  
只需几条命令，即可拉取后端、前端、Nginx 三个镜像并完成部署，快速运行 BiliNote！



## 🚀 快速开始

### 1. 克隆部署仓库

```bash
git clone https://github.com/jefferyhjw/bilinote-deploy.git
cd bilinote-deploy
```
### 2. 创建 .env 文件
```bash
cp .env.example .env
```

| 变量名                  | 示例值                    | 说明                                                                        |
| -------------------- | ---------------------- |---------------------------------------------------------------------------|
| `APP_PORT`           | `3015`                 | 应用运行端口                                                                    |
| `STATIC`             | `/static`              | 后端静态资源 URL 路径前缀                                                           |
| `OUT_DIR`            | `./static/screenshots` | 截图输出目录（服务器内部路径）                                                           |
| `IMAGE_BASE_URL`     | `/static/screenshots`  | 前端访问截图时的 URL 路径前缀                                                         |
| `DATA_DIR`           | `data`                 | 音视频缓存目录（服务器内部路径）                                                                   |
| `TRANSCRIBER_TYPE`   | `fast-whisper`         | 语音转文字引擎，支持：`fast-whisper` / `bcut` / `kuaishou` / `mlx-whisper`（Apple 平台） |
| `WHISPER_MODEL_SIZE` | `base`                 | Whisper 模型大小，如 `tiny` / `base` / `small` / `medium` / `large`             |
| `DOUYIN_COOKIES`     | （可填）                   | 下载抖音视频时的 Cookie，必填字段                                                      | |

### 3. 启动容器
```bash
docker-compose up -d
```
> 第一次启动需要等待一段时间，请耐心等待。

执行 `docker-compose logs -f`

如果看到 `INFO: Uvicorn running on http://0.0.0.0:8000 (Press CTRL+C to quit)" 表示服务启动成功。`

访问 http://{服务器IP}:{APP_PORT} 即可访问 BiliNote。
