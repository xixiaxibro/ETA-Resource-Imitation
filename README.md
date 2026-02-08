# IPv6-Measurement-Resource

<!--
Copyright (c) 2026 Flynn

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
 Hawkins
-->

<h3 align="center">
    <img src="https://github.com/xixiaxibro/ETA-Resource-Imitation/blob/main/ETA.png">
</h3>

<h1 align="center">
    <p>IPv6 Measurement Resources</p>
    <p>IPv6网络测量相关研究资源汇总</p>
</h1>

<p align="center">
    <img src="https://img.shields.io/badge/status-maintained-brightgreen">
    <a href="https://github.com/xixiaxibro/ETA-Resource-Imitation/blob/main/LICENSE">
        <img alt="GitHub" src="https://img.shields.io/github/license/xixiaxibro/ETA-Resource-Imitation.svg?color=green">
    </a>
    <img src="https://img.shields.io/github/stars/xixiaxibro/ETA-Resource-Imitation">
    <img src="https://img.shields.io/github/forks/xixiaxibro/ETA-Resource-Imitation">
    <a href="https://github.com/xixiaxibro/ETA-Resource-Imitation/graphs/traffic">
    <img src="https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2Fxixiaxibro%2FETA-Resource-Imitation&label=visitor%20%20%20&labelColor=%23697689&countColor=%232ccce4&style=flat">
    </a>
    <a href="https://github.com/xixiaxibro/ETA-Resource-Imitation#contributors-"><img src="https://img.shields.io/badge/Contributors-8-orange.svg"></a>
</p>


