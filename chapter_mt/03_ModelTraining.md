

\---



\# 📘 4️⃣ 03\_model.md



```markdown

\# 3 模型构建与原理



\---



\## 3.1 Transformer基础



机器翻译模型通常基于Transformer结构：



\- 编码器（理解）

\- 解码器（生成）



\---



\## 3.2 多语言模型



本案例采用 mBART 模型：



特点：



\- 支持多语言

\- 可迁移学习



\---



\## 3.3 模型加载



```python

from transformers import MBartForConditionalGeneration, MBart50TokenizerFast



model\_name = "facebook/mbart-large-50-many-to-many-mmt"

tokenizer = MBart50TokenizerFast.from\_pretrained(model\_name)

model = MBartForConditionalGeneration.from\_pretrained(model\_name)



\##3.4 数据预处理

def preprocess(example):

&#x20;   inputs = tokenizer(example\["translation"]\["src"], truncation=True)

&#x20;   targets = tokenizer(example\["translation"]\["tgt"], truncation=True)

&#x20;   inputs\["labels"] = targets\["input\_ids"]

&#x20;   return inputs

\##3.5 模型特点分析

特性	说明

多语言共享	参数共享

迁移能力	支持低资源

数据依赖	强

\##3.6 本节小结



模型能力来源于结构 + 数据





\---





