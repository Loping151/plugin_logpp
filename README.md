
# Log++(Logpp)插件：微信Bot统计GPT token数量/计费估计、管理

现仅支持GPT-3.5, GPT-4。使用其他语言模型时，统计结果仍然为对GPT而言的token数，但可以用于估算。


## 插件描述

按群聊/用户 实际与GPT的交互内容 写入 csv表格，结合Excel进行公式化统计，便于计费/估算和控制用量。

本插件基于[chatgpt-on-wechat](https://github.com/zhayujie/chatgpt-on-wechat). 但本人偏离主仓库太多，可能存在兼容性错误。

## 环境要求

```
pip install tiktoken
```
参考 https://github.com/openai/openai-cookbook/blob/main/examples/How_to_count_tokens_with_tiktoken.ipynb
## 使用说明

直接下载本仓库在plugin文件夹中并在plugin/config.json里启用。

本插件统计的消息是本体回复以后产生的内容。此时的输入消息只会是实际输给GPT的语句，或者类似画图的不经过GPT的其他功能语句，都统计在内，但回复是图像的消息我标注了tag。实际上sdwebui插件的画图不会经过我的逻辑，没有修饰回复环节。

输出消息是GPT的输出消息或其他功能语句，同样统计在内。

至于输入是图像的，由于我写了读图插件（https://github.com/Loping151/plugin_readim），输入会变为读图插件读图后的text，或者其他插件处理的结果。

每个日期会存在一份csv文件。失败的请求不算在内。

### 效果展示

![image](https://github.com/Loping151/plugin_logpp/assets/97866915/ceebe6ee-2c38-47b4-9d90-36ad6a50d2fe)

里面出现了一些指令，是测试时临时bug，可以忽略。
