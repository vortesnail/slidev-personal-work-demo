---
theme: default
title: 陈鑫 - Get笔记 - 个人转正述职
author: 陈鑫
aspectRatio: 16/9

# https://sli.dev/features/drawing
drawings:
  persist: false
transition: slide-left
fonts:
  local: Monserrat, Roboto Mono
hideInToc: true
mdc: true
---

# 转正述职汇报

AI产品部 · 2025.9.11

<div class="uppercase text-sm tracking-widest flex items-center">
陈鑫<img src="https://piccdn2.umiwi.com/fe-oss/default/MTc1NjgwMzk1NTgz.png" class="inline rounded-full w-4 ml-1"/>
</div>

<div class="abs-bl mx-14 my-12 flex">
  <img src="/logo-single.png" class="h-9">
  <div class="ml-3 flex flex-col text-left">
    <div class=text-sm>Get笔记</div>
    <div class="text-[0.75rem] opacity-50">加入于2025.04.17</div>
  </div>
</div>


---
layout: center
---

<div class="flex gap-[80px] items-center">
  <TableCard title="工作成果" description="主要介绍试用期的工作成果产出" />
  <TableCard title="未来规划" description="说一说接下来我计划要做的" />
</div>

---
layout: center
---

# 笔记分享

<div class="flex gap-[80px] items-center">
  <IphoneShare class="shrink-[0]"/>
  <FunctionDescription
    title="功能说明"
    description="笔记分享功能让信息流动更自由，通过简单操作实现高效传递，告别图片文件传输的繁琐，让信息同步更便利顺畅"
    :items="[{ text: 'APP 内分享功能实现' }, { text: '站外 H5 所有笔记笔记类型分享页面实现' }, { text: 'WEB 首次接入大数据埋点' }]"
    data="H5 分享页 PV 为 <b>34335</b>，APP 分享按钮点击总次数为 <b>8644</b>"
  />
</div>

---
layout: center
---

# Get日报

<div class="flex gap-[80px] items-center">
  <FunctionDescription
    title="功能说明"
    description="每日生成专属自己的日报，复盘前一天记了哪些笔记、关注订阅的博主有哪些更新"
    :items="[{ text: 'APP 端日报卡片和详情开发' }, { text: 'WEB 端完整日报卡片开发' }, { text: '自定义日报链接解析插件' }]"
    data="订阅日报人数为 <b>2407</b>，查看日报人数为 <b>1260</b>"
  />
  <IphoneDaily class="shrink-[0]"/>
</div>

---
layout: center
---

# 多图笔记

<div class="flex gap-[80px] items-center">
  <IphoneImage class="shrink-[0]"/>
  <FunctionDescription
    title="功能说明"
    description="一次最多上传10张图片，一键智能转笔记，极大方便用户多图记录"
    :items="[{ text: 'APP 多图上传逻辑实现' }, { text: 'WEB、APP 多图笔记详情页面适配' }]"
  />
</div>

---
layout: center
transition: fade
---

<div
  v-motion
  class="text-[42px]"
  :initial="{ x: -80 }"
  :enter="{ x: 0, y: 0 }"
>
  更多...
</div>

---
layout: center
---

<div class="flex flex-wrap gap-[20px] justify-between">
  <MoreCard v-click order="1" title="拍书笔记" description="参与 APP 端拍书上传笔记的列表、搜索、添加功能开发" />
  <MoreCard v-click order="2" title="导入音视频" description="WEB 端导入音视频功能开发" />
  <MoreCard v-click order="3" title="AI助手" description="WEB 端 AI 助手参与开发部分功能" />
  <MoreCard v-click order="4" title="项目优化相关" description="Web 端项目引入各种 lint 工具，强制 setup ts 语法开发，提升项目可维护性和代码健壮性" />
  <MoreCard v-click order="5" title="Get笔记桌面端" description="从零到一搭建起Get笔记的桌面端应用，打好基础，利于后续迭代" />
  <NextCard v-click />
</div>

---
layout: center
---

<Macbook />

---
layout: center
---

# 接下来做什么？

> 前提：根据产品需求灵活变通

<br>

<v-clicks>

- 实现「拉新」功能的完整链路
  - APP 入口页面、海报，以及 H5 的页面对接
  - 笔记分享数据埋点和奖励信息追踪
- Get笔记桌面端 v1.0.0 上线
  - 编辑和预览笔记的 markdown 样式调整（也有功能增加）
  - 会议录音完整交互实现
  - 网页 AI 助手
- Web端功能和页面重构
  - 编辑器
  - 整体布局、交互

</v-clicks>

---
layout: center
---

<h1>感谢</h1>
