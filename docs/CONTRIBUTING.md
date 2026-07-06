# 协作规范

## 分支

建议使用以下分支命名：

```text
feature/<short-name>
experiment/<model-or-idea>
fix/<short-name>
docs/<short-name>
```

## 提交信息

提交信息尽量具体，例如：

```text
Add COCO to YOLO conversion script
Document baseline training setup
Fix category id mapping
```

## PR 要求

PR 描述建议包含：

- 这次改了什么
- 为什么需要改
- 如何验证
- 是否影响数据路径、训练配置或提交格式

## 实验记录

每次正式实验建议记录：

- git commit
- 模型与预训练权重
- 输入尺寸
- batch size
- epoch
- 数据增强策略
- 验证集指标
- 测试提交文件版本
- 备注和问题

训练产物默认不要提交到 Git。
