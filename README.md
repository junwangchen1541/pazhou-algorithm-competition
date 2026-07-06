# 琶洲算法大赛：遥感路口目标检测

本仓库用于协作完成琶洲算法大赛初赛任务。当前任务是基于遥感影像切片检测道路交叉口，并区分三类目标：

| ID | 类别 |
| --- | --- |
| 1 | Four-way junction |
| 2 | Three-way junction |
| 3 | Roundabout |

## 任务理解

数据采用 COCO 目标检测格式，不是整图分类任务。模型需要对每张测试图输出目标框、类别和置信度。

初赛数据目录：

```text
train/images/                    训练图片
val/images/                      验证图片
test/images/                     测试图片，标注不可见
annotations/train.json           COCO 训练标注
annotations/val.json             COCO 验证标注
annotations/image_info_test.json COCO 测试图片信息
```

## 数据管理

原始数据和压缩包不提交到 Git。请将比赛数据放在本仓库根目录下：

```text
琶洲算法大赛-初赛数据/
```

该目录已被 `.gitignore` 排除。协作者需要从比赛官方渠道获取数据，并保持相同目录结构。

## 推荐工作流

1. 新建分支开发，不直接在 `main` 上提交实验代码。
2. 每次实验记录模型、输入尺寸、batch size、epoch、验证指标和备注。
3. 训练输出、权重文件、预测结果默认不进 Git，重要结果放到约定的外部存储或 release。
4. 提交 PR 前至少确认数据转换、训练入口或推理脚本能在本地跑通。

## 初始实验建议

RTX 4060 8GB 可先使用 YOLO 系列建立 baseline：

```bash
yolo detect train model=yolo11s.pt data=configs/yolo/data.yaml imgsz=768 batch=8 epochs=100 amp=True
```

如果显存不足，优先降低 batch size；如果仍不足，再降低输入尺寸。

## 仓库结构

```text
configs/        配置文件
docs/           项目说明和协作文档
scripts/        数据转换、训练、推理、提交文件生成脚本
src/            可复用源码
tests/          测试代码
```

当前仓库先建立协作规范和目录骨架，训练代码会在确认技术路线后逐步补齐。
