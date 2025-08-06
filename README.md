个人的学习路线
2025.07.25：观看视频，视频链接为：
            【这就是RAG 一看就懂的个人知识库架构】 https://www.bilibili.com/video/BV19RJhzyEWN/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
            【从零写AI RAG 个人知识库】 https://www.bilibili.com/video/BV168j7zCE6D/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
            【AI知识图谱 GraphRAG 是怎么回事？】 https://www.bilibili.com/video/BV1zoKuzoENM/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
            【RAG 工作机制详解——一个高质量知识库背后的技术全流程】 https://www.bilibili.com/video/BV1JLN2z4EZQ/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
注册得到了Gemini的api key，放到了我的环境变量中。跑通了以上第二个视频中的demo。
总结：抽象地理解了RAG，接触到了GraphRAG。简而言之就是：一份文档，对其进行分块chunk（这里大有学问），然后借助embedding模型将chunk向量化（https://huggingface.co/spaces/mteb/leaderboard中对各种Embedding模型做了评测），然后存入向量数据库，配置好语言模型和嵌入模型和向量数据库之后，直接提问。问题首先到嵌入模型哪里被变为向量，然后从向量数据库中找出几个和问题向量最接近的（算法有余弦相似度、欧氏距离、点积等），再对这几个最接近的进行重排（用cross-encoder模型，不懂这个但也是计算相似度的），然后将重排后的前几个和问题一起给到语言模型。


2025.7.26：观看视频，视频链接为：
            【使用Python构建RAG系统 —— 用代码还原 RAG系统的每个细节】 https://www.bilibili.com/video/BV1wc3izUEUb/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
这个视频和昨天的demo视频相似，只是用的是jupyter notebook来写的代码且多了个重排环节（cross-encoder模型）

2025.7.27：观看视频，视频链接为：
            【【Qwen2.5-7B微调】30分钟手把手带你用Fine-Tuning微调Qwen2.5-7B，实现低成本微调行业大模型，全程干货，草履虫也能学会！！（附教程）】 https://www.bilibili.com/video/BV1RiPVe8Ei5/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
注册了AutoDL，从该视频中可以学到SSH远程控制服务器，该视频仅仅是对微调的一个展示，并未深入教学，就是带你很粗略地看了遍流程。

2025.7.28~29：【4小时打造垂域专属大模型，Qwen3企业级微调实战！详解数据集创建方法+微调流程+微调模型性能评估完整流程｜实现知识灌注、MCP能力增强、推理性能优化！】 https://www.bilibili.com/video/BV1YLE1zyEvX/?p=5&share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
这是个系列视频，看完了原理，主要是构造数据集得很小心，边训练还得兼顾不让模型出现灾难性遗忘。在自己的机器上折腾老半天，老是遇到各种各样的问题，决意明天在AutoDL上再折腾。

2025.7.30：观看视频，视频链接为：
            【【DeepSeek+LoRA+FastAPI】开发人员如何微调大模型并暴露接口给后端调用】 https://www.bilibili.com/video/BV1R6P7eVEtd/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
这个UP讲的细且文档做的好，适合我这种小白，可以多关注下这个UP主。跟着视频走了一遍流程（在AutoDL租算力、连接SSH到VSCode中的终端、执行了LLaMA-Factory 安装部署、从huggingface下载模型到LLaMA-Factory环境中、准备数据集微调最重要的还是数据集的构建、在LLama-Factory 的可视化微调界⾯进行微调无代码操作简单、微调完毕导出合并后的模型、创建fast-api环境通过 FastAPI 部署模型并暴露 HTTP 接⼝、然后做前后端工作我没做、还有如何开放服务端⼝到公⽹企业部署等UP主也不会哈哈）。

2025.7.31:观看视频，视频链接为：
            【【知识科普】【纯本地化搭建】【不本地也行】DeepSeek + RAGFlow 构建个人知识库】 https://www.bilibili.com/video/BV1WiP2ezE5a/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
下载ollama是一个本地部署运行和管理大语言模型的工具（它有自己的网页），上github下载Ragflow源代码（这里并不包含它运行所需的环境和依赖），下载Docker（是一个封装好的环境，但是下载会遇到一些困难），Ragflow的文档中还有关于docker的代码在相应文件夹运行即可下载到适配的docker的镜像，在本地访问端口启动载Ragflow即可，在浏览器中打开Ragflow然后设置知识库啥的。需要注意的是本地电脑不但要有内存，还要有运存！看了评论区会遇到诸多问题，遂决定放弃跟做。

