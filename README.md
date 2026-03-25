# My-Ph.D.-Journal
## 一、我的成果
### 1.1 已发表论文
1. **Zhang X**, Wang H, Wang C, et al. [MoMD Transformer: adaptive multi-modal fault diagnosis via knowledge transfer with vibration-current signals](https://www.sciencedirect.com/science/article/pii/S1566253525011418)[J/OL]. _Information Fusion_, 2026, 130: 104079. （SCI中科院1区TOP，IF=15.5）
2. **Zhang X**, Wang H, Wang C, et al.<font style="color:rgb(34, 34, 34);"> </font>[Time-segment-wise feature fusion transformer for multi-modal fault diagnosis](https://www.sciencedirect.com/science/article/pii/S0952197624015161)[J]. _Engineering Applications of Artificial Intelligence_, 2024, 138: 109358. （SCI中科院1区TOP，IF=8.0）
3. **Zhang X**, Wang H, Wang C, et al. [A Safe-Domain Generative Adversarial Network with Transformer for Noisy Imbalanced Fault Diagnosis](https://ieeexplore.ieee.org/document/10152558)[C]//_2023 __<font style="color:rgb(34, 34, 34);">26th</font>__ International Conference on Computer Supported Cooperative Work in Design (CSCWD)_. IEEE, 2023: 363-368. （CCF-C，EI会议）
4. Wang C, Yin T, Wang H, **Zhang X**, et al. [Unknown intervention-aware neural Granger causal discovery via Kullback-Leibler divergence constraint](https://www.sciencedirect.com/science/article/pii/S1474034625011784)[J/OL]. _Advanced Engineering Informatics_, 2026, 71: 104285.
5. Yin C, Luo J, Ye Q, **Zhang X**. [AdaptGeo: Parameter-Efficient Cross-View Geo-Localization via Frozen Foundation Model and Transformer Adapter](https://ieeexplore.ieee.org/abstract/document/11262226)[J]. _IEEE Transactions on Geoscience and Remote Sensing_, 2025, 63: 1-19.
6. Wang C, Wang H, **Zhang X**, et al. [A transformer-based industrial time series prediction model with multivariate dynamic embedding](https://ieeexplore.ieee.org/abstract/document/10750033/)[J]. _IEEE Transactions on Industrial Informatics_, 2024.
7. Wang H, Wang C, Liu Q, **Zhang X**, et al. [A data and knowledge driven autonomous intelligent manufacturing system for intelligent factories](https://www.sciencedirect.com/science/article/pii/S0278612524000785)[J]. _Journal of Manufacturing Systems_, 2024, 74: 512-526.
8. Zuo L, Wang H, **Zhang X**, et al.<font style="color:rgb(34, 34, 34);"> </font>[Channel-Time Attention Based Patch-Attribute Alignment for Zero-Shot Fault Diagnosis](https://ieeexplore.ieee.org/document/10831666)[C]//_2024 IEEE International Conference on Systems, Man, and Cybernetics_ _(SMC)_. IEEE, 2024: 5137-5142.

### 1.2 申请专利
1. **张笑寒**, 刘敏, 徐高威. 数据与机理融合的工控多模态生成式预训练模型构建方法: 上海市, CN118940108A[P]. 2024-11-12
2. **张笑寒**, 徐高威, 刘敏. 基于低秩适应和token剪枝的复杂动态系统多任务模型微调方法: 上海市, CN118643876A[P]. 2024-09-13

## 二、做实验&写论文遇到的一些问题
### 2.1 torch版本-cuda版本-驱动版本对应问题
25年秋季学期，因为某些现在已想不起来的原因想要使用高版本的torch，发现实验室服务器的cuda版本太低不支持，尝试升级cuda版本，又发现新的cuda版本和显卡驱动版本也不匹配，服务器一度崩溃，经过n次的重置环境变量，以及重启主机，得以修复。再也不敢轻易升级服务器一些软件的版本。

### 2.2 同样的latex项目，在不同电脑上编译出来结果不同
主要体现在参考文献的字体大小不一致（对比如下图），经Gemini的分析得知，这和texlive的版本有关。而latex可以在线选择不同版本的texlive进行编译，发现最新的texlive 2025会把参考文献字体编译的特别大，之后统一了两台电脑的texlive版本，问题解决。

<img src="https://cdn.nlark.com/yuque/0/2026/png/63764939/1774405232179-204bb1fa-59d9-4c84-b6ea-326a6fbed2a6.png" width="344" title="" crop="0,0,1,1" id="W4xBw" class="ne-image"><img src="https://cdn.nlark.com/yuque/0/2026/png/63764939/1774405277966-4fd43fc1-9e39-4927-8314-a9063573158a.png" width="336" title="" crop="0,0,1,1" id="ue8cbc721" class="ne-image">

### 2.3 VSCode最新版本无法连接SSH服务器
由于pycharm太过笨重了，尽管具有优越的debug功能，但还是决定放弃pycharm转用vscode。然而发现VSCode在连接实验室服务器时弹出“远程主机不满足运行VSCode服务器的先决条件”，经上网搜索资料得知，1.85.2之后的VSCode版本已经要求glibc>=2.28。解决方法为：

1）直接把高版本的VSCode降到1.85，但是就无法使用写代码的AI Agent功能了

2）官网给出了patchelf方法，结合一些网友的经验贴尝试3次（miniforge安装和homebrew安装），但仍然失败，只得放弃。三个经验贴的地址为：

[“远程主机不满足运行 VS Code 服务器的先决条件”解决 - Undefined443 - 博客园](https://www.cnblogs.com/Undefined443/p/18830733)

[2026新版，远程主机可能不符合 glibc 和 libstdc++ VS Code 服务器的先决条件 | Bubble](https://blog.hexsix.me/posts/fix-vscode-remote-ssh-glibc-problem/)

[GitHub - MikeWang000000/vscode-server-centos7: Run the latest vscode-server on RHEL/CentOS 7!](https://github.com/MikeWang000000/vscode-server-centos7)

3）安装便携版的1.85版本，此时本地有两个版本的VSCode共存，一个主写代码，一个主跑实验。目前只得这样凑合使用。
