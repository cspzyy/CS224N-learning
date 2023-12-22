# Lecture 1 - Intro & Word Vectors

GPT: Prediction, natural language --> SQL



### Word Meaning & Relationship

representing words as discrete symbols:

```
one-hot(one 1, the rest 0s) vectors:
motel = [0 0 0 0 0 0 0 0 0 0 1 0 0 0 0]
hotel = [0 0 0 0 0 0 0 1 0 0 0 0 0 0 0]
```

Problem: but two one-hot vectors are orthogonal

Solution: learn to encode similarity in the vectors themselves

**Distributional semantics**: A word's meaning is given by the words that frequently appear close-by —— **context**



### Word2Vec

- corpus语料库
- text--t, center word--c, context--o
- Use the **similarity of the word vectors** for c and o to **calculate the probability** of o given c
- **Keep adjusting the word vectors** to maximize this probability

![1702969190526](img\softmax-objective_func.png)

how to calculate P(w~t+j~ | w~t~ ; θ) above

![1702969342488](img\probability.png)



使用“梯度gradient”来降低损失，对目标函数求v~c~偏导：

![1703233237719](img\gradient.png)

![1703233491604](img\probability(2).png)

即梯度为 "observed" - "expected"
