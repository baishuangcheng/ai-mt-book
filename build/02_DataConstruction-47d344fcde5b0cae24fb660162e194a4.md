

\---



\# 📘 3️⃣ 02\_data.md（重点）



```markdown

\# 2 数据准备与语料构建



数据是机器翻译系统的核心。



\---



\## 2.1 平行语料定义



平行语料是指：



> 同一语义内容在不同语言中的对应表达



\---



\## 2.2 汉英语料



来源：



\- 新闻

\- 开源语料库



特点：



\- 数据规模大

\- 结构规范



\---



\## 2.3 汉蒙语料（关键）



来源：



\- 政府网站

\- 新闻媒体

\- 人工构建



特点：



\- 数据规模小

\- 质量不稳定



👉 教学重点：



> 让学生参与语料构建



\---





\## 2.4 数据格式



```text

src.txt

tgt.txt



\##2.5 数据加载

def load\_parallel(src\_path, tgt\_path):

&#x20;   with open(src\_path, encoding='utf-8') as f:

&#x20;       src = f.readlines()

&#x20;   with open(tgt\_path, encoding='utf-8') as f:

&#x20;       tgt = f.readlines()

&#x20;   return \[{"translation": {"src": s.strip(), "tgt": t.strip()}} 

&#x20;           for s, t in zip(src, tgt)]



\##2.6 数据问题分析

问题	影响

数据少	模型不稳定

对齐错误	翻译错误

领域偏差	泛化差



\##2.7 数据增强思路

回译（Back Translation）

同义改写

语料扩展



\##2.8 本节小结



数据质量决定模型上限

