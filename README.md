# My-Ph.D.-Journey
此库总结了本人在博士科研过程中取得的成果以及遇到过的一些问题。
## 目录
- [一、我的成果](#一我的成果)
  - [1.1 已发表论文](#11-已发表论文)
  - [1.2 申请专利](#12-申请专利)
- [二、做实验&写论文遇到的一些问题](#二做实验写论文遇到的一些问题)
  - [2.1 torch版本-cuda版本-驱动版本对应问题](#21-torch版本-cuda版本-驱动版本对应问题)
  - [2.2 同样的LaTex项目，在不同电脑上编译出来结果不同](#22-同样的latex项目在不同电脑上编译出来结果不同)
  - [2.3 VSCode更改LaTex编译输出路径后，执行bibtex命令会报错](#23-vscode更改latex编译输出路径后执行bibtex命令会报错)
  - [2.4 论文投稿相关总结](#24-论文投稿相关总结)
  - [2.5 Pycharm与VSCode对比](#25-pycharm与vscode对比)
  - [2.6 VSCode最新版本无法连接SSH服务器](#26-vscode最新版本无法连接ssh服务器)
## 一、我的成果
### 1.1 已发表论文
1. **Zhang X**, Wang H, Wang C, et al. [MoMD Transformer: adaptive multi-modal fault diagnosis via knowledge transfer with vibration-current signals](https://www.sciencedirect.com/science/article/pii/S1566253525011418)[J/OL]. _Information Fusion_, 2026, 130: 104079. （SCI中科院1区TOP，IF=15.5）
2. **Zhang X**, Wang H, Wang C, et al. [Time-segment-wise feature fusion transformer for multi-modal fault diagnosis](https://www.sciencedirect.com/science/article/pii/S0952197624015161)[J]. _Engineering Applications of Artificial Intelligence_, 2024, 138: 109358. （SCI中科院1区TOP，IF=8.0）
3. **Zhang X**, Wang H, Wang C, et al. [A Safe-Domain Generative Adversarial Network with Transformer for Noisy Imbalanced Fault Diagnosis](https://ieeexplore.ieee.org/document/10152558)[C]//_2023 26th International Conference on Computer Supported Cooperative Work in Design (CSCWD)_. IEEE, 2023: 363-368. （CCF-C，EI会议）
4. Wang C, Yin T, Wang H, **Zhang X**, et al. [Unknown intervention-aware neural Granger causal discovery via Kullback-Leibler divergence constraint](https://www.sciencedirect.com/science/article/pii/S1474034625011784)[J/OL]. _Advanced Engineering Informatics_, 2026, 71: 104285.
5. Yin C, Luo J, Ye Q, **Zhang X**. [AdaptGeo: Parameter-Efficient Cross-View Geo-Localization via Frozen Foundation Model and Transformer Adapter](https://ieeexplore.ieee.org/abstract/document/11262226)[J]. _IEEE Transactions on Geoscience and Remote Sensing_, 2025, 63: 1-19.
6. Wang C, Wang H, **Zhang X**, et al. [A transformer-based industrial time series prediction model with multivariate dynamic embedding](https://ieeexplore.ieee.org/abstract/document/10750033/)[J]. _IEEE Transactions on Industrial Informatics_, 2024.
7. Wang H, Wang C, Liu Q, **Zhang X**, et al. [A data and knowledge driven autonomous intelligent manufacturing system for intelligent factories](https://www.sciencedirect.com/science/article/pii/S0278612524000785)[J]. _Journal of Manufacturing Systems_, 2024, 74: 512-526.
8. Zuo L, Wang H, **Zhang X**, et al. [Channel-Time Attention Based Patch-Attribute Alignment for Zero-Shot Fault Diagnosis](https://ieeexplore.ieee.org/document/10831666)[C]//_2024 IEEE International Conference on Systems, Man, and Cybernetics (SMC)_. IEEE, 2024: 5137-5142.

### 1.2 申请专利
1. **张笑寒**, 刘敏, 徐高威. 数据与机理融合的工控多模态生成式预训练模型构建方法: 上海市, CN118940108A[P]. 2024-11-12
2. **张笑寒**, 徐高威, 刘敏. 基于低秩适应和token剪枝的复杂动态系统多任务模型微调方法: 上海市, CN118643876A[P]. 2024-09-13

## 二、做实验&写论文遇到的一些问题
### 2.1 torch版本-cuda版本-驱动版本对应问题
25年秋季学期，因为某些现在已想不起来的原因想要使用高版本的torch，发现实验室服务器的cuda版本太低不支持，尝试升级cuda版本，又发现新的cuda版本和显卡驱动版本也不匹配，服务器一度崩溃，经过n次的重置环境变量，以及重启主机，得以修复。再也不敢轻易升级服务器一些软件的版本。

### 2.2 同样的LaTex项目，在不同电脑上编译出来结果不同
主要体现在参考文献的字体大小不一致（对比如下图），经Gemini的分析得知，这和texlive的版本有关。而latex可以在线选择不同版本的texlive进行编译，发现最新的texlive 2025会把参考文献字体编译的特别大，之后统一了两台电脑的texlive版本，问题解决。

<img src="https://cdn.nlark.com/yuque/0/2026/png/63764939/1774405232179-204bb1fa-59d9-4c84-b6ea-326a6fbed2a6.png" width="344" title="" crop="0,0,1,1" id="W4xBw" class="ne-image"><img src="https://cdn.nlark.com/yuque/0/2026/png/63764939/1774405277966-4fd43fc1-9e39-4927-8314-a9063573158a.png" width="336" title="" crop="0,0,1,1" id="ue8cbc721" class="ne-image">

### 2.3 VSCode更改LaTex编译输出路径后，执行bibtex命令会报错
为了LaTex项目文件夹的整洁与管理方便，选择更改默认设置（[VsCode配置Latex编译环境并且指定输出目录_latex编译输出-CSDN博客](https://blog.csdn.net/lyxichigoichie/article/details/125961850?spm=1001.2014.3001.5506)），编译时将中间文件输出都到"./Build"文件夹，但是有关bibtex的执行都会报错，最终上网寻找到解决方案：[bibtex因openout_any=p拒绝编译](https://hyliang96.github.io/posts/b812214a/#:~:text=%E8%8B%A5%E7%BC%96%E8%AF%91%E6%97%B6,%E4%BC%9A%E6%8A%A5%E9%94%99)。

### 2.4 论文投稿相关总结
IEEE：可使用任一作者的账号投稿，待到稿件正式提交后，系统按照投稿时填写的各作者邮箱自动创建老mc系统的账号，此时所有共同作者均可以在新老系统上看到稿件详情（登录账号的邮箱必须是投稿时填写的邮箱）。投稿账号的邮箱能接收到新提交的创建通知，和其他共同作者一起都能接收到任意阶段的提交通知和decision letter，接收邮箱为投稿时填写的各邮箱。

Elsevier：需使用通讯作者的账号提交，待到稿件正式提交后，所有共同作者均可收到身份确认链接（在投稿系统上填写的邮箱地址接收），然后可用任一账号确认后看到稿件详情。通讯作者邮箱（不确定是投稿时所填邮箱还是投稿账号绑定邮箱）能接收到新提交的创建通知、各阶段提交通知和decision letter，而其他共同作者只会接收到新稿件首次提交时的身份确认通知和录用后的right通知，各阶段的decision letter和返修提交通知均无法收到。

| **出版社** | **能否收到稿件创建通知** | **其他作者能否看到提交物** | **其他作者能否收到decision letter** | **能否收到返修提交通知** |
| :---: | :---: | :---: | :---: | :---: |
| IEEE | 仅投稿账号所绑邮箱 | 能，需使用投稿系统上所填邮箱对应的账号 | 能，在投稿系统上所填邮箱接收 | 能，在投稿系统上所填邮箱接收 |
| Elsevier | 仅投稿账号所绑邮箱 | 能，可使用任一账号确认身份链接（首次投稿时发送至投稿系统上所填的各作者邮箱） | 否 | 否 |


即重点在于投稿时在系统上所填写的邮箱，而不是投稿账号的绑定邮箱，更不是论文首页写的邮箱。

关于投稿系统上的Funder选择：

1）国家自然科学基金：National Natural Science Foundation of China

2）重点研发计划：Ministry of Science and Technology of the People's Republic of China

### 2.5 Pycharm与VSCode对比
Pycharm：Debug功能好，看变量方便；建立索引快，find in usage等；带参运行方便；远程ssh虽然映射很乱（本地不同的项目会映射到远程服务器的同一个文件夹），但可以和本地保持同步。

VSCode：轻量，开源，远程ssh直接操控服务器，更适合AI Agent功能，虽然少了很多功能（比如自动格式化），但是都可以通过安装扩展解决。

### 2.6 VSCode最新版本无法连接SSH服务器
由于pycharm太过笨重了，尽管具有优越的debug功能，但还是决定放弃pycharm转用VSCode。然而发现VSCode在连接实验室服务器时弹出“远程主机不满足运行VSCode服务器的先决条件”，经上网搜索资料得知，1.85.2之后的VSCode版本已经要求glibc>=2.28。解决方法为：

1）直接把高版本的VSCode降到1.85，但是就无法使用写代码的AI Agent功能了

2）官网给出了patchelf方法，结合一些网友的经验贴尝试3次（github包，miniforge安装和homebrew安装），但仍然失败，只得放弃。三个经验贴的地址为：

[“远程主机不满足运行 VS Code 服务器的先决条件”解决 - Undefined443 - 博客园](https://www.cnblogs.com/Undefined443/p/18830733)

[2026新版，远程主机可能不符合 glibc 和 libstdc++ VS Code 服务器的先决条件 | Bubble](https://blog.hexsix.me/posts/fix-vscode-remote-ssh-glibc-problem/)

[GitHub - MikeWang000000/vscode-server-centos7: Run the latest vscode-server on RHEL/CentOS 7!](https://github.com/MikeWang000000/vscode-server-centos7)

3）安装便携版的1.85版本，此时本地有两个版本的VSCode共存，一个主写代码，一个主跑实验。目前只得这样凑合使用。
