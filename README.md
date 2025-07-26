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
