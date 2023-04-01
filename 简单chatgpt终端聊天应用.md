此文介绍的是在终端状态下，与chatgpt聊天的简单应用程序，使用python编写。

1. 安装OpenAI的Python库：

```
pip install openai
```

2. 在命令行设置API密钥。密匙链接：https://platform.openai.com/account/api-keys

```
export OPENAI_API_KEY=【你的密匙】
```

3. 创建一个名为`chat_chatgpt.py`的Python文件，代码如下：

```python
import os
import openai

# 获取密匙
openai.api_key = os.getenv("OPENAI_API_KEY")

def chat_with_chatgpt(prompt):
    response = openai.Completion.create(
        model="text-davinci-003",
        prompt=prompt,
        temperature=0,
        max_tokens=100,
        top_p=1,
        frequency_penalty=0.0,
        presence_penalty=0.0,
        stop=["\n"]
    )

    return response.choices[0].text.strip()

if __name__ == "__main__":
    print("与ChatGPT聊天机器人开始对话，输入'退出'以结束对话。")

    history = "I am a highly intelligent question answering bot. If you ask me a question that is rooted in truth, I will give you the answer. If you ask me a question that is nonsense, trickery, or has no clear answer, I will respond with \"不知道\".\n\n"

    while True:
        user_input = input("你: ")
        if user_input.lower() == "退出":
            break

        history += f"Q: {user_input}\n"
        response = chat_with_chatgpt(history + "A: ")
        history += f"A: {response}\n"

        print(f"ChatGPT: {response}")
```

4. 在终端中运行以下命令启动程序：

```
py chat_chatgpt.py
```

你可以在终端与ChatGPT进行对话，输入你的问题或内容，然后按回车，ChatGPT将给出相应的回复。输入“退出”以结束对话。



5. 测试运行结果：

![image-20230331210359246](C:\Users\linzi\Desktop\BaiduSyncdisk\upGithub\chatgpt简明教程\img\image-20230331210359246.png)

大功告成！