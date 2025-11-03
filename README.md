# Farcaster 自动机器人
用于自动化操作 Farcaster / Warpcast 的脚本

# 作者与讨论
关于该软件的讨论及其工作原理，请前往 [Telegram 群组](https://t.me/x_0xJohn)。

#)。

# 功能特性
脚本同时以两种模式并行运行：发布帖子和执行随机操作。

### 发布帖子：
**1 - 通过 ChatGPT 生成。**
可以设置数量、延迟、主题、帖子长度。

**2 - 解析 Telegram 频道。**
需要从您的 Telegram 账户订阅所需频道，并将其添加到 `tg_channels.txt` 列表中。
首次运行脚本时，需要在您的 Telegram 账户中授权。之后会话将被保存。
每个 Farcaster 账号绑定一个特定的 TG 频道。可以解析并发布带有图片的帖子。

### 随机操作：
**1 - 点赞**

**2 - 评论：** 通过 ChatGPT 生成主题评论或使用 `comments.txt` 文件中的随机评论。

**3 - 关注 关注**

**4 - 转发**

所有操作均在特定分类中找到的随机帖子上执行。可以在 `FEED_KEY` 中更改此分类。您可以设定任意一组操作，它们将以随机顺序执行。

---

# Farcaster 自动机器人启动指南

### 步骤 步骤 1：下载并安装 Python
从 [python.org](https://www.python.org/) 下载并安装最新版本的 Python。
在安装前务必勾选 "Add Python to PATH" 选项。

### 步骤 2：检查 Python 和 pip 是否安装成功
打开命令提示符，输入以下命令来检查 Python 和 pip 的安装情况：
```sh
python --version
pip --version
```

### 步骤 3：从 GitHub 下载 Farcaster 自动机器人代码
[点击此处下载](https://github.com/0x-John/Farcaster-Auto-Bot)

### 步骤 4：安装依赖项
在命令提示符中，切换到项目文件所在的文件夹，然后安装依赖项：
```sh
cd 你的项目文件夹路径
pip install -r requirements.txt
```
（要在指定文件夹直接打开命令提示符，可以在文件夹地址栏中输入 `cmd` 后按回车）

### 步骤 5：配置 `data/config.py` 文件
***Telegram API** - 如果您想从 Telegram 频道发布帖子，则需要填写此项。
***ChatGPT API** - 如果您想使用 AI 生成帖子，则需要填写此项。
***GPT_PROXY** - 用于访问 ChatGPT 的独立代理。不能是俄罗斯或乌克兰 IP。格式：`http://用户名:密码@主机:端口`
***动作配置** - 根据您的需求填写完整的动作列表。
***帖子限制和延迟** - 设置动作之间的延迟时间（秒）以及通过 ChatGPT 发布的帖子数量。

### 步骤 6：填写 `data` 文件夹中的所有文本文件
***comments** - 如果希望使用文件中的评论，则需要填写。可以通过 ChatGPT 生成一系列中性评论并添加到这里。
***mnemonics** - **必填！** 助记词短语。创建账户时可以获得。
***proxy** - **必填！** 工作使用的代理。每行对应 `mnemonics.txt` 文件中的一行。
***tg_channels** - 如果希望从 TG 发布帖子，则需要填写。每行对应 `mnemonics.txt` 文件中的一行。格式：`@频道@频道地址`

### 步骤 7：运行脚本
使用以下命令在代码所在文件夹中运行脚本：
```sh
python main.py
```
