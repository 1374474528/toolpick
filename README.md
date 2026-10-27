# toolpick

**检查智能体在给定任务下选的工具是否合适。**

`toolpick` —— 把任务意图与被选工具的用途做匹配，标出用错工具或该用不用的调用

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`toolpick.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install 1374474528-toolpick
```

装完直接用命令名调用：

```bash
toolpick --help
```

也可以不用安装，直接把 `toolpick.py` 拷走用——它只依赖标准库。

## 为什么需要它

区分「选错工具」与「用对工具但参数错了」

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 工具选择正确性 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python toolpick.py --file input.txt
python toolpick.py --text "示例内容"
python toolpick.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 一致性靠字面差异判定，语义等价但写法不同会误报。
- 不解析跨文档的引用关系。

## 跑测试

```bash
python test_toolpick.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/1374474528/toolpick>

---

## 关于作者

1374474528 做工具选择正确性相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://1374474528.github.io>
- 仓库：<https://github.com/1374474528/toolpick>

## 许可

MIT，见 [LICENSE](LICENSE)。
