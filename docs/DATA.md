# 数据说明

## 本地路径

比赛数据应放置在仓库根目录：

```text
琶洲算法大赛-初赛数据/
```

不要将原始图片、标注文件、压缩包提交到 Git。

## 数据规模

当前初赛数据概况：

| Split | Images | Annotations |
| --- | ---: | ---: |
| train | 4002 | 26329 |
| val | 499 | 3151 |
| test | 502 | 0 |

类别分布：

| Split | Four-way junction | Three-way junction | Roundabout |
| --- | ---: | ---: | ---: |
| train | 20676 | 5504 | 149 |
| val | 2389 | 735 | 27 |

需要特别注意 `Roundabout` 样本明显偏少。

## 格式

标注为 COCO detection 格式：

```text
annotations/train.json
annotations/val.json
annotations/image_info_test.json
```

测试集文件只包含图片信息，不包含 `annotations`。
