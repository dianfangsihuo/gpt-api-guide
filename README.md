# RA API 接入指南 — 0.08 超低倍率、全模型不降智，一站式接入 GPT 等主流大模型

在日常开发 AI 应用、Agent 工作流或使用各类 AI 编程/对话客户端时，开发者最关心的三件事：**模型质量是否稳定（不降智）、调用成本是否可控、接口接入是否简单**。

**RA API** 提供兼容 OpenAI 格式的统一 API 网关，主营 **GPT** 系列并聚合 Claude、Gemini、Grok 等主流大模型，以 **0.08 超低倍率** 与 **全模型不降智** 的官方级体验，仅用一套代码即可快速完成接入。

- **平台地址**：[https://djb.qtgpt.top](https://djb.qtgpt.top)
- **Base URL**：`https://djb.qtgpt.top/v1`
- **联系 / 交流 QQ**：`2821074913`

---

## 一、核心优势

1. **主营 GPT 系列，全模型不降智**
   - 专注高质量模型通道，确保模型输出逻辑、代码能力与长上下文推理保持原汁原味，不掺水、不降智。
2. **0.08 超低倍率，性价比拉满**
   - 仅 **0.08 倍率** 计费，大幅降低个人开发者日常编程辅助、自动化脚本以及企业高频调用的 Token 成本。
3. **统一 OpenAI 协议，零成本迁移**
   - 完全兼容 OpenAI SDK 与标准接口格式，现有项目只需修改 `base_url` 和 `api_key`，即可无缝切换。
4. **多模型生态与清晰后台**
   - 除主营 GPT 外，同时支持 Anthropic（Claude）、Google（Gemini）、xAI（Grok）等主流生态；后台提供集中密钥管理、实时用量统计与调用日志，成本一目了然。

---

## 二、快速接入指南

### 1. 获取 API Key
1. 访问平台地址：[https://djb.qtgpt.top](https://djb.qtgpt.top)
2. 注册并登录账号（支持邮箱注册，如有优惠码可在注册时填写）。
3. 在控制台创建并复制你的 `API Key`。

### 2. 基础配置信息
- **Base URL**：`https://djb.qtgpt.top/v1`
- **Chat Completions 接口**：`https://djb.qtgpt.top/v1/chat/completions`

---

## 三、多语言调用代码示例

### Python 示例（官方 `openai` SDK）

```python
from openai import OpenAI

client = OpenAI(
    api_key="你的_API_KEY",
    base_url="https://djb.qtgpt.top/v1"
)

response = client.chat.completions.create(
    model="gpt-4o",  # 可按需替换为平台支持的 GPT 及其他模型 ID
    messages=[
        {"role": "system", "content": "你是一个专业的全栈开发工程师。"},
        {"role": "user", "content": "用 Python 写一个支持异步重试的 HTTP 请求封装函数。"}
    ],
    temperature=0.7
)

print(response.choices[0].message.content)
```

### JavaScript / Node.js 示例

```javascript
import OpenAI from "openai";

const client = new OpenAI({
  apiKey: "你的_API_KEY",
  baseURL: "https://djb.qtgpt.top/v1",
});

async function main() {
  const completion = await client.chat.completions.create({
    model: "gpt-4o",
    messages: [
      { role: "user", content: "简要对比 Redis 的 RDB 和 AOF 持久化机制。" }
    ],
  });

  console.log(completion.choices[0].message.content);
}

main();
```

### cURL 测试命令

```bash
curl https://djb.qtgpt.top/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer 你的_API_KEY" \
  -d '{
    "model": "gpt-4o",
    "messages": [{"role": "user", "content": "Hello!"}]
  }'
```

---

## 四、常见客户端配置

如果你平时使用 **Cursor、Cherry Studio、NextChat、沉浸式翻译** 等支持自定义 OpenAI 接口的工具，只需在设置中填入：
- **接口地址（Base URL）**：`https://djb.qtgpt.top/v1`
- **API Key**：在控制台创建的密钥

---

## 五、联系方式

- **平台地址**：[https://djb.qtgpt.top](https://djb.qtgpt.top)
- **联系 QQ**：`2821074913`
