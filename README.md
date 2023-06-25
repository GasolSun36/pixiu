## 貔貅(PiXiu): 基于中文金融知识图谱的指令微调模型
Instruct-tuning Large Language Models with Chinese Financial Knowledge Graph

<p align="center" width="100%">
<a ><img src="assets/pixiu.png" alt="PiXiu" style="width: 20%; min-width: 300px; display: block; margin: auto;"></a>
</p>

[![Code License](https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg)](https://github.com/tatsu-lab/stanford_alpaca/blob/main/LICENSE)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/release/python-3100/)

本项目开源了基于中文金融知识图谱指令微调模型([Bloom-7b1](https://huggingface.co/bigscience/bloom-7b1))。指令微调数据根据gpt-3.5-turbo和中文金融知识图谱(2023年3月之前)构建而来，并对Bloom-7b1进行了微调，提升其对金融领域问答的表现。

貔貅使用了8张A100-40g进行全参数训练，并使用了**RLAIF（Reinforcement Learning with AI Feedback）**。第一版本的貔貅（v1.0）只使用了问答数据进行训练，貔貅v2.0由更多样化的任务，更多的指令数据进行训练。

## 最新
- **[2023.06.25]** 我们发布了[貔貅v1.0](https://huggingface.co/gasolsun/pixiu-v1.0)模型以及在线[demo](https://9f716ab56b95fe2b83.gradio.live)🔥🔥🔥

## 示例
| 示例输入 | 貔貅-v1.0输出|
|:------------- |:-------------|
|请问招商银行跟杭州禾迈电力电子股份有限公司在哪些方面存在共同点？|两家公司都是在深圳证券交易所上市的公司。另外，他们都有共同的股东，包括招商银行股份有限公司、中国工商银行股份有限公司、中国建设银行股份有限公司、中国农业银行股份有限公司等。禾迈股份的涉及行业有计算机、通信和其他电子设备制造业、电气部件与设备、其他元器件、电子设备制造商、电子设备及仪表制造商等，而招商银行则涉及银行、综合性银行、全国性股份制银行、全国性银行、股份制银行、货币金融服务等行业。|
|中国农业银行的涉及行业有哪些？|中国农业银行的涉及行业包括综合性银行、银行、全国性银行、货币金融服务、国有大型银行等。|
|请你列举一下深圳市瑞丰光电子股份有限公司的股东。|深圳市瑞丰光电子股份有限公司的股东包括交通银行股份有限公司、兴业银行股份有限公司、中国国际金融股份有限公司、中信证券股份有限公司、中国工商银行股份有限公司、中国光大银行股份有限公司、中国农业银行股份有限公司、招商银行股份有限公司和中国建设银行股份有限公司。|


## 后续计划
1. 开源训练代码与论文。
2. 开源构建的指令微调数据。
3. 开源貔貅v2.0。📌

## 免责声明
本项目使用Apache 2.0协议。对于模型输出的所有内容，本项目不对其承担任何法律责任，同时也不会对使用相关资源和输出结果而可能带来的任何损失承担责任。