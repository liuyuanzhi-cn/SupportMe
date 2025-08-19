


# SupportMe 🎁

一个基于 **React + TypeScript** 开发的「打赏 / 点赞」组件。  
支持 **微信/支付宝打赏二维码**、**点赞统计**、**打赏记录管理**、**多主题样式**，可用于个人博客或内容网站。  

支持两种引入方式：  
- ✅ 通过 **npm 包** 安装并使用  
- ✅ 通过 **iframe 嵌入** 使用（零配置）

---

## ✨ 功能特性
- [x] **打赏功能**：微信/支付宝二维码，感谢弹窗
- [x] **点赞功能**：展示点赞数，支持感谢提示
- [x] **打赏记录管理**：管理员添加用户名、金额、时间
- [x] **多主题样式**：支持 `light` / `dark` / `colorful` / `minimal`
- [x] **配置化**：支付二维码、感谢文字、主题、是否显示按钮等
- [x] **后台设置**：输入管理员密码后可修改配置
- [x] **双引入方式**：npm 包 或 iframe 嵌入
- [x] **后端支持**：PostgreSQL + Node.js（Express/Fastify/NestJS 可选）

---

## 📦 安装与使用

### 方式一：通过 npm 引入（推荐）
```bash
npm install support-me
# 或者
yarn add support-me
````

在项目中使用：

```tsx
import { SupportMe } from "support-me";

export default function SupportWrapper() {
  return (
    <SupportMe
      wechatQr="/img/wechat.png"
      alipayQr="/img/alipay.png"
      thanksText="感谢支持，您的鼓励是我前进的动力！"
      theme="dark"
      showLike={true}
      showReward={true}
      apiBaseUrl="https://api.example.com"
      adminPassword="S3cR3t!"
    />
  );
}
```

在 Docusaurus 的 `.mdx` 文件中：

```mdx
<SupportWrapper />
```

---

### 方式二：通过 iframe 嵌入

无需安装，直接在页面中加入：

```html
<iframe src="https://support-me.vercel.app" width="100%" height="400"></iframe>
```

---

## ⚙️ 配置参数

| 配置项              | 类型                                             | 默认值         | 说明         |
| ---------------- | ---------------------------------------------- | ----------- | ---------- |
| `wechatQr`       | `string`                                       | -           | 微信支付二维码链接  |
| `alipayQr`       | `string`                                       | -           | 支付宝支付二维码链接 |
| `thanksText`     | `string`                                       | `"感谢您的支持！"` | 打赏感谢文字     |
| `theme`          | `"light" \| "dark" \| "colorful" \| "minimal"` | `"light"`   | 固定的主题样式选择  |
| `showLike`       | `boolean`                                      | `true`      | 是否显示点赞按钮   |
| `showReward`     | `boolean`                                      | `true`      | 是否显示打赏按钮   |
| `showRecordPage` | `boolean`                                      | `true`      | 是否显示记录页面入口 |
| `apiBaseUrl`     | `string`                                       | -           | 后端 API 地址  |
| `adminPassword`  | `string`                                       | -           | 管理员访问密码    |

---

## 🗄️ 后端说明

* **数据库**：PostgreSQL
* **ORM**：Prisma
* **API**：

  * `POST /api/support/reward` —— 添加打赏记录（需管理员密码）
  * `GET /api/support/reward` —— 获取打赏记录
  * `POST /api/support/like` —— 点赞 +1
  * `GET /api/support/like` —— 获取点赞次数
  * `POST /api/support/config` —— 保存配置（需管理员密码）
  * `GET /api/support/config` —— 获取配置

推荐部署：**Vercel + Supabase**

---

## 🚀 开发与调试

```bash
# 克隆项目
git clone https://github.com/yourname/support-me.git
cd support-me

# 安装依赖
npm install

# 启动开发
npm run dev

# 打包构建
npm run build
```

---

## 📜 许可证

[MIT License](./LICENSE)

---

## ❤️ 致谢

如果这个项目对你有帮助，可以点一个 ⭐ Star 支持一下！



