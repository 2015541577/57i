# 手机租赁统一后台系统（支持支付宝预授权 & 芝麻信用免押）

本系统是一整套面向租赁业务的小程序 + 后台管理平台，支持支付宝信用预授权、芝麻信用免押功能，并通过后台管理界面集中配置所有 API 参数。

## 📦 项目结构


## ✅ 支持功能

- 商品租赁系统（含库存、颜色、套餐、租期等）
- 芝麻信用授权 & 支付宝预授权冻结
- 系统设置界面：配置支付宝 AppID、私钥、公钥、服务ID 等
- 配置数据保存至数据库，可视化后台操作
- 权限控制：配置页面仅管理员可访问

## 🛠️ 宝塔部署指南（简要）

1. 宝塔面板新建站点，绑定 xnzapp 和 xnzope-main
2. 使用 PM2 启动 xnzshop-main 后端服务：
```bash
cd xnzshop-main
npm install
pm2 start index.js
导入 sql_system_config.sql 到你的 MySQL 数据库

配置 nginx 反向代理 /api 到 localhost:4000

后台登录 ➜ 系统管理 ➜ API配置，填写支付宝/芝麻参数

意事项
所有 API 配置项请在生产环境中填写真实可用的参数

芝麻信用授权地址需要备案后才能接入正式服务
# Node
node_modules/
dist/
.env
pm2.log

# Build
build/
*.log
*.tmp

# IDE
.vscode/
.idea/
.DS_Store
npm-debug.log*
