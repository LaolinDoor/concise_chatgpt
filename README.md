# concise_chatgpt简明教程

# 宗旨

本文宗旨是通俗、易懂、简练的方式介绍chatgpt，以便大家更好的使用。

chatgpt网址：https://chat.openai.com/

openai官方文档：https://platform.openai.com/docs/introduction

# 写在前面

chatgpt是什么？下面是chatgpt的回答

![image-20230331200414579](C:\Users\linzi\Desktop\BaiduSyncdisk\upGithub\chatgpt简明教程\img\image-20230331200414579.png)

你只要记住四个字就行了---“回答问题”，如果不够，再加两字---智能，他是迄今为止，最好的聊天模型，这里的最好是相对其他如Sifi，小度等聊天助手而言，他的出现确实令人惊艳，也确实能解决你的很多问题，但我希望你还是不要过度依赖chatgpt。记住chatgpt归根到底是人类智慧的产物，而你是一个人，万物之灵长，你有思想，有意识，有温度，甭管这个世界发展成什么样，你都应该去掌控他，而不是被他所左右。闲言少叙，开始。

# 发展历程

1. GPT（2018年）：OpenAI发布了第一代生成预训练Transformer（GPT）模型。这一版本采用了Transformer架构，通过无监督学习方法进行训练，为自然语言生成任务奠定了基础。
2. GPT-2（2019年）：OpenAI发布了GPT-2，该模型在参数量和训练数据集方面进行了扩展，显著提升了自然语言处理任务的性能。GPT-2表现出更好的生成内容的真实性和连贯性，引发了关于潜在风险和滥用的讨论。
3. GPT-3（2020年）：OpenAI发布了GPT-3，当时规模最大的语言模型之一，拥有1750亿个参数。GPT-3在各种自然语言处理任务上表现出非常高的准确性和连贯性。
4. GPT-4.0（2023）在模型规模、训练技术、多任务学习和推理效率等方面都有所改进.

# 原理简介

关于chatgpt的原理介绍，网上有很多，云山雾罩，很多人看的很费解，我将用你能听的懂的话讲述。

先给chatgpt海量的数据，进行学习。学习单词，短语，句子，形成自己的规律。回答时类似汉字接龙游戏，由第一个字根据规律生成第二个字，由第二个字生成第三个字，以此类推，形成一个完整的回答。但这样的出的答案不可控，为了得出可控的答案，对chatgpt提供范例学习，使chatgpt规范化。但这又会产生另一个问题，chatgpt会变得僵化，没有新意，给出的答案会程式化，模版化。为了让ChatGPT具有更好的创新性和适应性，采用强化学习方法，通过与人类互动，对其回答进行评价和奖励，使模型不断调整和改进，以生成更准确和合适的回答。

这是chatgpt原理简单介绍，实际过程更为复杂。

# 快速入门

## 提示--原则

1. chatgpt虽然不是人，只是一个工具，没有思想，没有意识，但你可以可以把它当做一个人来沟通。
2. 尽可能详细描述你的问题。
3. 举例说明，举例说明也是对chatgpt的一种训练。
4. 尽量使用英语提问。
5. 最好的指令就是自己写的，没有人比你更清楚，你想要什么。

## 提示--示例

1. 如果你不知道如何向ChatGPT询问你的问题，只需问

```
“举例说明向chatgpt问问题”
```

2. 角色扮演

```
我想让你充当销售，你要销售楼房，利用网络，自媒体，目标群体是30岁左右的工薪阶层。
```

3. 捕捉你的写作风格把你的写作提供给ChatGPT。

```
评估下面文本的风格、声音和语调。写一篇具有相同风格、声音和语气的新文章，新文章主题是[插入你想要的主题] 

[在这里插入您的文本]
```

4. temperature，这是调节chatgpt接口api中的参数，取值范围在0(保守)和1(创造性)之间。在你的提示后，尝试添加“请使用temperature为0.9”，内容会更有创意。

```
写一篇关于宇宙的文章，请使用temperature为0.9
```

5. 如果你使用ChatGPT获得的文章在使用时有“抄袭”警告，要修改提示词，告诉ChatGPT使用特定的风格和色调。

```
写一篇关于水泵的文章，重点是压力和流量，并说明压力如何与流量关系。使用诙谐的语气
```

**建议：一般情况下，不要想着绕开OpenAI content policy，有封号危险。**

**好了，到这，已经知道chatgpt是什么，大体上怎样使用了。**

# 模型

为满足不同应用场景、任务复杂性、计算资源和成本限制的需求，ChatGPT 提供了多个预训练模型，如text-davinci-003、text-curie-001，text-davinci-edit-002等，如果大家有这方面的需求，可以选择使用。

## 参数使用

现在介绍一下在预训练模型下，参数的使用，以达到对模型的微调。以text-davinci-003为例。

