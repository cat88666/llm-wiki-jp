# LLM-Wiki-JP 日本語 N2 知識体系

> 基于 Karpathy LLM Wiki 架构的日本語知识编译工程。
> 原始资料只读，由 AI 持续编译为结构化知识库。目标：N5→N2。

**入口：[知识库索引](wiki/index.md)** | [更新日志](wiki/log.md) | [维护规范](CLAUDE.md)

## 仓库结构

```text
├── raw/                    ← 原始学习资料（只读）
├── wiki/
│   ├── index.md            ← 自动生成的索引
│   ├── index.meta.toml     ← 索引配置
│   ├── log.md              ← 更新日志
│   └── concepts/
│       ├── 01-moji-goi/      L0 文字・語彙
│       ├── 02-bunpou-N5N4/   L1 基礎文法（N5-N4）
│       ├── 03-bunpou-N3/     L2 中級文法（N3）
│       ├── 04-bunpou-N2/     L3 上級文法（N2）
│       ├── 05-keigo/         L4 敬語
│       └── 06-dokkai-choukai/ L5 読解・聴解
├── prompt/
│   └── rewrite-prompt.md   ← 页面重写提示词
└── scripts/
    └── build_index.py      ← 索引生成/校验
```

## 知识分层

| 层 | 范围 | 内容 |
|----|------|------|
| L0 | 文字・語彙 | 仮名、漢字、語種、語構成 |
| L1 | 基礎文法 N5-N4 | 動詞活用、助詞、テ形、基本文型 |
| L2 | 中級文法 N3 | 条件、受身/使役、複合動詞、接続表現 |
| L3 | 上級文法 N2 | 書き言葉文型、モダリティ、硬い表現 |
| L4 | 敬語 | 尊敬語/謙譲語/丁寧語、ビジネス敬語 |
| L5 | 読解・聴解 | 読解戦略、聴解技巧、試験対策 |

## 指令

```
/ingest [路径]    把 raw/ 资料编译进 wiki
/query <问题>     基于 wiki 检索回答
/lint             检查知识库健康状态
```

## 索引维护

```bash
python3 scripts/build_index.py          # 重新生成
python3 scripts/build_index.py --check  # 校验
```
