# dupequest

**找出题库里语义重复的题目。**

`dupequest` —— 对题目做归一化与近重复检测，标出重复题与改写题

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`dupequest.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install index30fer-dupequest
```

装完直接用命令名调用：

```bash
dupequest --help
```

也可以不用安装，直接把 `dupequest.py` 拷走用——它只依赖标准库。

## 为什么需要它

改写题也算重复——题干换词但答案一样的没有额外信息量

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测题库去重 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python dupequest.py --file input.txt
python dupequest.py --text "示例内容"
python dupequest.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 近重复用字符 shingle 估算，长文本阈值需自己调。
- 只报告重复项，不删数据。

## 跑测试

```bash
python test_dupequest.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/index30fer/dupequest>

---

## 关于作者

index30fer 做评测题库去重相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://index30fer.github.io>
- 仓库：<https://github.com/index30fer/dupequest>

## 许可

MIT，见 [LICENSE](LICENSE)。