1. Temperature

   取值范围（0-1），对生成答案的多样化产生影响。比如说，预生成的答案有这几个选项，

   原始概率分布：

   - 苹果：0.2
   - 香蕉：0.3
   - 梨子：0.01
   - 橙子：0.15
   - 草莓：0.2

   当Temperature取值为0.1时，

   - 苹果：0.2 ^ (1 / 0.1) = 1024
   - 香蕉：0.3 ^ (1 / 0.1) = 3486.8
   - 梨子：0.01 ^ (1 / 0.1) = 1
   - 橙子：0.15 ^ (1 / 0.1) = 107.4
   - 草莓：0.2 ^ (1 / 0.1) = 1024

   概率就会变为：

   - 苹果：1024 / (1024 + 3486.8 + 1 + 107.4 + 1024) ≈ 0.218
   - 香蕉：3486.8 / (1024 + 3486.8 + 1 + 107.4 + 1024) ≈ 0.744
   - 梨子：1 / (1024 + 3486.8 + 1 + 107.4 + 1024) ≈ 0.0002
   - 橙子：107.4 / (1024 + 3486.8 + 1 + 107.4 + 1024) ≈ 0.023
   - 草莓：1024 / (1024 + 3486.8 + 1 + 107.4 + 1024) ≈ 0.218

   同理，当Temperature取值为1时，概率就是原始概率。

   可以看到，当Temperature取值越小，原本概率大的答案选项，呈现在你面前的概率，就越大；

   Temperature取值越大，其他概率的答案呈现在你面前的概率越大，会有更多种回答的选择给你。

   **总结**：较低的 `temperature` 值，生成的回答简单、连贯、保守且容易预测；较高的 `temperature` 值，会生成更有创意和多样性的答案。

2. Top P

   取值范围（0-1），就是设定累计概率值。再拿前面的例子举例，

   原始概率分布：

   - 苹果：0.2
   - 香蕉：0.3
   - 梨子：0.01
   - 橙子：0.15
   - 草莓：0.2

   当Top p值取0.5时，生成的答案，只取概率由高到低累计到0.5范围内的值，在此例中，只取苹果（0.2），香蕉（0.3），二者累计概率就是0.5，生成的答案，就是其中之一，当然生成香蕉的概率会更高。

   在具体应用中，要结合你的实际场景，选择temperature和Top p值搭配使用。比如（仅供参考）：

   - 新闻摘要    Temperature（0.6）Top p（0.8）
   - 创意写作   Temperature（0.9）Top p（0.6）
   - 客服           Temperature（0.3）Top p（0.7）

3. Maximum length

   生成文本的token最大长度。chatgpt通过将文本分解为token来理解和处理文本。token可以是单词，也可以是字符。粗略的可以认为，对于英语文本来说，1个token大约是4个字符或0.75个单词。值得注意的一点，chatgpt对提示和答案相加值设限。对于大多数模型，是2048或4000个token，或大约1500或3000个单词)。

4. Stop sequences

   设置文本在生成时，遇到什么文本时就终止。比如说，你设置Stop sequences为"!"感叹号，在生成文本时，出现"!",就不在继续生成文本。

5. Frequency penalty

   控制生成文本中同一个词的重复程度。比如Frequency penalty设置为0时，同一个词，可能就会多次重复出现；设置为2时，就会大大降低一个词重复出现的概率。设置合适的Frequency penalty值可以使生成的文本既不会过于重复，又能保持自然。

6. Presence penalty

   控制生成文本中相同语义的重复程度。如果Frequency penalty是在“形”的层面，那Presence penalty则说的是“神”的层面。较低的值生成的文本倾向于语义重复，而较高的值则会抑制这种重复现象。值得注意的是，较高的 Presence penalty 可以使生成的文本更具创造力和多样性，但也可能导致一些语义不清的输出。

7. Best of

   设置生成备选答案的数量，之后根据评分机制（如生成概率）选择一个最佳答案呈现给你。

8. Inject start text

   当你提供一个起始文本时，模型将以这个文本为基础，生成与其相关的后续内容

9. Inject restart text

   模型正在生成文本时，可以接着在提示中，加入内容，模型会按照重新加入后的提示，做调整，继续生成答案。

   

   # 实例演示

   [使用chatgpt写高考作文]: (../使用chatgpt写高考作文.md)
   [chatgpt终端聊天应用]: (../简单chatgpt终端聊天应用.md)

   

# 有用的关于chatgpt的Chrome 扩展

扩展有很多，经过使用，以下是我觉得比较好的。

- [ChatGPT for Google](https://chrome.google.com/webstore/detail/chatgpt-for-google/jgjaeacdkonaoafenlfkkkmbaopkbilf)   您可以让搜索引擎页面直接显示 ChatGPT 的答案。

- [Voice Control for ChatGPT](https://chrome.google.com/webstore/detail/voice-control-for-chatgpt/eollffkcakegifhacjnlnegohfdlidhn) 扩展ChatGPT与语音控制和朗读。

- [sharegpt-google](https://chrome.google.com/webstore/detail/sharegpt-share-your-chatg/daiacboceoaocpibfodeljbdfacokfjb)    与他人共享 ChatGPT 聊天记录可以生成各种格式，例如链接、图像和 PDF。

- [chatgpt-writer-google](https://chrome.google.com/webstore/detail/chatgpt-writer-write-mail/pdnenlnelpdomajfejgapbdpmjkfpjkp)   使用 ChatGPT 生成完整的电子邮件和消息。所有网站都支持它，并且对 Gmail 有更好的支持。

- [chatgpt-prompt-genius-google](https://chrome.google.com/webstore/detail/chatgpt-prompt-genius/jjdnakkfjnnbbckhifcfchagnpofjffo)   发现、共享、导入和使用最适合 ChatGPT 的提示。

  

  **学习了以上内容，你已经可以熟练应用chatgpt了，至于其他关于chatgpt的内容，如果你是一般用户，不必过分关注，你只要想着如何写出更好的提示词或指令（我更喜欢用提示词这个词，有一种平等沟通的感觉），更好的处理你的问题，就足够了。把chatgpt当作你的宠物，好好调教他，他会给你更多的惊喜！**

  

  **此文我会持续更新，发现了有趣的内容，我会补充进去。如果觉得对你有帮助，可以点个关注，谢谢**

  
