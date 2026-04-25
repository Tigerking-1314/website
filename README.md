# 慢病用药小管家（原型）

一个可直接部署的网页原型，用于展示慢病患者的「问诊－购药－用药－续方」连贯服务闭环。

## 已实现功能

- 用药计划：药品、慢病、剂量、服药时间、开始/疗程、库存、医嘱备注
- 今日用药：自动生成今日待服清单，支持一键“已服用/撤销”
- 库存与重复购药提示：按“库存 / 每日消耗”估算剩余天数，提示是否该续方/购药（避免重复购买）
- 复诊/续方提醒：显示距离日期的天数，并可导出 `.ics` 添加到系统日历
- 通知提醒：支持浏览器 Notification（在页面运行时按时弹出）
- 数据本地保存：使用 LocalStorage；支持 JSON 导入/导出
- 轻量 PWA：包含 `manifest.json`、`sw.js`

## 本地运行

直接打开 `index.html` 即可。

若要在本地起一个静态服务（推荐，便于 Service Worker 正常工作）：

```bash
python3 -m http.server 5173
```

然后打开 `http://localhost:5173/`。

## 部署（生成可提交链接）

### 方式 A：GitHub Pages

1. 把仓库推到 GitHub
2. GitHub 仓库 Settings → Pages
3. Build and deployment：选择 `Deploy from a branch`
4. Branch：`main` / folder：`/ (root)`
5. 保存后等待部署完成，即可得到链接

### 方式 B：Vercel

1. 用 Vercel 导入该仓库
2. Framework 选择 `Other`（静态）
3. Build Command 留空；Output Directory 留空
4. Deploy 后获得链接

