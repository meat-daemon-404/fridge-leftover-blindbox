# AI 冰箱剩菜盲盒 · Fridge Leftover Blindbox

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Recipes](https://img.shields.io/badge/本地四级菜谱池-1%2C009_道_%2B_577_张本地成品图-00b894)](https://github.com/meat-daemon-404/fridge-leftover-blindbox)
[![Tests](https://img.shields.io/badge/Unit_Tests-61%2F61_Passing-2ea44f)](https://github.com/meat-daemon-404/fridge-leftover-blindbox)

> **微信小程序 + H5 双端运行的「冰箱剩菜盲盒抽取 + 智能菜谱匹配 + 厨房全流程管家」应用** —— 内置 **1,009 道四级本地真实菜谱库** 与 **577 张本地化高清成品图**，支持赛博朋克 Canvas 动态菜名海报兜底、B 站教学视频直达、AI 口味改良、7 天周计划、跨菜谱购物清单与全屏语音免触控厨房模式。

## 核心架构与功能矩阵

### 1. 1,009 道四级本地菜谱池与零破图视觉兜底
- **四级优先级匹配引擎**：
  1. **精选特调库（`iddzz`）**：高颜值创意料理与懒人快手菜。
  2. **一碗食单库（`abowl` · 360 道）**：自带 **577 张本地化实拍成品图（`abowl-imgs/`）** 与精确克数配比。
  3. **程序员做饭指南（`HowToCook` · 298 道）**：结构化量化步骤与避坑提示。
  4. **中华家常菜底库**：覆盖南北常见食材组合，确保任意剩菜组合 100% 抽中可用食谱。
- **三层视觉与视频增强**：优先展示实拍成品图 → 无图菜谱自动通过 Canvas 实时绘制**赛博朋克霓虹菜名海报卡** → 一键跳转 B 站对应高赞做菜视频。

### 2. 实用四件套（口味偏好 · AI 改良 · 购物清单 · 步骤倒计时）
- **口味偏好改写（`applyPrefs`）**：支持「少油/免辣/低盐/快手 15 分钟/一人食」一键改写调料用量与步骤说明。
- **云+端双模 AI 改良（`improve` 云函数 + `improveLocal` 本地回退）**：无论是否配置云开发密钥，均能针对缺失食材生成等效替换方案与风味升级建议。
- **跨菜谱累积购物清单**：自动合并多道菜谱的缺口食材并按生鲜分类汇总。
- **步骤内嵌倒计时器（`stepSeconds`）**：自动解析步骤中的“炖 15 分钟”“大火收汁 30 秒”并生成一键启动计时器。

### 3. 厨房管家四件套（周计划 · Meal Prep · 语音厨房模式 · 反向平替）
- **7 天三餐周计划与营养均衡评分**：一键排布一周食谱并导出集中采购单。
- **周末备菜指南（Meal Prep）**：将多道菜的洗切、焯水、腌制工序合并批处理。
- **全屏大字语音厨房模式**：做饭双手沾水时可通过语音指令或大按钮切换「上一步 / 下一步 / 朗读步骤 / 启动计时」。
- **食材反向平替搜索**：家里缺某味调料或配菜时，毫秒级检索口感与风味最接近的平替方案。

## 目录结构

```text
fridge-leftover-blindbox/
├── miniprogram/                 # 微信小程序与 H5 核心前端源码
│   ├── pages/                   # 盲盒抽取、菜谱详情、周计划、购物清单、全屏厨房模式页面
│   ├── utils/                   # 四级菜谱匹配器、applyPrefs、improveLocal、stepSeconds 解析器
│   └── abowl-imgs/              # 577 张本地化高清菜谱成品图
├── cloud/functions/             # 微信云开发 CloudBase 云函数（AI 剩菜组合推理与改良）
└── tests/                       # 61 项自动化单元测试（覆盖匹配、偏好改写、计时解析与管家逻辑）
```

## 快速开始与测试

```bash
git clone https://github.com/meat-daemon-404/fridge-leftover-blindbox.git
cd fridge-leftover-blindbox

# 运行全部 61 项单元测试
npm test
```

使用**微信开发者工具**导入项目根目录即可直接预览小程序端，或直接打开 H5 预览入口体验完整功能。

## 许可证

本项目基于 [MIT License](LICENSE) 开源。
