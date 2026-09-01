# NOAA 太阳直射点与全球 3D 数字孪生台 (NOAA Solar Twin 3D)

基于 Cesium 3D 地球引擎与 NOAA 天文物理算法构建的全球太阳光照与微观测站数字孪生系统。

## ✨ 核心特性

- 🌐 **NOAA 天文物理引擎**：高精度计算太阳真黄经、太阳直射赤纬/经度（真正午）、均时差（EoT）、大气顶层辐照度。
- 🏢 **全球 3D 建筑与高精度地形**：集成 Cesium OSM Buildings 3D 建筑体素与全球真实地形（支持阴影实时投射与昼夜晨昏渐变）。
- 📍 **测站微观遥测与光伏算力**：支持任意地点（陆家嘴、曼哈顿、珠峰等预设或点击拾取/输入坐标），实时计算太阳高度角、方位角、法向日照辐射（DNI）与光伏板理论瞬时功率。
- 🧭 **地平全息雷达**：动态 360° 全景雷达投影，直观展示太阳天顶方位与高度。
- ⏳ **时间与四季模拟**：支持实时同步、日自转加速（1000x）、四季公转（50000x）、二十四节气与二分二至一键跳跃。

---

## 🔑 关于 Cesium Ion Access Token

本项目使用 Cesium Ion 提供的地形与 3D 建筑服务，需要使用 Cesium Ion Access Token。

### ⚠️ 安全注意事项（防盗刷）
1. **公开仓库安全**：
   - 建议前往 [Cesium Ion 控制台](https://ion.cesium.com/tokens) 创建一个专门的 Token。
   - 在 Token 设置的 **Allowed URL / Domain** 白名单中填入你的部署域名（例如 *.pages.dev, localhost）。
   - 这样即使前端代码公开，其他未经授权的域名也无法盗刷你的配额。
2. **自定义 Token**：
   - 页面支持在右上角点击 **「🔑 配置 Cesium Ion Token」** 随时输入你自己的 Token 并保存在本地浏览器 localStorage 中。
   - 也可以在 URL 查询参数中传入 ?token=YOUR_TOKEN 进行临时调试。

---

## 🚀 部署指南 (Cloudflare Pages)

本项目为纯静态单页面应用，非常适合部署到 **Cloudflare Pages**（全球 CDN 加速、免费无限流量）。

### 部署步骤：
1. **推送到 GitHub 仓库**：
   `ash
   git init
   git add .
   git commit -m "feat: initial commit"
   # 在 GitHub 上创建新仓库后关联并推送
   git remote add origin https://github.com/你的用户名/你的仓库名.git
   git branch -M main
   git push -u origin main
   `
2. **连接 Cloudflare Pages**：
   - 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)。
   - 进入 **Workers 和 Pages** -> 点击 **创建应用程序** -> 切换到 **Pages** 选项卡。
   - 点击 **连接到 Git**，授权并选择刚推送的 GitHub 仓库。
3. **构建设置 (0 配置)**：
   - **框架预设 (Framework preset)**: None
   - **构建命令 (Build command)**: 留空
   - **构建输出目录 (Build output directory)**: 留空（或填 ./）
4. **完成部署**：
   - 点击 **保存并部署**，数秒后即可通过 xxx.pages.dev 访问你的 3D 数字孪生系统！
