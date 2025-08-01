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
            https://kq4b3vgg5b.feishu.cn/wiki/QYONwI5tPiLEzLkMcWdcUCshnwd
跟做了第一个项目：使用CherryStudio+高德MCP打造个人出行规划助理，下载CherryStudio并在其中跳转申请大模型的Api（早已有了），上高德开放平台：https://console.amap.com/dev/id/select弄好MCP，在CherryStudio设置好MCP服务即可。用起来很傻瓜方便，并未涉及到设计这块，只是用了。
将AI出行助手生成的行程（文字版），在加上下面这段提示语↓，放到ChatGPT4o中，即可生成行程图（把以上的三天旅游规划生成三张现代风格的手帐插画图提示词，我希望插画偏可爱风格，每张插画是要包含景点、交通和天气的全部信息，插画是以人物旅行为主视角（比如一个女生旅行），手写文字。）
主流的MCP工具网站：
MCP官方服务器合集：https://github.com/modelcontextprotocol/servers
MCP Github热门导航：https://github.com/punkpeye/awesome-mcp-servers
Smithery：https://smithery.ai/
MCP导航：https://mcp.so/
阿里云百炼：https://bailian.console.aliyun.com/?tab=mcp

