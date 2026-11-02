# refusal_boundary_signature_match

**给模型压缩工程师·拒答边界与过度拒答算一个特征指纹并定位可疑片段。**

`refusal_boundary_signature_match` —— 通过字符级与结构级特征识别模型压缩工程师·拒答边界与过度拒答的痕迹，给出密度与命中位置

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`refusal_boundary_signature_match.py` 拷走就能用
- 不联网、不写文件

## 对应的岗位

- 目标岗位：**生数科技 · 初级模型压缩工程师**
- 技能主线：模型压缩、推理加速、PyTorch、ONNX
- 领域标签：大模型推理、AI基础设施
- 研究方向：模型压缩工程师·拒答边界与过度拒答

工具里的规则表就是照着上面这条岗位要求建的——每条规则都挂在技能线或领域标签上，命中时能指回具体要求。

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install yannvitwo-refusal_boundary_signature_match
```

装完直接用命令名调用：

```bash
refusal_boundary_signature_match --help
```

也可以不用安装，直接把 `refusal_boundary_signature_match.py` 拷走用——它只依赖标准库。

## 为什么需要它

只做特征匹配不做语义判定，所以不会被同义改写绕过

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到岗位要求的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python refusal_boundary_signature_match.py --file input.txt
python refusal_boundary_signature_match.py --text "示例内容"
python refusal_boundary_signature_match.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 相似度按字符与词估算，不等于向量相似度。
- 不联网，不做语义检索。

## 跑测试

```bash
python test_refusal_boundary_signature_match.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/yannvitwo/refusal_boundary_signature_match>

---

## 关于作者

yannvitwo 做模型压缩工程师·拒答边界与过度拒答相关的问题，方向对标生数科技的初级模型压缩工程师岗位。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://yannvitwo.github.io>
- 仓库：<https://github.com/yannvitwo/refusal_boundary_signature_match>

## 许可

MIT，见 [LICENSE](LICENSE)。
