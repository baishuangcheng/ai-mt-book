

\---



\# 📘 5️⃣ 04\_experiment.md



```markdown

\# 4 实验设计与结果对比



\---



\## 4.1 训练流程



```python

from transformers import Trainer, TrainingArguments



args = TrainingArguments(

&#x20;   output\_dir="./models",

&#x20;   num\_train\_epochs=1

)



trainer = Trainer(model=model, args=args, train\_dataset=dataset)

trainer.train()



\##4.2 翻译测试

def translate(text):

&#x20;   inputs = tokenizer(text, return\_tensors="pt")

&#x20;   outputs = model.generate(\*\*inputs)

&#x20;   return tokenizer.decode(outputs\[0], skip\_special\_tokens=True)

\##4.3 汉英 vs 汉蒙对比

维度	汉英	汉蒙

精度	高	低

稳定性	高	低

原因	数据丰富	数据稀缺

\##4.4 结果分析

数据决定性能

结构影响表达

