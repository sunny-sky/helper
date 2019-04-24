# helper
深度学习课作业指南

## 1 参考文献
- BLEU: [机器翻译质量评测算法-BLEU](https://www.jianshu.com/p/15c22fadcba5)
- [【论文】Match-LSTM 机器阅读理解](https://blog.csdn.net/u012892939/article/details/80186590)
- [Windows下git bash中添加wget](https://www.jianshu.com/p/fb6601795011)
- [LSTM原理及实现](https://blog.csdn.net/gzj_1101/article/details/79376798)
- [Attention原理与文本分类代码实践](https://blog.csdn.net/chen_yiwei/article/details/88647430)
- [浅谈attention机制](https://blog.csdn.net/u014665013/article/details/82619808)

## 2 操作指南
按readme操作过程中：
- 1：cat data/raw/trainset/search.train.json | python utils/preprocess.py > data/preprocessed/trainset/search.train.json
    - 报错 根据百度git提交的issue，建议使用preprocessed数据，因此忽略该步
- 转到python命令
- 2：python run.py --prepare 验证数据是否准备好
    - 报错，UnicodeDecodeError: 'gbk' codec can't decode byte 0x8c in position 52: illegal multibyte sequence
    dataset.py中_load_dataset函数内open(data_path)改为
    open(data_path, 'r', encoding='UTF-8')