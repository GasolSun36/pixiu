[**中文**](./README_zh.md) | [**English**](./README.md)

## 貔貅(PiXiu): 基于中文金融知识图谱的指令微调模型
Instruct-tuning Large Language Models with Chinese Financial Knowledge Graph

<p align="center" width="100%">
<a ><img src="assets/pixiu.png" alt="PiXiu" style="width: 20%; min-width: 500px; display: block; margin: auto;"></a>
</p>

[![Code License](https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg)](https://github.com/tatsu-lab/stanford_alpaca/blob/main/LICENSE)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/release/python-3100/)

This project open-sources the instruction-tuning model based on Chinese financial knowledge ([Bloom-7b1](https://huggingface.co/bigscience/bloom-7b1)). The instruction-tuning data is constructed based on gpt-3.5-turbo and the Chinese Financial Knowledge Graph (by March 2023), and Bloom-7b1 is fine-tuned to improve its performance on financial domain Q&A.

PiXiu was trained using 8 A100-40g for full parameters and **RLAIF (Reinforcement Learning with AI Feedback)**. The first version of PiXiu (v1.0) was trained using only Q&A data. PiXiu v2.0 was trained by more diverse tasks with more instruction data.

## News
- **[2023.06.25]** We released [PiXiu-v1.0](https://huggingface.co/gasolsun/pixiu-v1.0)and online [demo](https://3608dc4c3b806190cc.gradio.live)🔥🔥🔥

## Case
| Input |ChatGPT|Bloom-7b1| PiXiu-v1.0 output|
|:------------- |:-------------|:------------- |:------------- |
|请问招商银行跟杭州禾迈电力电子股份有限公司在哪些方面存在共同点？|招商银行和杭州禾迈电力电子股份有限公司在以下几个方面存在共同点：两家公司都是中国企业：招商银行是中国大陆的一家银行，而杭州禾迈电力电子股份有限公司是中国大陆的一家电力电子产品制造商。两家公司都致力于技术创新：招商银行一直在数字化转型方面进行探索和尝试，并且在人工智能、区块链等领域也有布局；杭州禾迈电力电子股份有限公司则一直致力于电力电子技术的创新和研发，并且在太阳能逆变器、新能源汽车充电桩等领域处于领先地位。两家公司都注重可持续发展：招商银行将可持续发展视为企业的核心价值和发展战略，积极推动绿色金融和社会责任投资；杭州禾迈电力电子股份有限公司也一直关注环保和可持续发展，在产品研发和生产中注重节能减排和环保要求。总的来说，招商银行和杭州禾迈电力电子股份有限公司在不同领域都有着积极的探索和发展，并且都注重可持续发展，这些都是它们的共同点。| 招商银行和杭州禾迈电力电子股份有限公司在以下几个方面存在共同点：1. 招商银行和杭州禾迈电力电子股份有限公司都是股份制商业银行。2. 招商银行和杭州禾迈电力电子股份有限公司都是国有控股的商业银行。3. 招商银行和杭州禾迈电力电子股份有限公司都是股份制商业银行。4. 招商银行和杭州禾迈电力电子股份有限公司都是国有控股的商业银行。5. 招商银行和杭州禾迈电力电子股份有限公司都是股份制商业银行。6. 招商银行和杭州禾迈电力电子股份有限公司都是国有控股的商业银行。7. 招商银行和杭州禾迈电力电子股份有限公司都是股份制商业银行。|**两家公司都是在深圳证券交易所上市的公司。另外，他们都有共同的股东，包括招商银行股份有限公司、中国工商银行股份有限公司、中国建设银行股份有限公司、中国农业银行股份有限公司等。禾迈股份的涉及行业有计算机、通信和其他电子设备制造业、电气部件与设备、其他元器件、电子设备制造商、电子设备及仪表制造商等，而招商银行则涉及银行、综合性银行、全国性股份制银行、全国性银行、股份制银行、货币金融服务等行业。**|
|中国农业银行的涉及行业有哪些？|中国农业银行是中国五大国有商业银行之一，其涉及的行业主要包括农业、农村、农民相关的金融服务，以及其他与农业相关的行业，例如畜牧业、渔业、林业、种植业等。此外，中国农业银行还提供一般商业银行的金融服务，包括个人储蓄、信用卡、个人贷款、企业贷款、投资理财、国际业务等，涉及的行业范围比较广泛。 | 中国农业银行的涉及行业有农业银行、农村信用社、农村商业银行、农村合作银行、村镇银行、农村资金互助社、小额贷款公司、农村资金互助社、农村资金互助社、农村资金互助社、农村资金互助社、农村资金互助社、|**中国农业银行的涉及行业包括综合性银行、银行、全国性银行、货币金融服务、国有大型银行等。**|
|请你列举一下深圳市瑞丰光电子股份有限公司的属于上市公司的股东。|根据公开披露的信息，深圳市瑞丰光电子股份有限公司的前十大股东及其持股比例如下：瑞丰控股集团有限公司，持股比例为49.58%，深圳市鹏华基金管理有限公司，持股比例为2.86%，国泰君安证券股份有限公司，持股比例为2.14%，国投瑞银基金管理有限公司，持股比例为1.91%，中国工商银行-易方达证券投资基金-易方达中小盘混合型证券投资基金，持股比例为1.50%，中国银行股份有限公司-中银香港证券-中银香港中小企业基金，持股比例为1.24%，深圳市前海开源基金管理有限公司，持股比例为1.08%，中国建设银行股份有限公司-中信建投证券-中信建投中小盘成长股票型证券投资基金，持股比例为1.02%，瑞丰光电子股份有限公司员工持股计划，持股比例为0.97%，中国工商银行-易方达证券投资基金-易方达消费行业股票型证券投资基金，持股比例为0.91%。需要注意的是，股东情况可能会随着时间而变化，以上信息仅供参考。| 深圳市瑞丰光电子股份有限公司的股东有：请你列举一下深圳市瑞丰光电子股份有限公司的股东。|**深圳市瑞丰光电子股份有限公司的属于上市公司的股东包括交通银行股份有限公司、兴业银行股份有限公司、中国国际金融股份有限公司、中信证券股份有限公司、中国工商银行股份有限公司、中国光大银行股份有限公司、中国农业银行股份有限公司和中国建设银行股份有限公司。**|


## TODO list
1. release training code and paper.
2. release instruction-tuning data.
3. release PiXiu v2.0. 📌

## Claims
This project uses the Apache 2.0 protocol. The project assumes no legal responsibility for any of the model's output and will not be held liable for any damages that may result from the use of the resources and output.