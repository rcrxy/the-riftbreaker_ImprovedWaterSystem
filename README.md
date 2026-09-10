# 《银河破裂者》Mod：改进水系统（Improved Water System）

> 这是一个《银河破裂者》（The Riftbreaker）的数值 Mod，仅修改了水体相关建筑的参数。

## 简介

提升抽气泵、净水器、液体压缩器与液体解压器的产能，并让压缩器与解压器的产能对齐，避免压缩液体堆积堵塞。

表中写法均为 **原版 → 修改后**。电能、造价、建造时间、升级链均未改动。

## 数值改动

### 抽气泵 Liquid Pump

| 等级 | 产率 | 容量 | 最小间距 |
| --- | --- | --- | --- |
| lv1 | 100 → **150** | 400 → **600** | 20 → **6** |
| lv2 | 150 → **300** | 600 → **1200** | 20 → **3** |
| lv3 | 200 → **500** | 800 → **2000** | 20 → **0** |

### 净水器 Water Filtering Plant

| 等级 | 泥浆输入 | 污泥输入 | 电能 | 水输出 | 容量 |
| --- | --- | --- | --- | --- | --- |
| lv1 | 100 → **150** | 200 → **300** | 50（不变） | 50 → **150** | 200 → **600** |
| lv2 | 100 → **300** | 200 → **600** | 75（不变） | 75 → **300** | 300 → **1200** |
| lv3 | 100 → **500** | 200 → **1000** | 100（不变） | 100 → **500** | 400 → **2000** |

### 液体压缩器 Liquid Compressor

| 等级 | 输入 / 输出 | 电能 |
| --- | --- | --- |
| lv1 | 100 → **300** | 500（不变） |
| lv2 | 150 → **600** | 750（不变） |
| lv3 | 200 → **1000** | 1000（不变） |

### 液体解压器 Liquid Decompressor

| 等级 | 输入 / 输出 | 电能 |
| --- | --- | --- |
| lv1 | 100 → **300** | 50（不变） |
| lv2 | 150 → **600** | 75（不变） |
| lv3 | 200 → **1000** | 100（不变） |

## 对齐关系

```
抽气泵产率         150 / 300 / 500
净水器泥浆输入     150 / 300 / 500   = 抽气泵产率（1 台泵配 1 台净水器）
净水器水输出       150 / 300 / 500
压缩器             300 / 600 / 1000  = 2 × 抽气泵产率
解压器             300 / 600 / 1000  = 压缩器（1:1，不再堆积）
容量（泵 / 净水器）600 / 1200 / 2000 = 4 秒缓冲
```

## 修改的游戏文件

- `entities/buildings/resources/liquid_pump.ent`
- `entities/buildings/resources/liquid_pump_lvl_2.ent`
- `entities/buildings/resources/liquid_pump_lvl_3.ent`
- `entities/buildings/resources/water_filtering_plant.ent`
- `entities/buildings/resources/water_filtering_plant_lvl_2.ent`
- `entities/buildings/resources/water_filtering_plant_lvl_3.ent`
- `entities/buildings/resources/liquid_compressor.ent`
- `entities/buildings/resources/liquid_compressor_lvl_2.ent`
- `entities/buildings/resources/liquid_compressor_lvl_3.ent`
- `entities/buildings/resources/liquid_decompressor.ent`
- `entities/buildings/resources/liquid_decompressor_lvl_2.ent`
- `entities/buildings/resources/liquid_decompressor_lvl_3.ent`
