# PML-IMB 实验数据集

本仓库说明作者在 PML-IMB 实验中使用的 20 个部分多标签学习（partial multi-label learning，PML）数据集文件。其中，14 个文件是在已有多标签数据集基础上构建的合成 PML 版本；另外 6 个是从第三方研究资源下载的真实世界 PML 基准数据集。文件包含特征、真实标签和候选标签，并非新采集的原始数据。


## 数据来源与处理

**合成 PML 数据集（14 个文件）。** 基础多标签数据来自[科尔多瓦大学 KDIS 多标签数据集资源库](https://www.uco.es/kdis/mllresources/)。为构造 PML 实验数据，在真实标签集合中随机加入假阳性标签，形成候选标签矩阵。

**真实世界 PML 数据集（6 个文件）。** `mirflickr`、`music_emotion`、`music_style`、`YeastBP`、`YeastCC` 和 `YeastMF` 是从第三方下载的 PML 基准数据，可从[东南大学 PALM 研究组的数据资源页](https://palm.seu.edu.cn/zhangml/Resources.htm)下载得到。


## 下载与使用

从 `dataset-v1.0` 版本的附件中下载 `.mat` 文件，并将它们放在同一个 `datasets/` 目录。GitHub 自动生成的“Source code”压缩包并不是数据集压缩包。运行配套的 PML-IMB 代码时，明确指定数据目录：

```bash
python main_graph_split_imb_val.py --data-dir /path/to/datasets
```

实验代码的默认数据集列表是上表 20 个文件名去掉 `.mat` 后缀的结果。若只运行部分数据集，可使用 `--datasets` 参数，例如：

```bash
python main_graph_split_imb_val.py --data-dir /path/to/datasets --datasets Scene_50,Water-quality_50,CAL500_150
```

## 引用与数据权利

使用这些文件时，请引用 PML-IMB 相关论文，以及适用的原始数据集论文或数据源。基础多标签数据集归属[科尔多瓦大学 KDIS 资源库](https://www.uco.es/kdis/mllresources/)所列来源；6 个真实世界 PML 基准数据见[东南大学 PALM 资源页](https://palm.seu.edu.cn/zhangml/Resources.htm)。
本 README 不对第三方数据授予新的许可。有关使用和再分发条款，请查阅原始数据提供方的说明。