2025.8.1:阅读文档，文档链接为：
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd  高德MCP打造出行助理
跟做了第一个项目：使用CherryStudio+高德MCP打造个人出行规划助理，下载CherryStudio并在其中跳转申请大模型的Api（早已有了），上高德开放平台：https://console.amap.com/dev/id/select弄好MCP，在CherryStudio设置好MCP服务即可。用起来很傻瓜方便，并未涉及到设计这块，只是用了。
将AI出行助手生成的行程（文字版），在加上下面这段提示语↓，放到ChatGPT4o中，即可生成行程图（把以上的三天旅游规划生成三张现代风格的手帐插画图提示词，我希望插画偏可爱风格，每张插画是要包含景点、交通和天气的全部信息，插画是以人物旅行为主视角（比如一个女生旅行），手写文字。）
主流的MCP工具网站：
MCP官方服务器合集：https://github.com/modelcontextprotocol/servers            
MCP Github热门导航：https://github.com/punkpeye/awesome-mcp-servers
Smithery：https://smithery.ai/
MCP导航：https://mcp.so/
阿里云百炼：https://bailian.console.aliyun.com/?tab=mcp

2025.8.2:阅读文档，文档链接为：
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd  MateGen：Jupyter智能引擎
相当于在Vscode中的通义千问，只是是在Jupyter中的。也可以部署到本地，那就相当于下载了个豆包APP。
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd  从零复现DeepSeek v3模型训练过程
很详细甚至到了代码中方法的讲解，包含了分词器训练、预训练、后训练即全量指令微调+DPO强化学习微调。还讲了wandb用来记录训练过程，清洗构建数据集也讲了点。对模型训练及微调我已有较多理解，就不跟做了。

2025.8.3:阅读文档，文档链接为：
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd  数据分析Agent DB-GPT项目实战
跟做了，因为我认为数据中大有机会！这个项目对AI数据分析应该是第一，但是很依赖LLM的质量，调用GPT-4效果会好点。注册了智谱的API，下载了FinalShell进行了使用，可以使用SSH链接挺好用的。

2025.8.4:阅读文档，文档链接为：
c
一个L2级的Agent级的Agent ，本质上就是⼀个具备推理能⼒的聊天机器⼈。部署Open WebUI是⼀个开源项⽬ ，该项⽬提供⼀个⽤⼾友好的Web界⾯ ，使开发者和⾮技术⽤⼾都 能够⽅便地与机器学习模型、⼤模型等进⾏交互。实现了可交互的问答界面。
然后造一份商家后台的商品信息模拟数据（这里教了Navicat可视化的工具连接 MySQL），然后构建大模型能够调用的函数并使得大模型能够正经用上该函数方法（可以说是Function Calling的纯手动实现教程）。讨论了并行函数调用和如何接入多个工具。
在Open WebUI接入开源大模型，个性化定制智能客服，给智能客服添加私有工具（即自己写的价格查询、结构查询函数）。没做，已理解不做。
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd  从零训练专属大模型技术实战合集
和前面从零复现DeepSeek v3模型训练过程是一样的，多了编写OpenAI风格的API。

2025.8.5:阅读文档，文档链接为：
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd  B站动态数据&舆情分析智能体
大模型本身是无法采取任何行动的，它们的作用只是用来输出文本，所以他只能作为大脑在接收信息后给出指令。
这里没给出教程，只是介绍了该项目，展示了一个正经的agents是怎么个框架，还讲解了langchain、langgraph。

2025.8.6:阅读文档，文档链接为：
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd  CrewAI+LangChain搭建Multi Agent
弄OpenAI的apikey弄了老半天，太麻烦了，虚拟卡平台被管控了，其他的平台成本太大50美刀算了。
尝试用OpenRouter来代替，能调用免费模型但是OpenRouter和后续的LangChain有点不兼容，要在LangChain中实例化LLM的时候，对应的模型有点难得找（找不到deepseek、qwen），或者说问题不在这，而是OpenRouter弄出的模型无法在LangChain中实例化模型。
附带的视频有对着OpenAI和LangChain文档讲，看了就知道大概怎么调用，后面忘了可以重看。


观看视频：
            【OpenRouter国内免费使用！聚合超多主流大模型，免费还不怕封号！】 https://www.bilibili.com/video/BV16GRPYXEzC/?share_source=copy_web&vd_source=54937f7fc746a085e167e38a94abf401
视频里教了怎么使用OpenRouter，它类似OpenAI的调用，但是实际上里头调用的不一定是GPT。OpenRouter本身并不是一个模型商，它实际上是模型调用的整合平台。

















