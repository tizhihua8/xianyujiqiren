# 🚀 Xianyu AutoAgent - 智能闲鱼客服机器人
根据[https://github.com/shaxiu/XianyuAutoAgent](https://github.com/shaxiu/XianyuAutoAgent) 项目改的 
做了多模型适配，增加了百炼的应用模式 http模式 可以自行拓展其他第三方的接口  
快递模块属于半成品还没调试好，用于对接我自己的寄快递小程序的，不需要请自行删除相关路由
real_xianyu_bot.py 是模拟真实登录机器人 就是说你可以不用拿另外一个咸鱼号去发 可以用这个直接测试机器人的忠诚度
由于不知道咋玩GUB的 所以代码我就新增了一个仓库 需要的自己下载吧
专为闲鱼平台打造的AI自动化客服系统，支持多大模型API，7×24小时自动值守，智能议价、上下文感知、专家协同。

## 🌟 主要特性
- **多模型支持**：OpenAI、阿里通义千问、Chutes、自定义HTTP等
- **多专家协同**：分类、议价、技术、物流等多场景切换
- **灵活配置**：意图识别、议价策略、商品信息均可配置
- **自定义提示词**：prompts目录下可自定义各类专家提示词
- **日志与监控**：loguru日志，支持后台监控
- **测试脚本**：test_bot.py命令行交互测试

## 🏗 目录结构
```
.
├── main.py                # 主程序入口
├── XianyuAgent.py         # 核心逻辑
├── real_xianyu_bot.py     # 真实机器人实现
├── XianyuApis.py          # 闲鱼API交互
├── config_manager.py      # 配置管理
├── context_manager.py     # 上下文管理
├── requirements.txt       # 依赖列表
├── setup.py               # 安装脚本
├── test_bot.py            # 测试脚本
├── data/
│   └── chat_history.db    # 对话历史数据库
├── providers/             # 多模型API适配
├── prompts/               # 提示词模板
├── utils/                 # 工具函数
├── images/                # 项目图片
├── mock_data/             # 预留模拟数据
├── .env                   # 环境变量（需自建）
├── config.json            # 系统配置
├── xianyu_config.json     # 业务配置
└── ...
```

## ⚙️ 安装与运行

### 环境要求
- Python 3.8+

### 安装依赖
```bash
pip install -r requirements.txt
```
或
```bash
python setup.py install
```

### 配置环境
1. 复制`example.env`为`.env`，填写API_KEY、COOKIES_STR等参数
2. 配置`config.json`和`xianyu_config.json`（可选）

### 启动机器人
```bash
python main.py
```

### 测试机器人
```bash
python test_bot.py
```
支持商品信息获取、会话重置、上下文管理等功能。

## 🔌 多模型API配置

支持OpenAI、通义千问、Chutes、自定义HTTP等，详见`.env`和`config.json`说明。只需切换`PROVIDER_TYPE`即可。

## 📝 提示词自定义

`prompts/`目录下可自定义各类专家提示词（如`price_prompt.txt`、`tech_prompt.txt`等）。

## 🛠 贡献方式

欢迎PR和Issue，详见贡献指南。

## 🧩 依赖说明

- openai
- websockets
- loguru
- python-dotenv
- requests
- asyncio
- dashscope
- aiohttp
- flask、httpx（setup.py中）

## 🗂 其他说明

- `data/chat_history.db`：对话历史数据库
- `mock_data/`：预留模拟数据目录
- `images/`：文档与展示图片
- `__pycache__/`、`xianyu_agent.egg-info/`：可忽略


