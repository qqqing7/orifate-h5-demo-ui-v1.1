# 东隅穿衣 · v1.1 前端测试包

这是七个独立前端版本的静态测试包，可直接部署到 GitHub Pages。

## 在线测试入口

部署完成后访问：

`https://<你的 GitHub 用户名>.github.io/<仓库名>/`

如果仓库根目录就是本文件夹的内容，入口页会自动列出所有版本。

## 版本目录

| 目录 | 版本 | 说明 |
|---|---|---|
| `v1/` | V1 · 恢复版 | 经典首页 |
| `v2/` | V2 · 日历优先 | 近 7 天日历 + 幸运色卡 |
| `v3-weather-girl/` | V3 · Weather Girl | 白色天气卡 + 照片条 |
| `v3-iphone17/` | V3 · iPhone 17 | 透明背景 + 无照片条 |
| `v5-five-drawer/` | V5 · 五色抽屉 | 彩色抽屉首页 |
| `v8-stage/` | V8 · 舞台式今日穿搭 | 舞台色卡 |
| `today-iphone16/` | 今日穿搭 · iPhone 16 | 深色大图 + 五色展示图 |

## 上传到 GitHub Pages

### 方式 A：GitHub Actions（推荐）

1. 新建 GitHub 仓库。
2. 把本文件夹里的**全部内容**上传到仓库根目录（不是把外层文件夹再套一层）。
3. 打开仓库 `Settings → Pages`，`Build and deployment` 选择 **GitHub Actions**。
4. 推送到 `main` 后，`.github/workflows/pages.yml` 会自动部署。
5. 在 Actions 完成后打开 `https://<用户名>.github.io/<仓库名>/`。

### 方式 B：Deploy from a branch

1. 上传本文件夹内容到仓库根目录。
2. `Settings → Pages` 选择 `Deploy from a branch`。
3. 分支选 `main`，目录选 `/ (root)`，保存。
4. 等待 Pages 构建完成。

> `index.html` 和版本目录必须同级；如果上传成了子目录，请把子目录里的内容移到仓库根目录，或在 Pages 设置里指向该子目录。

## 本地预览

在本文件夹执行：

```bash
python -m http.server 8000
```

然后打开：

`http://127.0.0.1:8000/`

不要直接双击 `index.html` 用 `file://` 打开，部分静态资源在 `file://` 下会受浏览器限制。

## 测试说明

- 纯前端演示，无真实后端、无真实天气、无真实 AI 识别。
- 照片只留在本地页面，不会上传。
- 色彩分析、体型分析、生日、幸运色等记录保存在浏览器 localStorage。
- 不同版本使用不同路径，存储互不影响。
- 清除浏览器站点数据会同时清除测试记录。
- 推荐使用 Chrome / Edge，移动端按 393×852 比例设计。

## 目录结构

```
.
├── index.html
├── .nojekyll
├── 404.html
├── README.md
├── .github/workflows/pages.yml
├── v1/
├── v2/
├── v3-weather-girl/
├── v3-iphone17/
├── v5-five-drawer/
├── v8-stage/
└── today-iphone16/
```

每个版本目录里是独立的 `index.html + assets + static`，没有跨版本运行时依赖。

