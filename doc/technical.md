# Technical

## 1. 技术栈

- 游戏：Rhythm Machine
- 类型：tool
- 简述：Tap the grid, make a beat — 8 instruments × adjustable 4–32 steps, 7 genre presets that auto-fit, and an AI prompt to spit out a starting groove
- 框架 / 语言 / 构建：JavaScript, Vite
- 渲染方式：DOM/CSS
- 依赖摘录：vite@^5.1.0
- 平台元信息：meta.title=Rhythm Machine；cover_url=/poster.png；category=tool；uuid=d3b8d8b4-ecba-4ac9-8b35-30a2f9c02677

## 2. 目录结构

- `index.html`：Vite/浏览器入口，挂载根节点和基础 meta。
- `vite.config.js`：配置构建、插件和相对路径 base。
- `package.json`：定义 npm 脚本、依赖和工程名称。
- `meta.json`：平台发布元信息，包含标题和封面。

关键源码模块：

- `src/`：源码目录。

## 3. 核心模块

- 状态管理与节奏：通过 React 状态与定时器处理倒计时、阶段推进或生成节奏。
- 渲染方式：DOM/CSS，样式由 CSS/Less 和组件结构共同完成。
- 碰撞 / 更新：未发现独立物理引擎，主要由用户操作和状态切换驱动。
- 音频：未发现独立音频模块，当前以视觉和文案反馈为主。
- Aigram 运行时：接入 `@shared/runtime` 或平台桥接能力，用于用户、资料页、分享、通知或平台 API。

## 4. 扩展点

- 改玩法参数：优先查找 `src/` 内大写常量、hooks、主组件顶部配置或关卡数组。
- 换素材：替换 `public/`、`src/img/` 或源码 import 的图片/音频文件，并保持相对路径。
- 调视觉：修改主样式文件中的颜色、间距、动画时长、网格尺寸和响应式规则。
- 改文案：修改 i18n 字典、组件内标题按钮文案，保持 zh/en 同步。
- 加平台能力：在已有 `@shared/runtime`、useGameSave、排行榜、墙或通知调用附近扩展，避免另起一套存储。
