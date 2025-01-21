## 本文内容

ChatGPT 的 **Power Automate 插件** 允许您直接从 ChatGPT 对话中创建、列出和运行云端流。您可以使用该插件创建在 ChatGPT 之外运行的即时、自动或预定流，或者运行具有来自 **Skills Plugins** 连接器的 **从 Copilot 运行** 触发器的流。

## 先决条件

- 具有 [ChatGPT Plus](https://bit.ly/bewildcard) 订阅的 OpenAI 帐户。
- 有权使用标准连接器创建流的 Power Automate 帐户。ChatGPT 的 Power Automate 插件目前不支持个人 Microsoft 帐户以及国家/地区和美国政府云中的帐户。

> **步骤：**
> 1. 登录到 [ChatGPT](https://bit.ly/bewildcard)。
> 2. 如果您以前没有使用过插件，请转到 **设置** -> **Beta 功能**，并启用 **插件** 开关。
> 3. 开始新的聊天，并使用顶部的模型选择器选择 **GPT-4**。
> 4. 将鼠标悬停在 GPT-4 上，然后选择 **插件**。
> 5. 在聊天顶部，选择 **未启用插件**，然后选择 **插件商店**。
> 6. 在插件商店中搜索 **Power Automate** 并选择 **安装**。
> 7. 使用您的 Power Automate 帐户登录并授权 OpenAI 连接到您的 Microsoft 帐户。

## 使用插件根据提示创建流

当您使用与创建流或自动化相关的提示时，ChatGPT 会通过 Power Automate 插件响应一个预览和创建云端流的链接。在您审阅并保存之前，流不会运行。以下是一些示例提示：

- 设置一个自动程序，每天早上给我发电子邮件，告诉我 Planner 中未完成的任务。
- 帮我创建一个自动化程序，当我的经理给我发送一封高度关注的电子邮件时，我会收到通知。
- 创建一个流，当项目添加到 SharePoint 中的文件夹时，会向我发送电子邮件。

**示例：**  
以下是一个使用 Power Automate 插件创建流的屏幕截图：  
![示例流](https://learn.microsoft.com/zh-cn/power-automate/media/use-chatgpt-plugin/create-flow.png)

## 使用插件来列出和运行流

您可以使用 ChatGPT 中的 **从 Copilot 运行** 触发器运行流，并根据流的标题和描述提供提示，例如 **发送电子邮件**、**发布到 Teams** 或 **添加到 Planner**。ChatGPT 会返回一个运行流的链接，您可以在提交流运行之前检查输入。

要检索 ChatGPT 可用的所有流的列表，请使用以下提示：

- 列出我的流。
- 显示我的流。
- 我的所有流是什么？

ChatGPT 会返回使用 **从 Copilot 运行** 触发器的流及其详细信息的表。

## 控制和隐私

从 ChatGPT 和其他基于大型语言模型 (LLM) 的 Copilot 体验中调用云端流时，请注意以下事项：

- ChatGPT 不会直接创建流，而是根据提示返回一个指向可能流的链接。用户需要在 Power Automate 门户中完成流的创建。
- 只有使用 **从 Copilot 运行** 触发器创建的流才能从 ChatGPT 中发现。
- ChatGPT 无法直接调用流运行，用户可以在提交之前检查运行细节和输入参数。
- 插件设置时，ChatGPT 不会共享用户连接或数据。

## 环境支持

目前，创建和运行的流需要在租户的默认环境中。未来将支持选择非默认环境来关联插件。

## 常见问题解答

### 什么是 Skills Plugins 连接器？

Skills Plugins 连接器是一个新的内置连接器，包括 **从 Copilot 运行** 触发器和 **响应 Copilot** 操作。它使 ChatGPT 和 Microsoft Copilot 能够独立于您的其他流来发现和运行云端流。

### 如何管理“从 ChatGPT 运行的流可以使用哪些连接器和操作”？

[Power Platform 数据丢失防护 (DLP) 策略](https://bit.ly/bewildcard) 可控制云端流使用哪些连接器和操作，包括具有 **从 Copilot 运行** 触发器的流。管理员可以从 [Power Platform 管理中心](https://bit.ly/bewildcard) 管理这些策略。

### 我的租户和 Power Platform 环境中的所有流都与 ChatGPT 共享吗？

否，只有使用 **从 Copilot 运行** 触发器的流对 ChatGPT 可见。即使对于这些流，也只有流的名称和描述是可访问的，以便 ChatGPT 确定何时调用流。

---

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)