\# 6 跨书写体系与系统扩展



\---



\## 6.1 问题定义



蒙古语存在两种书写体系：



\- 传统蒙古文

\- 西里尔文



\---



\## 6.2 转写示例



```python

def mongolian\_convert(text):

&#x20;   return text.replace("ᠠ", "а")



\##6.3 串接系统

def pipeline(text):

&#x20;   step1 = translate(text)

&#x20;   step2 = mongolian\_convert(step1)

&#x20;   return step2



\##6.4 优缺点



优点：



灵活

可扩展



缺点：



误差累积

\##6.5 本节小结



系统设计比单模型更重要