**Note:**
- ⭐ **Please leave a <font color='orange'>STAR</font> if you like this project!** ⭐
- If you find any <font color='red'>incorrect</font> / <font color='red'>inappropriate</font> / <font color='red'>outdated</font> content, please kindly consider opening an issue or a PR. 
- We would greatly appreciate your contribution to this list, and you will appear in the [contributors✨](#contributors-)!

# Content
- [About](#about)
- [Datasets](#datasets)
- [Tools](#tools)
- [Survey & Benchmark](#survey-and-benchmark)
    - [Survey](#survey)
- [IPv6 Network Measurement & Analysis](#ipv6-network-measurement--analysis)
    - [IPv6 Address Discovery & Topology](#ipv6-address-discovery--topology)
        - [Algorithmic Categories](#algorithmic-categories)
            - [Applied Reinforcement Learning](#applied-reinforcement-learning)
            - [Applied ML/Deep Learning](#applied-mldeep-learning)
            - [Statistical & Density-based](#statistical--density-based)
        - [Generation Paradigms](#generation-paradigms)
            - [Static Generation](#static-generation)
            - [Dynamic Generation & Scanning](#dynamic-generation--scanning)
- [Research Groups](#research-groups)
- [Blogs](#blogs)
- [Tool Libraries and Frameworks](#tool-libraries-and-frameworks)
- [News and Updates](#news-and-updates)
- [Contributors 🌟](#contributors-)

# About
A curated knowledge base for IPv6 Network Measurement, specifically emphasizing target generation strategies, active security auditing, benchmark datasets, and leading research laboratories.



# Datasets

| Dataset | Category | Description | Source / Link | Status |
| --- | --- | --- | --- | --- |
| **IPv6 Hitlist** | **Core Seeds** | The standard active IPv6 address list (Gasser et al.). The primary baseline for liveness. | [IPv6 Hitlist](https://ipv6hitlist.github.io/) | 🟢 Daily |
| **Rapid7 FDNS** | **Core Seeds** | **(Project Sonar)** Forward DNS AAAA records. Massive source of active domains mapped to IPv6. | [Rapid7 Open Data](https://opendata.rapid7.com/) | 🟢 Regularly |
| **CAIDA Ark** | **Topology** | **(Formerly "Scamper")** Global traceroute data. Essential for verifying connectivity and path analysis. | [CAIDA Archipelago](https://www.caida.org/projects/ark/) | 🟢 Regularly |
| **CAIDA DNS Names** | **Topology** | IPv6 hostnames derived from active traceroutes (Reverse DNS). Useful for identifying infrastructure roles. | [CAIDA Catalog](https://www.google.com/search?q=https://www.caida.org/catalog/datasets/ipv6_dns_names_dataset/) | 🟢 Req. Access |
| **Censys Certs** | **Domains** | IPv6-ready domains extracted from X.509 Certificates (CT Logs). Requires BigQuery access. | [Censys Research](https://search.censys.io/data) | 🟡 Application |
| **Routeviews Prefix** | **Metadata** | **(AS Mappings)** Maps IP prefixes to Autonomous Systems (AS). Used for network-level aggregation. | [CAIDA / Routeviews](https://www.caida.org/catalog/datasets/routeviews-prefix2as/) | 🟢 Daily |
| **Tranco** | **Rankings** | A research-oriented top sites ranking, hardened against manipulation. | [Tranco List](https://tranco-list.eu/) | 🟢 Daily |
| **Majestic Million** | **Rankings** | Top 1M domains based on backlink analysis. | [Majestic](https://majestic.com/reports/majestic-million) | 🟢 Daily |
| **Cisco Umbrella** | **Rankings** | Top 1M domains based on DNS usage. (Note: Access policy varies). | [Cisco Umbrella](https://s3-us-west-1.amazonaws.com/umbrella-static/index.html) | 🟡 Variable |
| **Alexa Top 1M** | **Rankings** | **[Retired]** Historical web traffic ranking. Discontinued in May 2022. | [Archived](https://www.google.com/search?q=https://pypi.org/project/alexa-top-1m/) | 🔴 Retired |




# Tools

| Tool | Language | GitHub Repository | Description & Notes |
| --- | --- | --- | --- |
| **ZMap** | C | **[zmap/zmap](https://github.com/zmap/zmap)** | **[Standard]** ZMap v6 实际上已经合并进主分支了，不需要找单独的 ZMapv6 库。大多数发行版直接支持。 |
| **Masscan** | C | **[robertdavidgraham/masscan](https://github.com/robertdavidgraham/masscan)** | **[High-Speed]** 号称最快的异步端口扫描器。注意它的 IPv6 支持需要特定参数开启。 |
| **Nmap** | C/C++ | **[nmap/nmap](https://github.com/nmap/nmap)** | **[Auditing]** 世界上最著名的扫描器。不仅是扫描，更重要的是它的 NSE 脚本引擎。 |
| **Scamper** | C | **[CAIDA/scamper](https://www.caida.org/catalog/software/scamper/)** * | **[Topology]** CAIDA 的核心工具。*注：它主要通过 CAIDA 官网分发源码包，GitHub 上主要是镜像或非官方维护版。建议去官网下。* |
| **Yarrp** | C++ | **[cmand/yarrp](https://github.com/cmand/yarrp)** | **[Trace]** "Yelling at Random Routers Progressively". 极速拓扑发现工具，CMAND 团队维护。 |
| **XMap** | C | **[idealeer/xmap](https://github.com/idealeer/xmap)** | **[Research]** 基于 ZMap 改写，专门优化了 IPv6 探测效率。 |
| **Scanv6** | **Go** | **[IPv6-Security/scanv6](https://github.com/IPv6-Security/scanv6)** | **[New]** 6Sense的**Golang Scanner**。它是 **6SENSE** 系统的一部分，支持“黑名单”和“反馈循环”。 |


# Survey and Benchmark

## Survey

### 1. IPv6 Measurement & Evaluation

* [Target Acquired? Evaluating Target Generation Algorithms for IPv6](https://ieeexplore.ieee.org/document/10199073). P. Foremski. `IEEE INFOCOM 2023`. (针对目标生成算法的系统性评估)
* [Seeds of Scanning: Exploring the Effects of Datasets, Methods, and Metrics on IPv6 Internet Scanning](https://dl.acm.org/doi/10.1145/3646547.3688449). Lion Steger. `ACM SIGCOMM 2024`. (对扫描方法论与评估指标的深度剖析)
* [Unveiling IPv6 Scanning Dynamics: A Longitudinal Study Using Large Scale Proactive and Passive IPv6 Telescopes](https://dl.acm.org/doi/10.1145/3749221). Q. Lone. `ACM IMC 2024`. (关于IPv6扫描动态性的长期测量研究)
* [Censys: A Map of Internet Hosts and Services](https://dl.acm.org/doi/10.1145/3718958.3754344). Liz Izhikevich. `ACM SIGCOMM 2024`. (互联网资产测量的工业级基准与系统架构)

### 2. IPv6 Security & Protocol Optimization

* [A Survey on IPv6 Security Threats and Defense Mechanisms](https://link.springer.com/chapter/10.1007/978-3-031-06794-5_47). S. J. Ma. `CANS 2022`. (IPv6 安全威胁与防御机制综述)
* [IPv6 Routing Protocol for Low-Power and Lossy Networks Security Vulnerabilities and Mitigation Techniques: A Survey](https://dl.acm.org/doi/10.1145/3732776). K. Shaukat. `ACM Computing Surveys 2024`. (低功耗有损网络中 RPL 协议的安全性分析)
* [IPv6 routing protocol enhancements over low-power and lossy networks for IoT applications: A systematic review](https://www.google.com/search?q=https://www.tandfonline.com/doi/abs/10.1080/13614568.2022.2131349). T. Al-Janabi. `New Review of Hypermedia and Multimedia 2022`. (IoT 场景下的 IPv6 路由增强技术综述)
* [6TiSCH – IPv6 Enabled Open Stack IoT Network Formation: A Review](https://dl.acm.org/doi/10.1145/3536166). S. K. Singh. `ACM Computing Surveys 2022`. (IPv6 与 6TiSCH 协议栈网络构建综述)


# IPv6 Network Measurement & Analysis
## IPv6 Address Discovery & Topology
### Algorithmic Categories
#### Applied Reinforcement Learning
* [6Hit: A Reinforcement Learning-based Approach to Target Generation for Internet-wide IPv6 Scanning](https://ieeexplore.ieee.org/document/9488794). Bingnan Hou. `INFOCOM 2021`.[无源码] 
* [6Sense: Internet-Wide IPv6 Scanning and its Security Applications](https://www.usenix.org/conference/usenixsecurity24/presentation/williams). Grant Williams. `USENIX Security 2024`.[[code]](https://github.com/IPv6-Security/6Sense) 
#### Applied ML/Deep Learning
* [IPv6 Prefix Target Generation through Pattern and Distribution Learning using Vision-Transformer and Guided-Diffusion](https://ieeexplore.ieee.org/document/11044676). Yaochen Ren. `INFOCOM 2025`.[[code]](https://github.com/6ptg/6ptg)
* [6GAN: IPv6 Multi-Pattern Target Generation via Generative Adversarial Nets with Reinforcement Learning](https://dl.acm.org/doi/10.1109/INFOCOM42981.2021.9488912). Tianyu Cui.  `INFOCOM 2021`. [[code]](https://github.com/CuiTianyu961030/6GAN) 
* [6GCVAE: Gated Convolutional Variational Autoencoder for IPv6 Target Generation](https://dl.acm.org/doi/10.1007/978-3-030-47426-3_47). Tianyu Cui. `PAKDD 2020`. [[code]](https://github.com/CuiTianyu961030/6GCVAE)
* [6VecLM: Language Modeling in Vector Space for IPv6 Target Generation](https://dl.acm.org/doi/10.1007/978-3-030-67667-4_12). Tianyu Cui. `ECML PKDD 2020` [[code]](https://github.com/CuiTianyu961030/6VecLM)
* [6Forest: An Ensemble Learning-based Approach to Target Generation for Internet-wide IPv6 Scanning](https://ieeexplore.ieee.org/document/9796925) Tao Yang. `INFOCOM 2022` [[code]](https://github.com/Lab-ANT/6Forest)
* [6Graph: : A graph-theoretic approach to address pattern mining for Internet-wide IPv6 scanning](https://dl.acm.org/doi/10.1016/j.comnet.2021.108666). Tao Yang. `Computer Networks 2022`[[code]](https://github.com/Lab-ANT/6Graph)
#### Statistical & Density-based
* [Entropy/IP: Uncovering Structure in IPv6 Addresses](https://www.entropy-ip.com/2016-v6structures.pdf). Paweł Foremski. `IMC 2016` [[code]](https://github.com/akamai/entropy-ip/)
* [DET: Enabling Efficient Probing of IPv6 Active Addresses](https://ieeexplore.ieee.org/document/9698406). Guanglei Song. `IEEE/ACM Transactions on Networking 2022` [[code]](https://github.com/sixiangdeweicao/DET)
* [6Tree: : Efficient dynamic discovery of active addresses in the IPv6 address space](https://dl.acm.org/doi/10.1016/j.comnet.2019.03.010).Zhizhu Liu`Computer Networks 2019` [[code]](https://github.com/zhizhul/6tree)
* [6Scan: A High-Efficiency Dynamic Internet-Wide IPv6 Scanner With Regional Encoding](https://ieeexplore.ieee.org/document/10012428).Bingnan Hou  `IEEE/ACM Transactions on Networking 2023` [[code]](https://github.com/hbn1987/6Scan)
* [Search in the Expanse: Towards Active and Global IPv6 Hitlists](https://ieeexplore.ieee.org/document/10229089). Bingnan Hou `IEEE/ACM Transactions on Networking 2023` [无源码]
### Generation Paradigms
#### Static Generation
* Entropy (Entropy/IP)
* 6GCVAE
* 6VecLM
* 6GAN
* 6Graph
* 6Forest
#### Dynamic Generation & Scanning
* 6Tree
* DET
* 6Hit
* 6Scan
* 6Sense


# Research Groups
<details>
<summary>
    Chinese Academy of Sciences, University of Chinese Academy of Sciences/China
</summary>

* [Gang Xiong](https://people.ucas.ac.cn/~xionggang) (Institute of Information Engineering)
* [Kai Chen](https://people.ucas.ac.cn/~kaichen) (Institute of Information Engineering)
* [Qixu Liu](https://people.ucas.ac.cn/~liuqixu) (Institute of Information Engineering)
* [Guozhu Meng](https://people.ucas.ac.cn/~gzmeng) (Institute of Information Engineering)
* [Qingyun Liu](https://people.ucas.ac.cn/~0027674) (Institute of Information Engineering)
* [Zhigang Lu](https://people.ucas.ac.cn/~luzhigang) (Institute of Information Engineering)
* [Xiaodong Li](https://people.ucas.edu.cn/~LEE) (Institute of Computing Technology)
* [Zhenyu Li](http://www.ict.ac.cn/sourcedb_2018_ict_cas/cn/jssrck/201111/t20111114_3395505.html) (Institute of Computing Technology)
* [Yujun Zhang](https://people.ucas.ac.cn/~yujun) (Institute of Computing Technology)
* [Yuqing Zhang](https://people.ucas.ac.cn/~zhangyuqing) (School of Computer Science and Technology)
</details>

<details>
<summary>
    Tsinghua University/China
</summary>

* [Ke Xu](http://www.thucsnet.org/xuke.html)
* [Jiahai Yang](https://nmgroup.tsinghua.edu.cn/yjh/)
* [Haixin Duan](http://netsec.ccert.edu.cn/people/duanhx/)
* [Jianjun Chen](https://www.jianjunchen.com/)
* [Dan Li](https://www.cs.tsinghua.edu.cn/info/1126/3948.htm)
* [Yong Cui](https://www.cs.tsinghua.edu.cn/info/1126/3589.htm)
* [Mingwei Xu](https://www.cs.tsinghua.edu.cn/info/1126/3580.htm)
* [Xia Yin](https://www.cs.tsinghua.edu.cn/info/1126/3578.htm)
* [Qi Li](https://www.insc.tsinghua.edu.cn/info/1157/2851.htm)
* [Dan Pei](https://www.cs.tsinghua.edu.cn/info/1127/3597.htm)
* [Zhiliang Wang](https://www.cs.tsinghua.edu.cn/info/1127/3593.htm)
* [Chao Zhang](https://netsec.ccert.edu.cn/chs/people/chaoz/)
</details>

<details>
<summary>
Zhejiang University/China
</summary>

* [Shouling Ji](https://person.zju.edu.cn/sji#0)
* [Wenyuan Xu](https://person.zju.edu.cn/wyxu#0)
* [Meng Luo](https://person.zju.edu.cn/mengluo#0)
* [Kui Ren](https://person.zju.edu.cn/kuiren)
* [Fan Zhang](https://person.zju.edu.cn/fanzhang)
</details>

<details>
<summary>
Harbin Institute of Technology/China
</summary>

* [Weizhe (James) Zhang](https://homepage.hit.edu.cn/wzzhang)
* [Xiangzhan Yu](https://homepage.hit.edu.cn/yuxiangzhan)
* [Hui (Sophia) He](https://homepage.hit.edu.cn/huihe)
* [Junbao Li](https://homepage.hit.edu.cn/lijunbao)
* [Zhaoxin Zhang](https://homepage.hit.edu.cn/zhangzhaoxin)
</details>

<details>
    <summary>
        Beijing University of Posts and Telecommunications/China
    </summary>

* [Shize Guo](https://scss.bupt.edu.cn/info/1063/5386.htm)
* [Dongbin Wang](https://scss.bupt.edu.cn/info/1249/5098.htm)
* [Zhongliang Yang](https://scss.bupt.edu.cn/info/1247/5070.htm)
</details>

<details>
<summary>
    Beijing Institute of Technology/China
</summary>    
    
* [Changzhen Hu](https://cst.bit.edu.cn/szdw/jsml/bssds/ca94335a79114dbe9ae967e53ca86bec.htm)
* [Liehuang Zhu](https://cs.bit.edu.cn/szdw/jsml/wlkjaqxy/zlh/index.htm)
* [Meng Shen](https://cst.bit.edu.cn/szdw/jsml/bssds/86728e84066248b0b13bdf04f685817f.htm)
* [Xuhui Ding](https://cst.bit.edu.cn/szdw/jsml/bssds/711aba6ea79b41618a2f2fac616652a9.htm)
</details>

<details>
<summary>
    Beihang University/China
</summary>    
    
* [Jian Mao](https://shi.buaa.edu.cn/maojian/zh_CN/index.htm)
* [Sheng Hong](http://shi.buaa.edu.cn/hongsheng/zh_CN/index.htm)
* [Ying Gao](https://shi.buaa.edu.cn/gaoying/zh_CN/index.htm)
</details>
    
<details>
<summary>
Xi'an Jiaotong University/China
</summary>
    
* [Xiaohong Guan](https://www.xjtu.edu.cn/jsnr.jsp?wbtreeid=1632&wbwbxjtuteacherid=502)
* [Chao Shen](https://gr.xjtu.edu.cn/web/cshen)
</details>
    
<details>
<summary>
Shanghai Jiao Tong University/China
</summary>
    
* [Guoxing Chen](https://donnod.github.io/)
* [Haojin Zhu](https://nsec.sjtu.edu.cn/~hjzhu/)
</details>

<details>
<summary>
    Others
</summary>

* [Guang Cheng](https://cyber.seu.edu.cn/cg1/list.htm) (Southeast University/China)
* [Fengwei Zhang](https://fengweiz.github.io/) (Southern University of Science and Technology/China)
* [Qian Wang](http://nisplab.whu.edu.cn/people.html) (Wuhan University/China)
* [Min Yang](https://cs.fudan.edu.cn/3e/d7/c25921a278231/page.htm) (Fudan University/China)
* [Shuguang Cui](https://sse.cuhk.edu.cn/en/faculty/cuishuguang) (The Chinese University of Hong Kong/China)
</details>
  
<details>
<summary>
Overseas
</summary>
    
* [Xuemin (Sherman) Shen](https://uwaterloo.ca/scholar/sshen) (University of Waterloo/Canada)
* [Xiaofeng Wang](https://homes.luddy.indiana.edu/xw7/) (Indiana University Bloomington/United States)
* [Tao Wang](https://www.cs.sfu.ca/~taowang/) (Simon Fraser University/Canada)
* [Ivan Martinovic](https://www.cs.ox.ac.uk/people/ivan.martinovic/) (University of Oxford/United Kingdom)
* [Amir Houmansadr](https://people.cs.umass.edu/~amir/) (University of Massachusetts Amherst/United States)
* [Giuseppe Aceto](http://wpage.unina.it/giuseppe.aceto/) (Università di Napoli Federico II/Italy)
* [Antonio Pescapè](http://wpage.unina.it/pescape/) (Università di Napoli Federico II/Italy)
* [Thorsten Holz](https://cispa.de/en/research/groups/holz) (CISPA Helmholtz Center for Information Security/Germany)
* [Mohammad Saidur Rahman](https://www.rahmanmsaidur.com/) (University of Texas at El Paso/United States)
* [Yue Zhang](https://yue.zyueinfosec.com/) (Drexel University/United States)
* [Xinyu Xing](http://xinyuxing.org/) (Northwestern University/United States)
* [Yang Liu](https://personal.ntu.edu.sg/yangliu/) (Nanyang Technological University/Singapore)
* [Alessandro Finamore](https://afinamore.io/) (Huawei Technologies/France)
* [Thijs van Ede](https://thijsvane.de/) (University of Twente/Netherlands)
</details>




| **实验室名称**                          | **机构**                        | **研究领域**                     | **活跃状态** |
|-----------------------------------------|---------------------------------|----------------------------------|--------------|
| PRL (Privacy Research Lab)             | Princeton University           | 网络隐私、加密通信、流量特征分析 | 🟢 活跃       |
| Computer Security and Industrial Cryptography (COSIC) | KU Leuven (比利时)             | 加密协议、网络匿名性、安全通信   | 🟢 活跃       |
| Network and Distributed Systems Security (NDSS Lab) | UC Irvine                      | 加密协议、匿名通信分析           | 🟢 活跃       |
| Information Security Group (ISG)       | Royal Holloway, University of London | 流量分析、TLS/QUIC研究           | 🟢 活跃       |
| SecLab                                 | Northeastern University        | 加密通信、网络测量、反审查       | 🟢 活跃       |
| Security and Privacy Engineering Lab (SPRITE) | Georgia Tech                   | 加密流量、IoT安全、数据保护      | 🟢 活跃       |
| CISPA Helmholtz Center                 | 德国                            | 加密通信协议分析、网络匿名性     | 🟢 活跃       |

# Blogs
## Network Traffic Knowledge
* [Icoding_F2014](https://blog.csdn.net/jmh1996)
* [Malware-Traffic-Analysis](https://www.malware-traffic-analysis.net/)
* [Awesome-NTA](https://github.com/wangtz19/Awesome-NTA)

## Network Traffic Analysis Tool Manual
* [Tshark](https://www.wireshark.org/docs/man-pages/tshark.html)
* [pyshark](https://github.com/KimiNewt/pyshark)
<!--
https://dilidonglong.com/2019/04/26/tshark%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95/
-->

# Tool Libraries and Frameworks
* [flowcontainer](https://github.com/jmhIcoding/flowcontainer)
* [scapy](https://scapy.net/)
* [wireshark](https://www.wireshark.org/)
* [pyshark](https://kiminewt.github.io/pyshark/)
* [Cisco Talos](https://talosintelligence.com/software)
* [Joy](https://github.com/cisco/joy)
* [Proxifier](https://www.proxifier.com/)
* [traffic_classification_utils](https://github.com/jmhIcoding/traffic_classification_utils)
* [Website-Fingerprinting-Library (WFlib)](https://github.com/Xinhao-Deng/Website-Fingerprinting-Library)

# News and Updates
**Version 2.0**
> March 22, 2025 
1. Welcome to the New Contributors!
2. The content is presented with a clearer structure and style.
3. Fixed some errors.

**Version 1.0**
> April 15, 2022 
1. Welcome to the Ph.Ds from IIE,CAS.

# Contributors 🌟

Thanks goes to these wonderful people!

<table>
  <tr>
    <td align="center"><a href="https://github.com/linwhitehat"><img src="https://avatars3.githubusercontent.com/u/20349381?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Xinjie Lin</b></sub></a><br /><a href="#ideas-XinjieLin" title="Ideas, Planning, & Feedback">🎯</a> <a href="https://github.com/linwhitehat/ETA-Resource/commits?author=linwhitehat" title="Documentation">📝</a> <a href="#maintenance-XinjieLin" title="Maintenance">📔</a></td>
    <td align="center"><a href="https://github.com/CuiTianyu961030"><img src="https://avatars.githubusercontent.com/u/43595189?v=4" width="100px;" alt=""/><br /><sub><b>Tianyu Cui</b></sub></a><br /><a href="#ideas-TianyuCui" title="Ideas, Planning, & Feedback">🎯</a> </td>
    <td align="center"><a href="https://github.com/jmhIcoding"><img src="https://avatars.githubusercontent.com/u/19209689?v=4" width="100px;" alt=""/><br /><sub><b>Minghao Jiang</b></sub></a><br /><a href="#ideas-MinghaoJiang" title="Ideas, Planning, & Feedback">🎯</a> </td>
    <td align="center"><a href="https://github.com/GuanZH95"><img src="https://avatars.githubusercontent.com/u/30852909?v=4" width="100px;" alt=""/><br /><sub><b>Zhong Guan</b></sub></a><br /><a href="#ideas-ZhongGuan" title="Ideas, Planning, & Feedback">🎯</a> <a href="https://github.com/linwhitehat/ETA-Resource/commits?author=GuanZH95" title="Documentation">📝</a></td>
    <td align="center"><a href="https://github.com/wayneowen7"><img src="https://avatars.githubusercontent.com/u/29433723?v=4" width="100px;" alt=""/><br /><sub><b>Wei Cai</b></sub></a><br /><a href="#ideas-WeiCai" title="Ideas, Planning, & Feedback">🎯</a> </td>
    <td align="center"><a href="https://github.com/XiyuanZhang971118"><img src="https://avatars.githubusercontent.com/u/155507014?v=4" width="100px;" alt=""/><br /><sub><b>Xiyuan Zhang</b></sub></a><br /><a href="#ideas-XiyuanZhang" title="Ideas, Planning, & Feedback">🎯</a> <a href="https://github.com/linwhitehat/ETA-Resource/commits?author=XiyuanZhang971118" title="Documentation">📝</a></td>
    <td align="center"><a href="https://github.com/yyyjn"><img src="https://avatars.githubusercontent.com/u/32609644?s=400&v=4" width="100px;" alt=""/><br /><sub><b>Junnan Yin</b></sub></a><br /><a href="#ideas-JunnanYin" title="Ideas, Planning, & Feedback">🎯</a> <a href="https://github.com/linwhitehat/ETA-Resource/commits?author=yyyjn" title="Documentation">📝</a></td>
    <td align="center"><a href="https://github.com/xixiaxibro"><img src="https://avatars.githubusercontent.com/u/48472542?v=4" width="100px;" alt=""/><br /><sub><b>Fulin Zhou</b></sub></a><br /><a href="#troublemaker-FulinZhou" title="Make trouble">🎯</a> <a href="https://github.com/xixiaxibro/ETA-Resource-Imitation/commits?author=xixiaxibro" title="Documentation">📝</a></td>
  </tr>
</table>
