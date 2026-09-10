# 《银河破裂者》Mod：改进水系统（Improved Water System）

> 这是一个《银河破裂者》（The Riftbreaker）的数值 Mod，仅修改了水体相关建筑的参数。

## 简介

提升抽气泵、净水器、液体压缩器与液体解压器的产能，并按固定倍率重新设计各级数值，使水体的生产、缓存与压缩／解压环节保持一致的比例关系。

电能、造价、建造时间、升级链均未改动。

## 数值设计

| 建筑 | Lv1 | Lv2 | Lv3 | 设计关系 |
| --- | --- | --- | --- | --- |
| 液体泵产量 | 150 | 300 | 450 | 基础液体单位 |
| 液体泵缓存 | 600 | 1200 | 1800 | 4 秒缓存 |
| 净水器泥浆输入 | 150 | 300 | 450 | 1 泵 : 1 净水器 |
| 净水器污泥输入 | 300 | 600 | 900 | 泥浆的 2 倍 |
| 净水器水输出 | 150 | 300 | 450 | 与泥浆输入对齐 |
| 净水器缓存 | 600 | 1200 | 1800 | 4 秒缓存 |
| 液体压缩器 | 300 | 600 | 900 | 同级基础液体 × 2 |
| 液体解压器 | 100 | 200 | 300 | 压缩 : 解压 = 3 : 1 |

## 相对原版的改动

写法为 **原版 → 修改后**。

| 建筑 | 等级 | 改动 |
| --- | --- | --- |
| 抽气泵 | lv1 | 产率 100 → 150；容量 400 → 600；最小间距 20 → 10 |
| 抽气泵 | lv2 | 产率 150 → 300；容量 600 → 1200；最小间距 20 → 5 |
| 抽气泵 | lv3 | 产率 200 → 450；容量 800 → 1800；最小间距 20 → 1 |
| 净水器 | lv1 | 泥浆 100 → 150；污泥 200 → 300；水 50 → 150；容量 200 → 600 |
| 净水器 | lv2 | 泥浆 100 → 300；污泥 200 → 600；水 75 → 300；容量 300 → 1200 |
| 净水器 | lv3 | 泥浆 100 → 450；污泥 200 → 900；水 100 → 450；容量 400 → 1800 |
| 液体压缩器 | lv1 | 通量 100 → 300 |
| 液体压缩器 | lv2 | 通量 150 → 600 |
| 液体压缩器 | lv3 | 通量 200 → 900 |
| 液体解压器 | lv1 | 通量 100（与原版一致） |
| 液体解压器 | lv2 | 通量 150 → 200 |
| 液体解压器 | lv3 | 通量 200 → 300 |

电能：净水器 50 / 75 / 100，压缩器 500 / 750 / 1000，解压器 50 / 75 / 100，均与原版一致。

## 各级别关系

```
基础液体单位      150 / 300 / 450
抽气泵产量        150 / 300 / 450   = 基础液体单位
抽气泵缓存        600 / 1200 / 1800 = 4 × 产量
净水器泥浆输入    150 / 300 / 450   = 抽气泵产量（1 台泵配 1 台净水器）
净水器污泥输入    300 / 600 / 900   = 2 × 泥浆输入
净水器水输出      150 / 300 / 450   = 泥浆输入
净水器缓存        600 / 1200 / 1800 = 4 × 水输出
液体压缩器        300 / 600 / 900   = 2 × 基础液体单位
液体解压器        100 / 200 / 300   = 压缩器 ÷ 3
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
