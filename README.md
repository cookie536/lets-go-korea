# 让我们去韩国旅行 🇰🇷

为中文零基础学习者设计的28天韩国旅行韩语学习网站。

**在线学习：[lets-go-korea.netlify.app](https://lets-go-korea.netlify.app/)**

从韩文字母和拼读开始，学习酒店入住、餐厅点餐、购物支付、交通问路等旅行交流。

## 功能

- 6节字母与拼读入门，覆盖21个元音、19个辅音、音节组合和基础收音/连音。
- 28天课程：240个第一册原始词条、中文语法拆解、阅读翻译与140道小测。
- 8段旅行情景对话、常见标识和数词速查。
- 韩语合成语音播放，支持慢速和语音选择。
- 按实际学词日期，在第1、3、7、14、21天安排复习。
- 学习进度在当前浏览器本地保存，可导入/导出JSON备份。

## 使用

访问在线网站，先进入“零基础入门”，再按28天课程学习。无需构建或安装依赖。

本地运行：

```bash
python3 -m http.server 8765 --bind 127.0.0.1
```

浏览器打开 `http://127.0.0.1:8765/`。也可以直接用现代浏览器打开 `index.html`。

运行检查（需要Node.js）：

```bash
node checks.mjs
```

## 项目文件

| 文件 | 用途 |
| --- | --- |
| `index.html` | 网页入口与导航 |
| `style.css` | 桌面与手机布局 |
| `app.js` | 学习交互、语音、评分及复习逻辑 |
| `data.js` | 词汇、课程、语法、题库和对话 |
| `checks.mjs` | 数据、课程渲染、题目评分与复习日期检查 |
| `docs/` | 数据来源、上游许可说明与源数据指纹 |

## 部署到Netlify

此项目是静态网站，无需构建命令。Netlify发布目录为仓库根目录 `.`，配置见 `netlify.toml`。可以手动上传项目文件夹，也可以在Netlify连接此GitHub仓库后按提交自动部署。

本仓库只保存源码。已有的Netlify网站不会因为上传GitHub而自动建立关联；如需自动更新，在Netlify现有项目中连接本仓库。

## 教学来源与限制

原始词汇来自 [Open Yonsei Korean Vocabulary](https://github.com/Amulopapa67/open-yonsei-korean-vocabulary)，v0.1.0第一册（`data/json/vol-01.json`）。本课按旅行实用性筛选240个不同韩文词条，不是语料统计的词频排名。`data.js`中的 `words[].source` 保留源词条字段和复核状态。

课程安排、字母讲解、语法、阅读翻译、练习、答案、情景对话及标识为AI生成教学内容，不是延世教材原文或官方课程。模拟价格、路线和营业信息不作为真实旅行依据。词条的原始复核状态未提升为重新认证。

语音使用浏览器及设备上的韩语合成语音，不是教材录音；需设备支持韩语声音。本站不录制麦克风，不提供自动发音评分。机制参考 [MDN SpeechSynthesis](https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/getVoices)。

## 隐私

进度、错题、自评和练习笔记仅保存于浏览器 `localStorage`。本仓库不含个人学习进度、账号密钥或内部托管配置；换设备前请自行导出学习进度。不同网站域名与本地文件的进度不会自动互通。

## 署名与许可

Open Yonsei Korean Vocabulary contributors, “Open Yonsei Korean Vocabulary dataset”, version 0.1.0, CC BY-SA 3.0。

本项目对源词汇进行了筛选、分类与重排，添加教学设计和网页交互，未修改上游仓库的原始词汇文件。本课程及网页作为数据衍生物按 [CC BY-SA 3.0](LICENSE.md) 共享。第三方词典字段继续遵循上游来源与第三方许可条款；参见 `docs/UPSTREAM_SOURCES.md` 与 `docs/THIRD_PARTY_NOTICES.md`。本项目与延世大学及其韩国语学堂无从属、赞助或背书关系。
